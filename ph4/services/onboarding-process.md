 # Virtual Labs Onboarding Process

## Introduction

Virtual Labs is a mission-driven project under the Ministry of Education (MoE) aimed at providing laboratory learning experiences to students lacking adequate lab infrastructure. With over 150 labs developed by various consortium institutes, the project follows a streamlined software development life cycle to ensure high-quality labs. This document outlines the onboarding process for developers within the Virtual Labs project.

## Purpose

This document details the experiment onboarding process for lab developers requesting their lab's hosting on the central cloud. It specifies the steps involved in the onboarding process.

## Audience

The target audience for this document includes all lab developers and owners seeking to develop new experiments.

## Definitions

### Onboarding
Onboarding marks the start of software development for an approved lab, with the CPE team creating a Git repository for each experiment.

### GitHub handle
A GitHub handle is a public reference that can be traced back to all public (and sometimes private) activities done on GitHub.

## Onboarding

### Prerequisites

The onboarding process requires:

1. An approved lab proposal in PDF format - [reference](https://drive.google.com/file/d/1yjLMM96kxYnQ4_DiDOwFhdqLG0--0Z1P/view?usp=drive_link).
2. Primary GitHub handle - It must be a university-based GitHub handle.
3. Secondary GitHub handle - It must be the primary account of the contributing Developers.

### Process

**Step 1**

New developers raise an [issue](https://github.com/virtual-labs/engineers-forum/issues/new?assignees=&labels=Phase-3%2C+create+experiment+repos&template=experiment-repository-creation-request.md&title=Experiment+Repository+Creation+Request+for+%3Cfill+the+lab+name+here%3E) to request the creation of experiment repositories for the lab.

**Step 2**

Developers fill in the requested information on the issue and attach the lab proposal [sample](https://github.com/virtual-labs/engineers-forum/files/5985232/Java.Proposal.pdf).

**Step 3**

The Central Platform Engineering (CPE), IIITH team creates experiment repositories for each experiment in the proposal on GitHub and shares the links to the created repositories on the same issue. [sample](https://github.com/virtual-labs/engineers-forum/issues/673#issuecomment-779564300)

**Step 4**

Developers populate the dev branches of the created repositories with the source code of the experiments and unit test the experiments locally. They do not delete the gh-pages branch, as it is required for automatically deploying the experiment along with UI on GitHub pages for testing the complete experiment. They also do not delete the `.github` directory and the `LICENSE` file.

## Conclusion

For detailed information about the development process and the next steps, please refer to this [document](https://github.com/virtual-labs/engineers-forum/blob/master/ph4/services/development-processmd).
