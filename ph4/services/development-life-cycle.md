# Virtual Labs Development Lifecycle

## Introduction

This document outlines the experiment development life cycle for developers in the Virtual Labs project, aiming to ensure the creation of high-quality labs.
# Experiment Life Cycle

## Development

*Note: This section is for completeness and does not fall under CPE team responsibilities.*

After onboarding, the lab developer can begin developing and testing the approved experiments. The developer checks the source code into the experiment repository and merges it to the main branch. Developers should not delete the gh-pages branch or .github directory.

A sample experiment codebase is available here, and the deployed testing URL can be found here. Developers will receive an email regarding the deployment's success or failure.

## Experiment Customization and Inclusion

To include or customize an experiment, follow these steps:

1. **Update experiment.json:** Add any new items or updates to the side menu or simulation by modifying the experiment.json file.
2. **Fill Out Instructions:** Ensure all instructions in the side menu are complete and properly linked. For more details about the side menu, please refer to this document.
3. **Populate Existing Files:** Once you have the repository, make sure to populate the existing files as required. Avoid adding unnecessary files.

## Basic Requirements for the Experiments

- All experiments must work on HTTPS.
- Follow responsive design principles.
- Experiments should be static.
- Average page load size should be below 2MB, with no page exceeding 5MB.
- Average page load time should be below 1.5 seconds on a fast 3G connection, with no page exceeding 3 seconds.

## Experiment Development Strategy

### Static Experiments

- Offer high performance, security, and low cost.
- The CPE team provides a framework for static experiments, including uniform UI, a styling library, analytics, and performance tools.

### Experiments Requiring Backend

- Built using JavaScript, Python, etc., with higher hosting and maintenance costs.
- Developers are responsible for UI conformity, analytics, containerization, and updates.

Developers should consult the CPE team to determine if a backend is necessary.
