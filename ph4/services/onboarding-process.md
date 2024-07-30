# Virtual Labs On-Boarding Process

## Introduction

Virtual Labs is a mission-driven project under the Ministry of Education (MoE) aimed at providing laboratory learning experiences to students lacking adequate lab infrastructure. With over 150 labs developed by various consortium institutes, the project follows a streamlined software development life cycle to ensure high-quality labs. This document outlines the onboarding process for developers within the Virtual Labs project.

## Purpose

This document details the experiment onboarding process for lab developers requesting their lab's hosting on the central cloud. It specifies the roles and responsibilities of all parties involved in the onboarding process.

## Motivation

A well-defined onboarding process ensures a consistent user experience and allows experiment authors to focus on content creation. Consolidated information regarding all deployments also facilitates effective reporting.

## Audience

The target audience for this document includes all lab developers and owners seeking to utilize the hosting service provided by the Central Platform Engineering (CPE) team at IIITH.

## Definitions

### On-boarding
On-boarding marks the start of software development for an approved lab, with the CPE team creating a Git repository for each experiment.

### Hosting Unit
A hosting unit is the codebase/repository hosted in its entirety during the hosting process. It can be a standalone experiment or a lab comprising multiple related experiments.

### Hosting
Hosting is a service provided by the CPE team to publish the developed lab/experiments on a central cloud.

### Repository Owner
The primary owner of a repository is responsible for all code within it and has final approval authority for hosting requests. They must ensure the main branch contains only the code to be hosted.

### Requester
The repository owner or developer who submits a hosting request.

### Tags
The repository owner must tag each merge to the main branch following [Semantic Versioning](https://semver.org/). All hosting requests should specify a tag.

### Testing
The repository owner is responsible for testing deployments. The CPE team provides the deployment link, and the repository owner ensures the deployed hosting unit functions as expected.

## On-boarding

### Objectives
Provide centralized organization and uniform repository structure.

### Pre-requisites

The onboarding process requires:
1. An approved lab proposal in PDF format.
2. Primary Repository Owner details.

### Process

1. The CPE team creates a Git repository for each experiment of the approved lab.
2. The lab developer raises an [issue](https://github.com/virtual-labs/engineers-forum/issues/new?assignees=&labels=Phase-3%2C+create+experiment+repos&template=experiment-repository-creation-request.md&title=Experiment+Repository+Creation+Request+for+%3Cfill+the+lab+name+here%3E) on the engineers-forum repository under the Virtual Labs organization on GitHub, attaching the PDF of the approved proposal.
3. The CPE team creates the Git repositories and shares the URLs on the same issue.

#### Experiment Repository Structure

Each experiment repository contains four default branches:

1. **dev**: For development and unit testing.
2. **testing**: For end-to-end testing, deployed automatically via CI/CD.
3. **gh-pages**: Automatically created during testing branch deployment; should not be tampered with.
4. **main**: Contains production artifacts; only code and documents merged from the testing branch are added.

The initial structure and hierarchy of each default branch include:

<pre>
├── experiment
│   ├── images
│   │   └── README.md
│   ├── simulation
│   │   ├── css
│   │   │   ├── main.css
│   │   │   └── README.md
│   │   ├── images
│   │   │   └── README.md
│   │   ├── js
│   │   │   ├── main.js
│   │   │   └── README.md
│   │   └── index.html
│   ├── aim.md
│   ├── experiment-name.md
│   ├── posttest.js
│   ├── pretest.js
│   ├── procedure.md
│   ├── README.md
│   ├── references.md
│   └── theory.md
├── pedagogy
│   ├── images
│   │   └── README.md
│   └── README.md
├── storyboard
│   ├── flowchart
│   │   └── README.md
│   ├── mindmap
│   │   └── README.md
│   ├── storyboard
│   │   └── README.md
│   └── README.md
├── LICENSE
└── README.md
</pre>

## Development

**Note:** This section is for completeness and does not fall under CPE team responsibilities.

After onboarding, the lab developer can begin developing and testing the approved experiments. The developer checks the source code into the experiment repository and merges it to the main branch. Developers should not delete the gh-pages branch or .github directory.

A sample experiment codebase is available [here](https://github.com/virtual-labs/ph3-exp-dev-process/tree/main/sample/experiment), and the deployed testing URL can be found [here](https://virtual-labs.github.io/ph3-exp-dev-process/). Developers will receive an email regarding the deployment success or failure.

### Basic Requirements for the Experiments

1. All experiments must work on HTTPS.
2. Follow responsive design principles.
3. Experiments should be static, with exceptions for server-side components.
4. Average page load size should be below 2MB, with no page exceeding 5MB.
5. Average page load time should be below 1.5 seconds on a fast 3G connection, with no page exceeding 3 seconds.

### Experiment Development Strategy

**Static Experiments**
- Offer high performance, security, and low cost.
- The CPE team provides a framework for static experiments, including uniform UI, a styling library, analytics, and performance tools.

**Experiments Requiring Backend**
- Built using JavaScript, Python, etc., with higher hosting and maintenance costs.
- Developers are responsible for UI conformity, analytics, containerization, and updates.

Developers should consult the CPE team to determine if a backend is necessary.
