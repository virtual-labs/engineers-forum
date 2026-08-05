# Virtual Labs Bug Management Process

## Introduction

The **Virtual Labs Bug Management Process** outlines the systematic approach for handling, tracking, and resolving bugs within the Virtual Labs project. This process is designed to ensure that all bugs are efficiently documented, prioritized, and addressed, maintaining the quality and reliability of the labs. By following this standardized workflow, developers can effectively collaborate to fix issues, implement improvements, and ensure that Virtual Labs provides a seamless and high-quality experience for users.

## Purpose

This document serves as a guide for developers to follow during the bug resolution lifecycle, from identification to closure. It details the steps involved in documenting and fixing bugs reported for experiments.

## Audience

This document is intended for all lab developers and owners working to fix experiment bugs within the Virtual Labs ecosystem.

## Virtual Labs Bug Management Workflow

When a Virtual Lab user reports a bug through the bug reporting tool, it is automatically logged as an issue in the [GitHub Bug Tracker](https://github.com/virtual-labs/bugs-virtual-labs/issues). Each bug is assigned an **Institute Label** corresponding to the institute responsible for developing the lab.

Since all reported bugs are managed as GitHub issues, developers require **triage access** to the `bugs-virtual-labs` repository before they can assign issues, apply labels, or add comments. If you are setting up bug management for the first time, begin by requesting repository access as described in **Step 1** below.

Once you have the required permissions, you can monitor, analyze, assign, and resolve bugs for your institute using GitHub's issue management features. If you are unfamiliar with GitHub Issues, the following documentation will help you understand the basic workflows before proceeding:

- [Assigning Issues](https://docs.github.com/en/issues/tracking-your-work-with-issues/using-issues/assigning-issues-and-pull-requests-to-other-github-users)
- [Managing Labels](https://docs.github.com/en/issues/using-labels-and-milestones-to-track-work/managing-labels)
- [Commenting on Issues](https://docs.github.com/en/actions/use-cases-and-examples/project-management/commenting-on-an-issue-when-a-label-is-added)

Follow the steps below to obtain access, monitor reported bugs, and manage their resolution for your institute, ensuring the availability of high-quality Virtual Labs.

### Step 1. Obtain Access and Monitor Logged Bugs

- Repository access requests for each institute are available [here](https://github.com/virtual-labs/engineers-forum/issues?q=is%3Aissue+is%3Aopen+%22Bug+Repository+Access+Request+for%22). If you do not already have access, comment with your GitHub details on your institute's corresponding access request issue. For example, see the [Bug Repository Access Request for IITH](https://github.com/virtual-labs/engineers-forum/issues/984).

- The **Institute Developer Lead** is responsible for managing developer access to the bug repository. Whenever a new developer joins the institute's Virtual Labs team, the Institute Developer Lead should request repository access for them. Similarly, if a developer leaves the team, the Institute Developer Lead should submit a request to remove their access from the bug repository.

- Once your request is approved, you will receive **triage** permissions for the `bugs-virtual-labs` repository. These permissions allow you to assign issues, apply labels, and comment on them.

- After obtaining access, filter issues using your institute's label to view and monitor bugs reported for the Virtual Labs developed by your institute.

#### Bug Analytics Dashboard

A centralized [Virtual Labs Bug Analytics Dashboard](https://datastudio.google.com/embed/reporting/534cd76b-580b-464a-b370-b85f980a76d0/page/p_ckvok7gord) is available for monitoring and analyzing bug reporting and processing activities across Virtual Labs. The dashboard provides insights into institute-wise and lab-wise bug trends, issue status distribution, resolution progress, and overall bug management activity.

Developers, reviewers, coordinators, and nodal centres can use this dashboard to track the effectiveness and progress of bug handling workflows.

### Step 2. Understand the Bug

- Analyze a reported bug by viewing the following key details:
  - **Lab Name**: The name of the lab where the issue occurred.
  - **Experiment Name**: The specific experiment within the lab associated with the bug.
  - **Type(s) of Issue(s)**: Categorization of the issue.
  - **Additional Information** (Optional): Any extra details provided by the user to help understand the issue.
  - **User Agent/Environment**: Information about the user's browser, operating system, or device.
  - **Experiment Link**: A direct link to the affected experiment.
  - **Virtual Lab User Email** (Optional): The user’s email address for follow-up, if provided.
  - **Screenshot** (Optional): Visual evidence of the issue, if attached.

### Step 3: Triage and Categorize the Bug

- Examine and quickly test the bug in the User Agent/ Environment (i.e. browser and operating system) mentioned in the bug report and then proceed with categorizing the bug.
- Assign one of the following labels to categorize the reported bug accurately:
  - **Bug**: A valid issue with the experiment or lab that needs resolution.
  - **Duplicate**: The issue is already reported and duplicates an existing entry.
  - **Resolved**: The issue has been fixed, and all necessary actions are completed.
  - **Invalid**: The issue is irrelevant due to reporting errors, insufficient data, or a misunderstanding of the scope.
  - **Test**: The issue was created for testing or experimentation purposes only.
  - **Inappropriate**: The issue contains offensive, vulgar, or demeaning content.
  - **In Progress**: The issue is currently being addressed.
  - **Not Reproducible**: The issue cannot be replicated based on the provided information.
  - **Question**: Additional clarification is needed from the Virtual Lab user (refer to Step 4.6).
  - **Documentation**: The issue pertains to documentation-related concerns.
  - **Enhancement**: The issue suggests new features or improvements beyond the current implementation.

- **Note:** Always assign the label **Bug** to an issue before proceeding with its resolution.

### Step 4. Fix the Bug

1. Label the bug as **In Progress** and assign it to yourself.
2. Identify the corresponding experiment and lab from the bug details.
3. If you lack access to the lab, search for the corresponding lab issue [here](https://github.com/virtual-labs/engineers-forum/issues)
4. Look for an issue titled **Experiment Repository Creation Request** for the corresponding lab. Open the issue and comment at the end, requesting access. Clearly include your GitHub ID and ask for access to the repository. For detailed guidance, refer to the **Requesting Access to Existing Repositories for New Developers** section [here](https://vlead.vlabs.ac.in/development/#onboarding-process)
5. Follow the [Virtual Lab Development process](https://github.com/virtual-labs/engineers-forum/blob/master/ph4/services/development-process.md) to fix the bug.
6. If the bug details lacks clarity and includes the virtual lab user’s email address, contact them for additional details using [this template](https://github.com/virtual-labs/engineers-forum/blob/master/ph4/services/bug-processing-guide.md#email-template-for-asking-the-questionclarification-from-the-user--).
7. Label the bug as **Question** if clarification is requested.
8. Close certain bug types with comments explaining the reason:
   - Invalid [Example](https://github.com/virtual-labs/bugs-virtual-labs/issues/1419)
   - Inappropriate [Example](https://github.com/virtual-labs/bugs-virtual-labs/issues/3329)
   - Duplicate [Example](https://github.com/virtual-labs/bugs-virtual-labs/issues/220)
   - Not Reproducible [Example](https://github.com/virtual-labs/bugs-virtual-labs/issues/626)
9. Add comments explaining your findings, coding decisions, or resolutions to maintain clarity.

### Step 5. Close the Bug

1. Ensure compliance with the [Virtual Lab Development process](https://github.com/virtual-labs/engineers-forum/blob/master/ph4/services/development-process.md).
2. After completing testing in the **testing branch** and verifying it on the GitHub Pages hosted link, merge the changes into the main branch.
3. Tag the commit, and raise a rehosting request following the [Virtual Labs hosting process](https://vlead.vlabs.ac.in/development/#hosting-process).
4. Once the experiment is live in production and has been verified, mark the bug as **Resolved** and close the bug.
5. Notify the user via email if their email address is provided, using [this template](https://github.com/virtual-labs/engineers-forum/blob/master/ph4/services/bug-processing-guide.md#email-template-for-notifying-the-user-about-the-resolved-bug-).
6. For duplicate bugs, notify the users using the [same email template](https://github.com/virtual-labs/engineers-forum/blob/master/ph4/services/bug-processing-guide.md#email-template-for-notifying-the-user-about-the-resolved-bug-).

### Do's and Don'ts

**_Do’s_**

- Assign the bug to yourself while working on it.
- Comment clearly when assigning labels, especially for _Invalid_, _Duplicate_, _Inappropriate_, or _Not Reproducible_.
- Notify the Virtual Lab user who filed the bug, after a bug is fixed using the provided email templates.

**_Don’ts_**

- Never label a bug _Resolved_ without testing the fix on the latest hosted link.
- Never close a bug without providing the reason in comment.

#### Email Template for asking the question/clarification from the user -

> Subject: Follow-Up on [BUG REPORT] `<experiment-name>` #`<bug-number>`
>
> Dear `<user-name>`,
>
> Thank you for taking the time to report the bug in the virtual labs experiment - `<experiment-name>`. Your feedback is invaluable in helping us improve and provide a better experience for all users.
>
> We wanted to let you know that we are actively working on addressing the issue you reported. Here is the link to the issue you created: https://github.com/virtual-labs/bugs-virtual-labs/issues/bug-number
>
> However, we’re currently facing some challenges in reproducing the problem. The attached image and additional details lack the context needed to fully understand the situation.
>
> Could you kindly provide more specific information or explain the image further? Your input would greatly assist us in identifying and resolving the issue as quickly as possible.
>
> Thank you again for your valuable contribution. We appreciate your patience and look forward to your reply.
>
> Best regards,
>
> `<developer-name>`

#### Email Template for notifying the user about the resolved bug-

> Subject: Follow-Up on [BUG REPORT] `<experiment-name>` #`<bug-number>`
>
> Dear `<user-name>`,
>
> Thank you for taking the time to report the bug in the Virtual Labs. Your feedback has been invaluable in helping us improve and provide a better experience for all users.
>
> We’re pleased to inform you that the issue you reported has been resolved. Here is the link to the issue you created: https://github.com/virtual-labs/bugs-virtual-labs/issues/bug-number
>
> We deeply appreciate your participation and effort in bringing this to our attention. If you encounter any further issues or have additional suggestions, please don’t hesitate to reach out to us.
>
> Thank you once again for your contribution to enhancing our system.
>
> Best regards,
>
> `<developer-name>`

## Conclusion

This document provides a structured workflow for handling bug reports, ensuring clear communication, efficient resolution, and maintaining high-quality labs in the Virtual Labs ecosystem.
