# Virtual Labs Development Process

## Introduction

This document outlines the experiment development life cycle for developers in the Virtual Labs project, aiming to ensure the creation of high-quality labs.

## Purpose

This document details the experiment development process for lab developers. It specifies the steps involved.

## Audience

The target audience for this document includes all lab developers and owners seeking to develop new experiments.

# Experiment Life Cycle

## Preparation for Development

### Verify Repositories

1. **Check Repository Creation:** Ensure all required repositories are created and accessible.

### Development Tools

To start development, use the following tools:
1. **Web VS Extension:** Utilize the Web VS extension for online development.
2. **VS Extension:** Use the VS extension for local development.

The entire workflow is built into these two tools. Follow the provided links to access and install them:
- [VS Extension](https://github.com/virtual-labs/tool-vscode-plugin)
- [Web VS Extension](https://github.com/virtual-labs/tool-web-ext-vscode)

## Available Tools

### Performance Tool

A tool that generates performance reports for experiment codebases, providing scores, metrics, and improvement suggestions, using the Lighthouse API.

### Validation Tool

This tool validates code post-experiment development by executing ESLint on JavaScript, checking HTTP links, and ensuring JSON files conform to a schema


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



## Development Process

*Note: This section is for completeness and does not fall under CPE team responsibilities.*

After onboarding, the lab developer can begin developing and testing the approved experiments. The developer checks the source code into the experiment repository and merges it to the main branch. Developers should not delete the gh-pages branch or .github directory.

A sample experiment codebase is available [here](https://github.com/virtual-labs/ph3-exp-dev-process/tree/main/sample/experiment), and the deployed testing URL can be found [here](https://virtual-labs.github.io/ph3-exp-dev-process/). Developers will receive an email regarding the deployment's

#### Experiment Repository Structure

Each experiment repository contains four default branches:

1. **dev**: For development and unit testing.
2. **testing**: For end-to-end testing, deployed automatically via CI/CD.
3. **gh-pages**: Automatically created during the testing branch deployment; should not be tampered with.
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
└── README.md
</pre>

## Experiment Customization and Inclusion

To include or customize an experiment, follow these steps:

1. **Update experiment.json:** Add any new items or updates to the side menu or simulation by modifying the experiment.json file.
2. **Fill Out Instructions:** Ensure all instructions in the side menu are complete and properly linked. For more details about the side menu, please refer to this document.
3. **Populate Existing Files:** Once you have the repository, make sure to populate the existing files as required. Avoid adding unnecessary files.

Developers should consult the CPE team to determine if a backend is necessary.
