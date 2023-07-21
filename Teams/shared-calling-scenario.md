---
title: "Shared Calling scenario"
ms.reviewer: jenstr
ms.date: 7/21/2023
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection: 
  - M365-voice
  - m365initiative-voice
  - highpri
  - Tier1
audience: Admin
appliesto: 
  - Microsoft Teams
ms.localizationpriority: medium
ms.custom: 
  - Phone System
description: "This article provides a Shared Calling example scenario."
---

# Shared Calling example scenario

Before reading this article, be sure you've read [Plan and configure Shared Calling](shared-calling-plan.md) and [Configure Shared Calling routing policies](shared-calling-setup.md). Those articles describe licensing requirements, prerequisite configuration, and how to configure a Shared Calling routing policy.

This article provides a sample scenario for setting up Shared Calling. It provides a PowerShell example for the following steps:

1. Get the user.
1. Enable voice for the user.
1. Get the phone number of the Auto attendant resource account.
1. Create the emergency call routing policy based on the phone number type of the Auto attendant.
1. Set the static emergency location on the resource account.
1. Create the Shared Calling routing policy.
1. Grant the Shared policy to the user.
1. If this is a Direct Routing number, grant an online voice routing policy to the user and resource account.

```powershell
# Get the Shared Calling user
$user = Get-CsOnlineUser -Identity user@contoso.com

# Enable voice for the user
Set-CsPhoneNumberAssignment -Identity user@contoso.com -EnterpriseVoiceEnabled $true

# Get the phone number of the Auto attendant resource account
$main-aa = 'main-aa@contoso.com'
$PhoneNumber=Get-CsPhoneNumberAssignment -AssignedPstnTargetId $main-aa

if ($PhoneNumber.NumberType -eq 'DirectRouting') {

	# Define the emergency numbers for emergency calling
	$en1=New-CsTeamsEmergencyNumber -EmergencyDialString 933 -OnlinePSTNUsage WW
	$en2=New-CsTeamsEmergencyNumber -EmergencyDialString 911 -OnlinePSTNUsage WW

	New-CsTeamsEmergencyCallRoutingPolicy -Identity TECRP-DR -EmergencyNumbers @{add=$en1,$en2} -AllowEnhancedEmergencyServices $true

	# Grant the policy to the user
	Grant-CsTeamsEmergencyCallRoutingPolicy -Identity $user -PolicyName TECRP-DR

}
else {
	# Define the emergency numbers for emergency calling
	$en1=New-CsTeamsEmergencyNumber -EmergencyDialString 933
	$en2=New-CsTeamsEmergencyNumber -EmergencyDialString 911

	New-CsTeamsEmergencyCallRoutingPolicy -Identity TECRP-CPOC -EmergencyNumbers @{add=$en1,$en2} -AllowEnhancedEmergencyServices $true

	# Grant the policy to the user
	Grant-CsTeamsEmergencyCallRoutingPolicy -Identity $user -PolicyName TECRP-CPOC

}


# Set the static emergency location on the resource account
$CivicAddress = Get-CsOnlineLisCivicAdress -City Seattle
Set-CsPhoneNumberAssignment -Identity $main-aa -LocationId $CivicAddress.DefaultLocationId -PhoneNumber $PhoneNumber.TelephoneNumber -PhoneNumberType $PhoneNumber.NumberType

# Create the Shared Calling routing policy
$ecbn1 = '+14255556789'
$ecbn2 = '+14255554321'
$ra = Get-CsOnlineUser -Identity $main-aa
New-CsTeamsSharedCallingRoutingPolicy -Identity Seattle -ResourceAccount $ra.Identity -EmergencyNumbers @{add=$ecbn1,$ecbn2}


# Grant the Shared Calling policy to the user
Grant-CsTeamsSharedCallingRoutingPolicy -Identity $user -PolicyName Seattle

# If this is a Direct Routing number, grant an online voice routing policy to the user and resource account
if ($PhoneNumber.NumberType -eq 'DirectRouting') {
	Grant-CsOnlineVoiceRoutingPolicy -Identity $user -PolicyName Seattle
	Grant-CsOnlineVoiceRoutingPolicy -Identity $main-aa -PolicyName Seattle
}
```

## Related topics

- [Plan and configure Shared Calling](shared-calling-plan.md)
- [Configure Shared Calling routing policies](shared-calling-setup.md)
