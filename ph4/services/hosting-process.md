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
The responsibility of testing the deployments lies with the repository owner. The CPE team provides the deployment link, while the repository owner ensures the deployed hosting unit works as expected.


## Hosting

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
3. [Tag](https://github.com/virtual-labs/engineers-forum/edit/master/ph4/services/hosting-process.md?plain=94#L101) to be hosted
4. Contact Person details
5. Approved Review (PDF attachment)

The CPE team builds the experiments with the common Virtual Labs UI and deploys them to the central cloud. The team adds the hosting link to the request issue, and the requester verifies it.

### Lifecycle of a Hosting Request

1. The requester raises a hosting request issue or requests rehosting.
2. Upon successful hosting, the team adds the link to the issue.
3. On failure, the team responds to the requester, who then fixes the issue and requests rehosting.
4. The requester verifies the hosted link and approves or requests a revert.
5. Approval from the requester is required for sharing the hosted URL.

## FAQ

**Why use the Hosting Service?**

The Hosting Service provides high-availability, high-performance deployment without spending extra resources. It also includes additional services like analytics.

**Does the Hosting Service improve website performance?**

Yes, the CPE team works continuously to improve performance based on analytics data.

**Does the CPE team help improve my Lab performance?**

The CPE team improves infrastructure but does not alter your code.

**Does Hosting Service add UI to my webpages?**

The CPE team does not add UI elements but provides a uniform UI framework for experiments. Developers should conform to this framework.
