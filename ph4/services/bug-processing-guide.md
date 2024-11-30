# Virtual Labs Bug Processing

## Introduction

This document explains the bug processing workflow for developers in the Virtual Labs project. It aims to ensure the timely maintenance of high-quality labs by standardizing the bug documentation and fixing process.

## Purpose

The purpose of this document is to detail the steps involved in documenting and fixing bugs reported for experiments. It serves as a guide for lab developers to address issues efficiently.

## Audience

This document is intended for all lab developers and owners working to fix experiment bugs within the Virtual Labs ecosystem.

## Lifecycle of the Bug

### Step 1. Looking for a Bug
- A Virtual Lab User reports a bug using the **bug reporting tool**.
- The bug is logged at [GitHub Bug Tracker](https://github.com/virtual-labs/bugs-virtual-labs/issues).
- The bug is labeled with an **Institute Label** corresponding to the lab’s developing institute.
- Developers can filter the bugs by their institute to view relevant issues.

### Step 2. Understanding Bug details
Each bug includes the following information:
- Lab Name
- Experiment Name
- Type(s) of Issue(s)
- Additional Info (Optional)
- User Agent/Environment
- Experiment Link
- Email (Optional)
- Screenshot (Optional)

### Step 3. Categorizing the Bug
The developer analyzes the bug and assigns one of the following labels:
- **Bug** : The issue that provides a valid problem with the experiment/the lab.
- **Duplicate** : The issue duplicates an existing one.
- **Resolved** : The issue has been fixed and necessary actions are completed.
- **Invalid** : The issue is irrelevant due to reporting errors, insufficient data, or misunderstanding of the scope.
- **Test** : The issue was created solely for testing or experimentation.
- **Inappropriate** : The issue contains offensive, irrelevant, or non-compliant comments.
- **In Progress** : The issue is currently being worked on.
- **Not Reproducible** : The issue cannot be replicated based on the provided information.
- **Question** : More clarification is needed from the virtual lab user. (refer to step 4.6)
- **Documentation** : The issue is related to documentation.
- **Enhancement** : The issue requests new features beyond the current implementation.
Note: Assign the bug as **Bug** before proceeding for fixing the bug.

### Step 4. Fixing the Bug
1. Label the bug as **In Progress** and assign it to yourself.
2. Identify the corresponding experiment and lab from the bug details.
3. If you lack access to the lab, find the lab creation request on [virtual-labs/engineers-forum](https://github.com/virtual-labs/engineers-forum/issues) and request access by commenting.
4. Follow the [Virtual Lab Development process](https://github.com/virtual-labs/engineers-forum/blob/master/ph4/services/development-process.md) to fix the bug.
5. If the bug details lacks clarity and includes the virtual lab user’s email address, contact them for mroe details using [this template](https://github.com/virtual-labs/engineers-forum/blob/master/ph4/services/bug-processing-guide.md#email-template-for-asking-the-questionclarification-from-the-user--).
6. Label the bug as **Question** if clarification is requested.
7. Close certain bug types with comments explaining the reason:
    - Invalid [Example](https://github.com/virtual-labs/bugs-virtual-labs/issues/1419)
    - Inappropriate [Example](https://github.com/virtual-labs/bugs-virtual-labs/issues/3329)
    - Duplicate [Example](https://github.com/virtual-labs/bugs-virtual-labs/issues/220)
    - Not Reproducible [Example](https://github.com/virtual-labs/bugs-virtual-labs/issues/626)
8. Add comments explaining your findings, coding decisions, or resolutions to maintain clarity.

### Step 5. Closing the Bug
1. Ensure compliance with the [Virtual Lab Development process](https://github.com/virtual-labs/engineers-forum/blob/master/ph4/services/development-process.md). 
2. Once testing is complete in the **testing branch**, request hosting for the corresponding experiment.
3. After verifying the bug fix on the hosted link, mark the bug as **Resolved**.
4. Once the experiment is in production and verified, close the bug.
5. Notify the user if their email is provided, using [this template](https://github.com/virtual-labs/engineers-forum/blob/master/ph4/services/bug-processing-guide.md#email-template-for-notifying-the-user-about-the-resolved-bug-).
6. For duplicate bugs, notify the users using the [same email template](https://github.com/virtual-labs/engineers-forum/blob/master/ph4/services/bug-processing-guide.md#email-template-for-notifying-the-user-about-the-resolved-bug-).

### Do's and Don'ts
***Do’s***
- Assign the bug to yourself while working on it.
- Comment clearly when assigning labels, especially for *Invalid*, *Duplicate*, *Inappropriate*, or *Not Reproducible*.
- Notify the virtual lab users who filed the bug, after a bug is fixed using the provided email templates.

***Don’ts***
- Never label a bug *Resolved* without testing the fix on the latest hosted link.
- Never close a bug without providing the reason in comment.

#### Email Template for asking the question/clarification from the user -

> Subject: Follow-Up on [BUG REPORT] `<experiment-name>` #`<bug-number>`
> 
> Dear `<user-name>`,
>  
> Thank you for taking the time to report the bug in the virtual labs experiment - `<experiment-name>`. Your feedback  is invaluable in helping us improve and provide a better experience for all users.
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