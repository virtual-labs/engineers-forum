# Virtual Labs Onboarding Process

## Introduction

Virtual Labs is a mission-driven project under the Ministry of Education (MoE) that aims to provide laboratory learning experiences to students who lack adequate lab infrastructure. With over 150 labs developed by various consortium institutes, the project follows a streamlined software development life cycle to ensure the delivery of high-quality labs. This document outlines the onboarding process for developers involved in the Virtual Labs project.

## Purpose

This document details the process for onboarding lab developers requesting to host their labs on the central cloud. It specifies the steps required for successful onboarding.

## Audience

The intended audience for this document includes all lab developers and owners who are interested in developing new experiments.

## Definitions

### Onboarding
Onboarding initiates the software development process for an approved lab, with the Central Platform Engineering (CPE) team responsible for creating a Git repository for each experiment.

### GitHub Handle
A GitHub handle is a unique identifier associated with a user’s public (and sometimes private) activities on GitHub.

## Onboarding

### Prerequisites

Before beginning the onboarding process, the following prerequisites must be met:

1. An Approved lab proposal in PDF format - [reference](https://drive.google.com/file/d/1yjLMM96kxYnQ4_DiDOwFhdqLG0--0Z1P/view?usp=drive_link).
2. One Primary GitHub handle - This should be a university-affiliated GitHub account.
3. Secondary GitHub handles - This should be the GitHub accounts used by the contributing developers.

### Onboarding Process 
#### Requesting New Repository Creation and Access for New Developers

**Step 1:**  
Raise an [Experiment Repository Creation Request](https://github.com/virtual-labs/engineers-forum/issues/new?assignees=&labels=Phase-3%2C+create+experiment+repos&template=experiment-repository-creation-request.md&title=Experiment+Repository+Creation+Request+for+%3Cfill+the+lab+name+here%3E) to request the creation of experiment repositories for the lab.

**Step 2:**  
Provide the following information in the above created issue on the Engineers’ Forum repository:
 1. Coordinating Institute: Your institute name
 2. Approver’s Name: Name of the approver
 3. Approved Proposal: Upload the PDF of the approved proposal
 4. Primary GitHub Handle Details: Provide the Primary GitHub handle details to which write permissions need to be given and notifications need to be sent. This should be a university affliated handle. 
    
     a. Name: Provide the Name that the Primary GitHub Handle is associated with

     b. GitHub Handle: Provide the email id that the Primary GitHub Handle is associated with

     c. Email id: Provide the email id that the Primary GitHub Handle is associated with
    
 5. Secondary GitHub Handle Details: Provide the additional GitHub handle(s) to which write permissions need to be given

     a. Name: Provide the Name that the Secondary GitHub Handle is associated with
    
     b. GitHub Handle: Provide the email id that the Secondary GitHub Handle is associated with
    
     c. Email id: Provide the email id that the Secondary GitHub Handle is associated with

**Step 3:**  
The CPE team at IIITH will create experiment repositories for each experiment listed in the proposal on GitHub. The links to the repositories will be shared in the same issue thread. [sample](https://github.com/virtual-labs/engineers-forum/issues/673#issuecomment-779564300). Once this process is complete, developers will be notified in form of a comment in the above created issue. 

**Step 4:**  
Developers can now begin populating the development branches of these repositories with the source code for the experiments.

#### Requesting Access to Existing Repositories for New Developers
**Step 1:**  
Navigate to the [GitHub repository](https://github.com/virtual-labs/engineers-forum/issues). Use the search bar to locate the experiment name, and then click on the corresponding issue.

**Step 2:**  
Provide the following information in the issue as comments:
 1. Primary GitHub Handle Details: Provide the Primary GitHub handle details to which write permissions need to be given and notifications need to be sent. This should be a university-affiliated handle. 
    
     a. Name: Provide the Name that the Primary GitHub Handle is associated with

     b. GitHub Handle: Provide the email id that the Primary GitHub Handle is associated with

     c. Email id: Provide the email id that the Primary GitHub Handle is associated with
    
 2. Secondary GitHub Handle Details: Provide the additional GitHub handle(s) to which write permissions need to be given
 
     a. Name: Provide the Name that the Secondary GitHub Handle is associated with
   
     b. GitHub Handle: Provide the email id that the Secondary GitHub Handle is associated with
    
     c. Email id: Provide the email id that the Secondary GitHub Handle is associated with

**Step 3:**  
The CPE team at IIITH will share the links to the experiment repositories as comments in the same GitHub issue thread for each experiment listed in the proposal. You can refer to this [sample](https://github.com/virtual-labs/engineers-forum/issues/673#issuecomment-779564300). 

**Step 4:**  
Once the access for the repositories are shared, the developers can now begin populating the development branches of these repositories with the source code for the experiments.


## Conclusion

This document provides a comprehensive guide to the onboarding process. Upon completing these four steps, developers can proceed to the development phase. For detailed guidance on the next steps, please refer to this [document](https://github.com/virtual-labs/engineers-forum/blob/master/ph4/services/development-process.md).

## Conclusion

This document provides a comprehensive guide to the onboarding process. Upon completing these four steps, developers can proceed to the development phase. For detailed guidance on the next steps, please refer to this [document](https://github.com/virtual-labs/engineers-forum/blob/master/ph4/services/development-process.md).



## FAQ

**Can I change the Primary and Secondary GitHub Handle after submitting the experiment repository creation request?**

Yes, the primary GitHub handle can be changed. However, it is recommended to maintain a consistent university-specific handle for Virtual Labs development. Secondary handles are flexible and can be updated as needed.
