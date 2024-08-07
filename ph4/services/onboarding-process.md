# Virtual Labs Onboarding Process

## Introduction

Virtual Labs is a mission-driven project under the Ministry of Education (MoE) aimed at providing laboratory learning experiences to students lacking adequate lab infrastructure. With over 150 labs developed by various consortium institutes, the project follows a streamlined software development life cycle to ensure high-quality labs. This document outlines the onboarding process for developers within the Virtual Labs project.

## Purpose

This document details the experiment onboarding process for lab developers requesting their lab's hosting on the central cloud. It specifies the roles and responsibilities of all parties involved in the onboarding process.

## Motivation

A well-defined onboarding process ensures a consistent user experience and allows experiment authors to focus on content creation. Consolidated information regarding all deployments also facilitates effective reporting.

## Audience

The target audience for this document includes all lab developers and owners seeking to utilize the hosting service provided by the Central Platform Engineering (CPE) team at IIITH.

## Definitions

### Onboarding
Onboarding marks the start of software development for an approved lab, with the CPE team creating a Git repository for each experiment.

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

## Onboarding

### Objectives
Provide centralized organization and uniform repository structure.

### Prerequisites

The onboarding process requires:
1. An approved lab proposal in PDF format.
2. Primary GitHub handle.
3. Secondary GitHub handle.

### Process

Onboarding Process for New Developers

1. **Provide GitHub Handles:**
   - New developer submits primary and secondary GitHub handles to the CPE team.

2. **CPE Team Actions:**
   - CPE team creates a Git repository for each approved experiment lab.
   - Grants repository access to the developer.

3. **Developer Actions:**
   - Developer raises an [issue](https://github.com/virtual-labs/engineers-forum/issues/new?assignees=&labels=Phase-3%2C+create+experiment+repos&template=experiment-repository-creation-request.md&title=Experiment+Repository+Creation+Request+for+%3Cfill+the+lab+name+here%3E) on the engineers-forum repository under the Virtual Labs organization.
   - Attaches the PDF of the approved proposal to the issue.

4. **Repository URLs Sharing:**
   - CPE team creates the Git repositories.
   - Shares the repository URLs on the same issue.

