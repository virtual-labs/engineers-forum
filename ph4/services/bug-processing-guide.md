# Lifecycle of the Bug
## 1. Bug Creation
- A user reports a bug using the bug reporting tool.
- The bug is logged at [GitHub Bug Tracker](https://github.com/virtual-labs/bugs-virtual-labs/).
- The bug is labeled with an *Institute Label* corresponding to the lab’s developing institute.

## 2. Bug Details
Each bug includes the following information:
- Lab Name
- Experiment Name
- Type(s) of Issue(s)
- Additional Info (Optional)
- User Agent/Environment
- Experiment Link
- Screenshot (Optional)

## 3. Bug Categorization
The developer analyzes the bug based on the provided details and labels it as one of the following:
- **Duplicate** : The issue duplicates an existing one.
- **Resolved** : The issue has been fixed and necessary actions are completed.
- **Invalid** : The issue is irrelevant due to reporting errors, insufficient data, or misunderstanding of the scope.
- **Test** : The issue was created solely for testing or experimentation.
- **Inappropriate** : The issue contains offensive, irrelevant, or non-compliant comments.
- **In Progress** : The issue is currently being worked on.
- **Not Reproducible** : The issue cannot be replicated based on the provided information.
- **Question** : More clarification is needed from the user.
- **Documentation** : The issue is related to documentation.
- **Enhancement** : The issue requests new features beyond the current implementation.

## 4. Closing Bugs
Certain bug types should be closed with a comment explaining the reason:
- Invalid
- Inappropriate
- Duplicate
- Not Reproducible
For examples, refer to [Issue #220](https://github.com/virtual-labs/bugs-virtual-labs/issues/220) and [Issue #278](https://github.com/virtual-labs/bugs-virtual-labs/issues/278).

## 5. Status Updates
- If you’re working on a bug, label it as In Progress.
- Once a bug is fixed, label it as Resolved before closing it.

## 6. Commenting Guidelines
- Clearly comment on the bug when assigning a label.
- Never close a bug without adding a comment explaining the reason.

## 7. Contacting the User
- If the bug report lacks clarity and includes the user’s email address, contact them for further details.
- Notify the user when the bug has been fixed. Use the email templates provided for user communication.

### Email Template for asking the question/clarification from the user -

> Subject: Follow-Up on [BUG REPORT] <experiment-name> #<bug-number>
> 
> Dear `<user-name>`,
>  
> Thank you for taking the time to report the bug in the virtual labs experiment - `<experiment-name>`. Your feedback  is invaluable in helping us improve and provide a better experience for all users.
> 
> We wanted to let you know that we are actively working on addressing the issue you reported. Here is the link to the issue you created: https://github.com/virtual-labs/bugs-virtual-labs/issues/`<bug-number>`
> 
> However, we’re currently facing some challenges in reproducing the problem. The attached image and additional details lack the context needed to fully understand the situation.
> 
> Could you kindly provide more specific information or explain the image further? Your input would greatly assist us in identifying and resolving the issue as quickly as possible.
> 
> Thank you again for your valuable contribution. We appreciate your patience and look forward to your reply.
> 
> Best regards,
> `<developer-name>`


### Email Template for notifying the user about the resolved bug-

> Subject: Follow-Up on [BUG REPORT] <experiment-name> #<bug-number>
> Dear `<user-name>`,
> Thank you for taking the time to report the bug in the Virtual Labs. Your feedback has been invaluable in helping us improve and provide a better experience for all users.
> We’re pleased to inform you that the issue you reported has been resolved. Here is the link to the issue you created: https://github.com/virtual-labs/bugs-virtual-labs/issues/`<bug-number>`
> We deeply appreciate your participation and effort in bringing this to our attention. If you encounter any further issues or have additional suggestions, please don’t hesitate to reach out to us.
> Thank you once again for your contribution to enhancing our system.
> Best regards,
> `<developer-name>`

