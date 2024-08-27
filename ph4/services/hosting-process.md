# Virtual Labs Hosting Process

## Introduction

Virtual Labs is a mission-mode project under the Ministry of Education (MoE) aimed at providing laboratory learning experiences.  The objective of this project is to provide a laboratory learning experience to students who do not have access to adequate laboratory infrastructure. Currently, there are 150+ labs developed by various institutes in the consortium. This document outlines the hosting process for the Virtual Labs project.

## Purpose

The document defines the hosting process for lab developers requesting to host their labs on the central cloud. It details the roles and responsibilities involved in the hosting process.

## Motivation

A structured hosting process ensures consistent user experience and effective reporting.

## Audience

The target audience for this document comprises all lab developers and owners who want to avail the hosting service provided by the Central Platform Engineering (CPE), IIITH team.

## Definitions

### Hosting Unit
A hosting unit is the code base/repository hosted in its entirety during the hosting process. It corresponds to one public repository and could be a standalone experiment or a lab with a set of related experiments.

### Hosting
Hosting is a service provided by the CPE team to publish the developed lab/experiments on a central cloud.

### Requester
A repository owner or developer who raises a hosting request.

### Tags
The repository owner is responsible for tagging each merge to the main branch, following [Semantic Versioning](https://semver.org/). All Virtual Labs hosting requests should specify a tag.

### Testing
The responsibility for testing the deployments lies with the repository owner. The CPE team provides the deployment link, while the repository owner ensures the deployed hosting unit works as expected.


## Hosting Process

### Objectives

Hosting includes:
1. Providing infrastructure to serve the lab/experiments.
2. Ensuring round-the-clock availability.
3. Meeting infrastructure performance criteria.

### Pre-requisites

Once the experiment is approved, the developer merges the testing branch with the main branch and creates a tag on the main branch. The experiment is then ready for public availability.

### Process

After completing all experiments listed in the proposal, the developer raises a [Lab/Experiment Hosting Request issue](https://github.com/virtual-labs/engineers-forum/issues/new?assignees=&labels=Phase-3&template=lab-experiment-s--hosting-request.md&title=Lab%2FExperiment+Hosting+Request+for++) on the Engineers’ Forum repository with:
1. Experiment Name
2. Experiment Repository URL
3. [Tag](https://github.com/virtual-labs/engineers-forum/blob/master/ph4/services/development-process.md#step-5-tagging-the-release) to be hosted
4. Contact Person details
5. Approved Review (PDF attachment)

The CPE team builds the experiments with the common Virtual Labs UI and deploys them to the central cloud. The team adds the hosting link to the request issue, and the requester verifies it.

### Lifecycle of a Hosting Request

**Step 1:**  
The requester initiates a hosting or rehosting request by raising an issue.

**Step 2:**  
Once hosting is successful, the team updates the issue with the hosted link.

**Step 3:**  
If hosting fails, the CPE team notifies the requester, who then addresses the issue and submits a rehosting request.

**Step 4:**  
The CPE team rehosts the experiment and requests the requester to test the hosted link.

**Step 5:**  
The requester tests the hosted link, and then either approves it or requests changes.

**Step 6:**  
Upon approval from the requester, the hosted URL is shared with IITD for final hosting on the Virtual Labs website.

**Step 7:**  
After receiving confirmation from IITD, the experiment is made accessible to users on the Virtual Labs website.


## FAQ

**Why use the Hosting Service?**

The Hosting Service provides high-availability, high-performance deployment without spending extra resources. It also includes additional services like analytics.

**Does the Hosting Service improve website performance?**

Yes, the CPE team works continuously to improve performance based on analytics data.

**Does the CPE team help improve my Lab performance?**

The CPE team improves infrastructure but does not alter your code.

**Does Hosting Service add UI to my webpages?**

The CPE team does not add UI elements but provides a uniform UI framework for experiments. Developers should conform to this framework.
