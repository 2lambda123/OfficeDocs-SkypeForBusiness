---
title: Purchase, configure, and enable Career Coach for Microsoft Teams for Education
author: SerdarSoysal
ms.author: serdars
ms.reviewer: alaina.creager
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Learn how to purchase, configure, and enable Career Coach for Microsoft Teams for Education.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection: 
  - M365-collaboration
appliesto: 
  - Microsoft Teams
---

# Purchase, configure, and enable Career Coach for Microsoft Teams

Career Coach is a Microsoft Teams for Education app powered by LinkedIn that provides personalized guidance for higher education students to navigate their career journey. Career Coach offers educational institutions a unified career solution for students to discover their career path, grow real-world skills, and build their network all in one place.

## Supported languages

Career Coach is localized in the following languages:

- Chinese (Simplified, Mainland China)
- Chinese (Traditional, Taiwan)
- English (US)
- English (UK)
- French (Canada)
- French (France)
- German (Deutschland)
- Japanese (Japan)
- Portuguese (Brazil)
- Spanish (Spain)
- Spanish (Mexico)

Learn more about [Career Coach](https://aka.ms/career-coach).

> [!TIP]
> Use the best practices and helpful tips in this guide to enable the capabilities of Career Coach for students, faculty, and staff. See the [Quick planning guide](https://support.microsoft.com/office/c5d0b934-bfcf-4fe7-8a85-ba7bbb1b6ad4) article.

## Review the requirements

To enable Career Coach for your educational institution, review what you need to get Career Coach up and running.

### Technical requirements

- Office 365 tenant with Azure Active Directory with LinkedIn account connections enabled.
- Microsoft Teams.
- LinkedIn School Page.

### Data and files from your educational institution

- Educational institution's logo and graphical assets [in the required format](#brand-and-preferences).

- Course catalog data. [View sample file](https://aka.ms/career-coach/docs/it-admins/sample-catalog) and [document format](#course-catalog-document-format-and-schema).

- List of fields of study offered. [View sample file](https://aka.ms/career-coach/docs/it-admins/sample-fieldsofstudy).

- Educational institution’s [LinkedIn School Page URL](https://www.linkedin.com/help/linkedin/answer/40133/differences-between-a-linkedin-page-for-a-school-and-company?lang=en).

- Educational institution's privacy policy URL.

- Educational institution links to career-related resources such as a career services website and student job postings (optional).

## Setup checklist

In preparation to release Career Coach for your tenant there are several admin roles that will be needed. These roles and permissions may be assigned to one individual or may require collaboration with IT professionals in your organization. Use this guide to help identify the individuals necessary to complete the needed tasks.

You can check your account’s assigned roles by visiting the [Microsoft 365 admin center > Users > Active users](https://go.microsoft.com/fwlink/p/?linkid=834822) > Select your username to confirm your role.

Learn more about [admin roles in the Microsoft 365 admin center](/microsoft-365/admin/add-users/about-admin-roles).

### [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339)

Role: [Global Administrator](/azure/active-directory/roles/permissions-reference#global-administrator)
Career Coach tasks:

- [Purchase licenses](#purchase-career-coach-licenses)
- [Assign licenses](#assign-career-coach-licenses-to-users)

### [Azure Active Directory admin center](https://go.microsoft.com/fwlink/p/?linkid=2067268)

Role: [Global Administrator](/azure/active-directory/roles/permissions-reference#global-administrator)
Career Coach task:

- [Turn on LinkedIn account connections](#turn-on-linkedin-account-connections)

### [Teams admin center](https://admin.teams.microsoft.com/dashboard)

Role: [Teams administrator](/azure/active-directory/roles/permissions-reference#teams-administrator)
Career Coach tasks:

- [Add Career Coach as an installed app](#add-career-coach-as-an-installed-app)
- [Configure the Career Coach app settings](#configure-career-coach-settings)
  - [Brand and preferences](#brand-and-preferences) - required
  - [LinkedIn connection](#linkedin-connection) - required
  - [Course catalog](#course-catalog) - required
  - [Fields of study](#fields-of-study) - required
  - [Customization](#customization) - optional
- [Setup policies](#setup-policies-and-pin-the-app)
- [Pin the app](#setup-policies-and-pin-the-app)

### LinkedIn developer portal

Role: [LinkedIn School Page Super Admin](https://www.linkedin.com/help/linkedin/answer/a541981)
Career Coach task:

- [Verify the LinkedIn School Page](#verify-the-linkedin-school-page)

## Purchase Career Coach licenses

### License types

Career Coach requires a license to access the application.

There are two license types available.

- The **Student license** is designed for students.
- The **Faculty license** is designed for faculty, staff, and IT professionals involved in supporting students with Career Coach.

> [!IMPORTANT]
> A Career Coach **Faculty license** must be assigned to the IT admin completing the configuration.

### Purchase licenses

Career Coach is available worldwide (except China and Russia) for qualified higher education institutions as an add-on license through Enrollment for Education Solutions (EES), Cloud Service Providers (CSP), and Microsoft 365 admin center (web direct).

As a Microsoft Teams app, the tenant must have Microsoft 365 A3/A5 or Office 365 A1/A3/A5 to purchase the add-on Career Coach license. Separate licenses are offered for students and faculty users.

### Sign up for a free trial

A standard 90-day free trial is available for 25 students and 25 faculty/staff licenses. One trial is available per qualifying tenant. Trial licenses can be activated from Microsoft 365 admin center by tenants who are qualified to purchase Career Coach.

For trial activation, sign into [Microsoft 365 admin center > Billing > Purchase services > search for Career Coach](https://go.microsoft.com/fwlink/p/?linkid=868433) to find the [student license trial](https://signup.microsoft.com/signup?OfferId=b3a40ff2-3d0d-481e-a0ed-f4de1069f201) and [faculty license trial](https://signup.microsoft.com/signup?OfferId=6f6e7db5-b9ab-4baa-86be-f13d0ae6a2c8).

## Prepare for Career Coach

### Turn on LinkedIn account connections

There are two ways LinkedIn account connections are used by Career Coach.

- To allow students, faculty, and staff to connect their Microsoft 365 account to their LinkedIn account and [send LinkedIn invitations from Career Coach](https://support.microsoft.com/topic/career-coach-quick-start-guide-for-students-c419db47-9290-4961-9684-c3f86a9b3708#bkmk_connect_your_linkedin_account).
- To turn on the [Build your Network](https://support.microsoft.com/topic/career-coach-quick-start-guide-for-students-c419db47-9290-4961-9684-c3f86a9b3708#bkmk_build_your_network) and [Explore Careers](https://support.microsoft.com/topic/career-coach-quick-start-guide-for-students-c419db47-9290-4961-9684-c3f86a9b3708#bkmk_discover_your_career_path) features using public alumni data from LinkedIn.

1. Sign into the [Azure AD admin center](https://go.microsoft.com/fwlink/p/?linkid=2067268) with a [global admin account](#setup-checklist) for the Azure AD organization.

2. Select **Users**.

3. On the **Users** page, select **User settings**.

4. **LinkedIn account connections** must be set to **Yes** or **Selected group** for Career Coach to be properly configured.

   - Select **Yes** to enable the service for all users in your educational institution.
   - Select **Selected group** to enable the service for only a group of selected users in your educational institution.

For more information, see [LinkedIn account connections in Azure Active Directory](/azure/active-directory/enterprise-users/linkedin-integration).

> [!NOTE]
> No data is shared without the user's consent.

### Allow Microsoft apps in Teams

Career Coach is a Microsoft application, and so it must be allowed within Teams app permission policies.

1. Sign in to the **[Teams admin center](https://admin.teams.microsoft.com)**.

2. In the left navigation, select **Teams apps** > **[Permission policies](https://admin.teams.microsoft.com/policies/manage-apps)**.

3. Select your preferred policy.
    1. If you're unsure which policy to use, refer to the [Microsoft Teams Policy management documentation](policy-packages-edu.md) or use the [Education policy wizard](easy-policy-setup-edu.md) to configure a policy for Microsoft Teams.

Learn more about [configuring permission policies](teams-app-permission-policies.md).

### Add Career Coach as an installed app

This step ensures that Career Coach is properly configured for your organization and that students find Career Coach.

1. Sign into the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851).

2. Select **Teams apps** > **Setup policies**, and select your preferred policy.
    1. If you're unsure which policy to use, refer to the [Microsoft Teams Policy management documentation](policy-packages-edu.md) or use the [Education policy wizard](easy-policy-setup-edu.md) to configure a policy for Microsoft Teams.

3. Under **Installed apps**, select **+ Add apps**.

4. In the **Add installed apps** pane, search for the apps you want to automatically install for users when they start Teams. You can also filter apps by app permission policy.

5. When you've chosen your list of apps, select **Add**.

6. Select **Save** > **Confirm**.

> [!NOTE]
> Editing or assigning a policy can take a few hours for changes to take effect. The Career Coach won't be available in Microsoft Teams until the changes are complete.

## Configure Career Coach settings

### Access the Career Coach app settings

To configure Career Coach settings and enable it for users, you must be a global admin or Teams service admin to access the page.

1. Sign into the [Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851).
2. In the left navigation, select **Teams apps** > **Manage apps**.
3. Search or browse for **Career Coach**.
4. Select **Career Coach**, and then **Settings**.

![shows the Career Coach app selected with the Settings tab selected.](media/career-coach-app-updated.png)

### Career Coach configuration categories

To effectively enable Career Coach for students, faculty, and staff, the following settings are required:

- [Brand and preferences](#brand-and-preferences)
- [LinkedIn connection](#linkedin-connection)
- [Course catalog](#course-catalog)
- [Fields of study](#fields-of-study)

You can also set optional [Customization](#customization) settings.

> [!TIP]
> Quickly navigate from one category to another by selecting **Career Coach** path located at the top of the page in the format `Manage apps\Career Coach\Setting label`.

### Brand and preferences

Customize Career Coach to match your educational institution’s brand. You're responsible for respecting others' rights, including copyright and trademark rights.

> [!IMPORTANT]
> This is a required section. Career Coach can't be enabled without **Brand and preferences** submitted.

1. Sign into the **[Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851)**.

2. Select **Teams apps** > **Manage apps** > **Career Coach** > **Settings** > **Edit brand and preferences**.

3. Under **Branding**, add **Organization name**.

4. Upload the **Organization icon**. The icon is used throughout Career Coach to identify content unique to your educational institution, course catalog resources throughout the app, and on the real-world experiences section of the dashboard.

    The icon is best formatted as:

    - A transparent PNG
    - Aspect ratio of 1:1
    - Maximum size of 64 px x 64 px

5. Upload the **Learning content thumbnail image**. The thumbnail will be used for course catalog learning resources throughout the app when a specific image isn't specified for a course offered by your educational institution.

    The thumbnail is best formatted as:

    - A PNG
    - Aspect ratio of 16:9
    - Maximum size of 360 px x 200 px

6. Add the **Organization privacy policy URL**. If added, the institution's privacy policy will be available for students to review in Career Coach.

7. Select **Submit**.

8. To confirm settings were submitted successfully, check [Career Coach configuration status](#configuration-status) for **Complete**.

![the Career Coach branding section of the admin center.](media/career-coach-brand-updated.png)

### LinkedIn connection

The LinkedIn connection setting connects Career Coach with public alumni data from your institution’s LinkedIn School Page.

This step can only be completed if [LinkedIn account connections are enabled in Azure Active Directory](#turn-on-linkedin-account-connections). The LinkedIn connection setting enables the [Build your Network](https://support.microsoft.com/topic/career-coach-quick-start-guide-for-students-c419db47-9290-4961-9684-c3f86a9b3708#bkmk_build_your_network) and [Explore Careers](https://support.microsoft.com/topic/career-coach-quick-start-guide-for-students-c419db47-9290-4961-9684-c3f86a9b3708#bkmk_discover_your_career_path) features.

> [!IMPORTANT]
> This is a required section. Career Coach can't be enabled without the LinkedIn School Page connection verified.

#### Add the LinkedIn School Page URL

The process of adding the LinkedIn School Page URL is handled by a Teams Administrator. The subsequent step of verifying the URL is completed by your educational institution’s LinkedIn School Page Super admin.

1. Sign into the **[Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851)**.

2. Select **Teams apps** > **Manage apps** > **Career Coach** > **Settings** > **LinkedIn connection**.

3. Select **Connect to LinkedIn**.

4. Find your institution's LinkedIn School Page by searching on LinkedIn and selecting the **School** filter. Or connect with a marketing staff member at your institution to determine the correct LinkedIn School Page to use. For more information, see [How to identify LinkedIn pages](https://www.linkedin.com/help/linkedin/answer/40133/differences-between-a-linkedin-page-for-a-school-and-company?lang=en).

    ![linkedin search for school.](media/career-coach-school-search-updated.png)

5. Add the **LinkedIn School Page URL**. The URL must be a *school page*, not a *company page*, and is typically formatted as `https://www.linkedin.com/school/willow-university/`.

   ![linkedin School Page example.](media/career-coach-linkedin-page-url-updated.png)

6. Select **Submit**.

7. After the **LinkedIn School Page URL** is successfully submitted, the settings page will update to show the **Verification link** and **Verification link expiration**. The verification link expires after 30 days.

8. Copy the **Verification link** and share it with your educational institution’s LinkedIn School Page Super admin.

9. The LinkedIn School Page Super admin will use the unique verification link to [verify the LinkedIn School Page](#verify-the-linkedin-school-page) and associate it with Career Coach.

10. To confirm the verification and settings were submitted successfully, check that the [Career Coach configuration status](#configuration-status) is marked **Complete**.

#### Verify the LinkedIn School Page

The LinkedIn School Page verification must be completed by your educational institution’s [LinkedIn School Page Super admin](https://www.linkedin.com/help/linkedin/answer/a541981).

You can check your LinkedIn account’s admin roles by signing into LinkedIn and visiting your educational institution’s LinkedIn School Page. If your account is assigned a Super admin role, you'll see **Super admin view** listed next to your educational institution’s name on the LinkedIn page. If you don't see the **Super admin view** tag, then you're not a Super admin for your school’s page.

1. After the **LinkedIn School Page URL** is submitted by the Teams administrator, the page will show the **Verification link** and **Verification link expiration**. The verification link expires after 30 days.

   ![linkedin connections for the career coach app.](media/career-coach-linkedin-updated.png)  

2. Copy the verification link and share it with your LinkedIn School Page Super admin.

3. The LinkedIn page Super admin will open the verification link to associate Career Coach with your school's page. For more information, see [Additional documentation about LinkedIn page verification](https://www.linkedin.com/help/linkedin/answer/102672).

4. Once verification is complete, the Teams administrator can view whether the settings were submitted successfully by checking if the [Career Coach configuration status](#configuration-status) is marked **Complete**.

   ![linkedin page verification in the linkedin developer portal.](media/career-coach-linkedin-verification-updated.png)

### Course catalog

The course catalog records the courses and classes offered by your educational institution.

Career Coach uses course catalog data to identify a student’s skills from their transcript and to suggest courses to take.

> [!IMPORTANT]
> This is a required section. Career Coach can't be enabled without a course catalog.

These courses are used within Career Coach in two areas:

- Courses are returned as part of [learning resources](https://support.microsoft.com/topic/career-coach-quick-start-guide-for-students-c419db47-9290-4961-9684-c3f86a9b3708#bkmk_grow_real_world_skills).  

- Courses and course metadata, like course titles and descriptions, are used to help students identify their skills when they [upload a transcript](https://support.microsoft.com/topic/career-coach-quick-start-guide-for-students-c419db47-9290-4961-9684-c3f86a9b3708#bkmk_Set_up_your_profile).

To create the course catalog, put together a list of all courses taught at your educational institution and upload it as a CSV file using the [course catalog document format and schema](#course-catalog-document-format-and-schema).

> [!TIP]
> Start with the [sample course catalog](https://aka.ms/career-coach/docs/it-admins/sample-catalog) document to ensure proper formatting.  You can also reference the [course catalog document format and schema](#course-catalog-document-format-and-schema) sections for details on required and recommended fields.

#### Add the course catalog

1. Sign into the **[Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851)**.

2. Select **Teams apps** > **Manage apps** > Search **Career Coach** > **Settings** > **Course catalog**.

3. Select **Upload Course Catalog** > Upload courses in CSV format with the required columns: courseId, title, and sourceLink.
    1. Each row must include data for each of the required columns.
    1. *Including the recommended fields improves the experience for students by returning better search results and skill identification.*

4. A preview of a section of the uploaded course catalog will appear for your reference.

5. Select **Submit** when ready.

6. The [status of the uploaded document](#course-catalog-status) is shown in the settings page.

7. To confirm settings were submitted successfully, check that the [Career Coach configuration status](#configuration-status) is marked **Complete**.

> [!TIP]
> To upload a new file, ensure the last file is cleared by selecting (X) to close the document preview. This action will allow the **Upload** button to display again.

![the course catalog section of the career coach app.](media/course-catalog-updated.png)

#### Course catalog document format and schema

The document needs to be in CSV format with a maximum size of 18 MB. Large files should be split into multiple smaller files that include a maximum of 15,000 rows for successful processing.

The document must contain the required course metadata: **course title**, **course ID**, and **course URL**.

> [!TIP]
> Start with the [sample course catalog]( https://aka.ms/career-coach/docs/it-admins/sample-catalog) document to ensure proper formatting. *Including the recommended fields improves the experience for students by returning better search results and skill identification.*

The following table shows the items to include in the course catalog:

| Name             | Status      | Type   | Description                                                                    |
|------------------|-------------|--------|--------------------------------------------------------------------------------|
| courseId         | Required    | string | The courseId maps to what is generated in the student transcript.             |
| title            | Required    | string | The course title.                                                              |
| sourceLink       | Required    | URL    | Website link to the course page to learn more about the course and syllabus.   |
| description      | Recommended | string | Introduction text for the course that describes the learning objectives.       |
| language         | Recommended | string | Language of the course. Use standard language codes.                           |
| format           | Recommended | string | Mode of teaching (online, video, in person).                                   |
| thumbnailLink    | Recommended | URL    | Thumbnail link to the course image.                                            |
| thumbnailAltText | Recommended | string | Accessibility alt text for the image                                           |
| educationLevel   | Recommended | string | Study level, ex. Undergraduate/Graduate.                                       |
| topics           | Recommended | string | Topics or tags that are associated with the skills the courses teach.          |

### Course catalog status

The course catalog status is shown on the Course catalog settings page once a document has been uploaded, providing details of the document upload and processing status.

During processing, Career Coach will analyze your document for duplicates, normalize and enrich your catalog by extracting skills from titles and descriptions, and store it for use on the Learn page and during student transcript uploads for skill identification.

![the course catalog upload status of the career coach app.](media/career-coach-course-catalog-status-updated.png)

| Column           | Value     | Description                                                                                        |
| ---------------- | --------- | -------------------------------------------------------------------------------------------------- |
| Time uploaded    | Timestamp | Date and time an IT admin uploaded a document.                                                     |
| Time completed   | Timestamp | Date and time the document was processed completely.                                               |
| Courses uploaded | Integer   | Number of courses found in the document.                                                           |
| Ingestion status | Pending   | Document in queue for processing.                                                                  |
| Ingestion status | Running   | Document is currently be processed. This process can take up to 6 hours depending on the size of your document. |
| Ingestion status | Success   | Ingestion process is complete, and courses will be available in Career Coach once all required settings are configured. |
| Ingestion status | Failed    | Check the document format and reupload.                                                           |
| Duplicates       | Integer   | Number of duplicate courses found in the document.                                                 |

> [!NOTE]
> If a column in the course catalog status is blank, the document is currently being processed, and those values aren't available. This process can take up to 6 hours depending on the size of your catalog. Once the document has been processed, the values will be populated. You can refresh the page to check for updates.

### Fields of study

The fields of study are synonymous with major areas of interest, academic major, and degree programs. These fields of study are referenced by students when they start using Career Coach and begin setting up their personalized profile.

The list of fields lets students discover fields of study that may interest them and add their planned academic focus to their profile in Career Coach.

> [!IMPORTANT]
> This is a required section. Career Coach can't be enabled without a list of fields of study.
>
> Add all fields of study available to students such as Engineering, English, Business, and so on

#### Add the fields of study

1. Sign in to the **[Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851)**.

2. Select **Teams apps** > **Manage apps** > Search **Career Coach** > **Settings** >  **Fields of study**.

3. Select **Upload** to upload the fields of study file in CSV format. A preview of the fields of study document will appear.

4. Select **Submit**.

5. To confirm the settings were submitted successfully, check that the [Career Coach configuration status](#configuration-status) is marked **Complete**.

#### Fields of study document format and schema

The document needs to be in CSV format with a maximum size of 18 MB. The document must contain the required metadata: **Field of study name**.

The following table shows the items to include in the fields of study:

| Name          | Status   | Type   | Description                    |
|---------------|----------|--------|--------------------------------|
| fieldsOfStudy | Required | string | The name of the field of study |

### Customization

The Customization setting supports adding opportunities to gain real-world experiences to the dashboard that your educational institution offers to students.

The recommended links to include are those that help students gain real-world experience, like job boards, events, career services office, career-related events, and student clubs.

1. Sign into the **[Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851)**.

2. Select **Teams apps** > **Manage apps** > Search **Career Coach** > **Settings**.

3. Select **Customize the experience** > **+ Add**

4. Add each **title**, **URL**, and **info-tip description** > Select **Apply**.

5. A preview of the added information will appear.

6. Select **Submit**.

## Career Coach settings status

The Career Coach settings page in Teams admin center provides a status summary of incomplete, pending, complete, and failed steps for configuring Career Coach.

The status message can help you determine whether Career Coach is properly configured and ready to release to your tenant.

### Configuration status

The configuration status section of the app settings page will display the real-time status using the following legend.

![the configuration status section of the career coach app.](media/career-coach-config-status-updated.png)

| Category                    | Status                                        | Description                                                 |
| --------------------------- | --------------------------------------------- | ----------------------------------------------------------- |
| Service provisioning status | Career Coach is initializing your tenant.     | Service provisioning occurs automatically upon accessing the Career Coach settings page. Configuration changes won't be accepted until initial setup is complete. Estimated time for service provisioning is up to 15 minutes. |
| Service provisioning status | Career Coach is ready to be configured.       | Career Coach settings page is ready for IT admin to submit settings. |
| Brand and preferences       | Not started                                   | Settings need to be submitted. |
| Brand and preferences       | Missing: Learning icon                        | Upload the missing learning content thumbnail image. |
| Brand and preferences       | Missing: Logo                                 | Upload the missing organization icon. |
| Brand and preferences       | Missing: Institution name                     | Upload the missing organization name. |
| Brand and preferences       | Complete                                      | No further action needed. Setting is complete. |
| Course catalog upload       | Not started                                   | Course catalog CSV needs to be submitted. |
| Course catalog upload       | Missing: a successful course catalog upload   | Check the course catalog status for details on course catalog processing. |
| Course catalog upload       | Complete                                      | No further action needed. Setting is complete. |
| LinkedIn school connection  | Not started                                   | LinkedIn School Page URL needs to be submitted. |
| LinkedIn school connection  | Missing: an approved LinkedIn School Page URL | Awaiting LinkedIn School Page Super admin verification approval. |
| LinkedIn school connection  | Complete                                      | No further action needed. Setting is complete. |
| Fields of study upload      | Not started                                   | Field of study CSV needs to be submitted. |
| Fields of study upload      | Missing: areas of interest                    | Check whether the field of study upload is successful. |
| Fields of study upload      | Complete                                      | No further action needed. Setting is complete. |

> [!NOTE]
> Once all required steps are marked as complete, Career Coach can be successfully released to your tenant.

## Making Career Coach available to your organization

At this point, Career Coach has been configured for your organization.

Next, follow these steps to ensure Career Coach is available to your organization in Microsoft Teams.

### Assign Career Coach licenses to users

For step-by-step instructions, see [Assign licenses to users](/microsoft-365/admin/manage/assign-licenses-to-users).

### Setup policies and pin the app

Pinning Career Coach will add it to the left rail of the Microsoft Teams window to make it more accessible and visible for students. If you prefer to pin Career Coach for a subset of your users, then you'll need to implement a [Setup policy](teams-app-setup-policies.md) with that group included.

1. Sign into the **[Teams admin center](https://go.microsoft.com/fwlink/p/?linkid=2066851)**.

2. Select **Teams apps** > **Setup policies** and select your preferred policy.

    If you're unsure which policy to use, refer to the [Microsoft Teams Policy management documentation](policy-packages-edu.md) or use the [Education policy wizard](easy-policy-setup-edu.md) to configure a policy for Microsoft Teams.

3. Under **Pinned apps**, choose **Add apps**.

4. Select your preferred policy under **Search based on this app permission policy**.

5. Search for **Career Coach** under **Search by name**, and then select **Add** > **Add** to close the pane.

6. Choose the order for the app to appear and select **Confirm**.

> [!NOTE]
> Students will be notified in Microsoft Teams that Career Coach has been pinned.

## Accessibility in Career Coach

Career Coach has a responsibility to create an experience that is accessible for all users. Career Coach conforms to WCAG 2.1 A, AA and AAA and adopts all global accessibility standards.

Career Coach accessibility features include:

- A logical heading structure and clear focus indicators to support navigation by mouse, keyboard or voice.
- Skip links to allow users to get to important features faster.
- Clear and concise text to make reading and understanding Career Coach simple for all users.
- Color contrast with Dark and High contrast modes for diverse needs and preferences.
- A right sized user experience that is verified on all formats (PC, Mac, Android and iPhone) using [Section 508 Trusted Testers](https://www.dhs.gov/trusted-tester).

## Troubleshooting

### Missing required configuration data

If you see "Career Coach is currently being set up for you to use soon" in the Career Coach experience, **all required configuration data hasn't been added**.

The following **sections must be completed** before Career Coach can be used:

- [Brand and preferences](#brand-and-preferences)
- [LinkedIn connection](#linkedin-connection)
- [Course catalog](#course-catalog)
- [Fields of study](#fields-of-study)

Reference the [Career Coach configuration status](#configuration-status) to see which settings need to be completed.

### Incorrect formatting of Course catalog or Fields of study data

CSVs for course catalog and field of study have required formats and a maximum size of 18 MB.

Reference the Career Coach [course catalog document schema](#course-catalog-document-format-and-schema) and Career Coach [fields of study document schema](#fields-of-study-document-format-and-schema) to ensure proper configuration.

Additionally, a course catalog file should have no more than 15,000 rows to ensure successful processing.

### Missing fields in Career Coach settings pages

Career Coach settings pages have required fields. If necessary fields aren't completed, the page won't submit.

You may not see a warning message; the page won't submit.

The submission is successful when you see a green banner at the top of the page.

### Setup policy changes aren't complete

If Career Coach isn't showing in Microsoft Teams for users, then the setup policy changes may not have taken effect yet. Career Coach won't be installed and pinned for users in Microsoft Teams until the setup policy changes take effect. Policy changes can take a few hours to take effect.

However, Career Coach can be installed directly from the Microsoft Teams app store.

- If users are unable to find Career Coach in the Microsoft Teams app store, review your app permission policies and ensure that Career Coach isn't a blocked app.
- Career Coach is a Microsoft app, and it's a best practice to allow Microsoft apps by permission policies. Learn more about [configuring permission policies](teams-app-permission-policies.md).

### Career Coach initialization isn't complete

You may encounter the following error: “We can't retrieve the app's settings. Try again. If you continue to have problems, contact Microsoft customer support.”

Check the **Service Provisioning status** on the Career Coach settings page.

If your tenant is still being initialized, wait 15 minutes and try again. Open a support ticket if you still receive the error.

## Resources

The following resources will help you plan your Career Coach implementation with Microsoft Teams.

- [Career Coach quick planning guide](https://support.microsoft.com/topic/career-coach-quick-planning-guide-c5d0b934-bfcf-4fe7-8a85-ba7bbb1b6ad4)
- [Career Coach quick start guide for students](https://support.microsoft.com/topic/career-coach-quick-start-guide-for-students-c419db47-9290-4961-9684-c3f86a9b3708)
- [Engage students with Career Coach lesson plans](https://support.microsoft.com/topic/get-started-with-career-coach-goals-and-activities-086ce412-05de-4259-a9fd-c96471cef1b0?preview=true)
- [Welcome to Microsoft Teams](Teams-overview.md)
- [How to roll out Teams](get-started-with-teams-resources-for-org-wide-rollout.md?tabs=SmallBusiness)
- [Overview of teams and channels in Microsoft Teams](teams-channels-overview.md)
- [Managing apps in Microsoft Teams admin center](manage-apps.md)
- [Getting started with admin training for Microsoft Teams](ITAdmin-readiness.md)
- [Teams troubleshooting](/microsoftteams/troubleshoot/teams-welcome)
- [Manage app permission policies in Microsoft Teams](teams-app-permission-policies.md)
