# Virtual Labs Hosting Process

## Introduction

**Virtual Labs** is a mission-mode project under the Ministry of Education (MoE), Government of India, designed to provide laboratory learning experiences to students who may lack access to adequate laboratory infrastructure. Currently, there are over 150 labs developed by various institutes within the consortium. This document outlines the standardized hosting process for the Virtual Labs project.

## Purpose

This document defines the hosting process for lab developers requesting to host their labs on the central cloud. It details the roles and responsibilities involved in ensuring a smooth and consistent hosting experience.

## Motivation

A structured hosting process helps maintain a consistent user experience, efficient reporting, and reliability for users accessing the labs.

## Audience

The target audience for this document includes all lab developers and owners seeking hosting services provided by the Central Platform Engineering (CPE) team at IIIT Hyderabad.

## Definitions

### Hosting Unit
A **hosting unit** is the codebase or repository that is hosted in its entirety during the hosting process. It corresponds to one public repository and could be a standalone experiment or a lab containing multiple related experiments.

### Hosting
**Hosting** is a service provided by the CPE team to publish the developed lab or experiments on a central cloud infrastructure.

### Requester
A **requester** is the repository owner or developer who raises a hosting request.

### Tags
The repository owner is responsible for tagging each merge to the main branch, following [Semantic Versioning](https://semver.org/). All Virtual Labs hosting requests must specify a tag for version control.

### Testing
The responsibility for testing the deployed lab/experiment lies with the repository owner. The CPE team provides the deployment link, and the repository owner verifies that the hosted unit works as expected.

## Hosting Process

### Objectives

The hosting process aims to:
1. Provide infrastructure to serve the lab or experiments.
2. Ensure 24/7 availability of hosted experiments.
3. Meet specified infrastructure performance criteria to maintain a seamless user experience.

### Pre-requisites

Before submitting a hosting request:
1. The developer must ensure that the experiment has been approved.
2. Merge the **testing** branch with the **main** branch.
3. Create a **tag** on the main branch, indicating readiness for public availability.

### Process

Once all experiments listed in the proposal are complete, the developer should raise a Lab/Experiment Hosting Request issue on the Engineers’ Forum repository. This can be done by filling out [this form](https://github.com/virtual-labs/engineers-forum/issues/new?assignees=&labels=Phase-3&projects=&template=lab-experiments-hosting-request.md&title=Lab%2FExperiment+Hosting+Request+for++) with the following details:
1. **Experiment Name**
2. **Experiment Repository URL**
3. **Tag** to be hosted (following [tagging guidelines](https://github.com/virtual-labs/engineers-forum/blob/master/ph4/services/development-process.md#step-5-tagging-the-release) )
4. **Contact Person** details
5. **Approved Review Document** (PDF attachment)

Upon receiving the request, the CPE team will:
1. Build the experiments with the common Virtual Labs UI.
2. Deploy the experiments to the central cloud.
3. Update the request issue with the hosting link.

The requester is then responsible for verifying the deployment and confirming that it functions as expected.

### Lifecycle of a Hosting Request

**Step 1: Request Initiation**  
The requester initiates a hosting or rehosting request by raising an issue. For rehosting, the institution requesting rehosting should visit [this link](https://github.com/virtual-labs/engineers-forum/issues), locate the hosting issue corresponding to the lab they wish to rehost, and comment with details of the experiment(s) requiring rehosting.

**Step 2: Hosting Success Update**  
If hosting is successful, the CPE team updates the issue with the hosted link.

**Step 3: Hosting Failure Notification**  
If hosting fails, the CPE team notifies the requester of the issue. The requester then addresses the issue and submits a rehosting request as part of the same issue.

**Step 4: Rehosting and Testing Request**  
The CPE team rehosts the experiment and requests the requester to test the new hosted link.

**Step 5: Requester Testing**  
The requester tests the hosted link. They then either approve the hosting or request further changes.

**Step 6: Final Approval and Sharing**  
Once approved by the requester, the hosted URL is shared with IIT Delhi (IITD) for final hosting on the Virtual Labs website.

**Step 7: Experiment Accessibility**  
Upon confirmation from IITD, the experiment is made accessible to users on the Virtual Labs website.


## FAQ

**Why should I use the Hosting Service?**

The Hosting Service provides a high-availability, high-performance deployment environment for your lab or experiment, without requiring additional resources. It also includes supplementary services, such as analytics, to help you monitor usage and performance.

**Will the Hosting Service improve website performance?**

Yes, the CPE team actively monitors and optimizes performance based on analytics data to ensure a smooth user experience.

**Can the CPE team help improve my lab’s performance?**

The CPE team is responsible for optimizing the hosting infrastructure. However, it does not modify or optimize the lab’s code itself. Performance improvements to the code are the developer’s responsibility.

**Does the Hosting Service add UI elements to my webpages?**

The CPE team does not add individual UI elements to your pages. However, it provides a uniform UI framework for all experiments. Developers are encouraged to adhere to this framework to maintain consistency across Virtual Labs.
