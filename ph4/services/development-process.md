# Virtual Labs Development Process

## Introduction

This document outlines the experiment development process for developers in the Virtual Labs project, aiming to ensure the creation of high-quality labs.

## Purpose

This document details the experiment development process for lab developers, specifying the steps involved in creating the experiments.

## Audience

The intended audience for this document includes all lab developers and owners who are seeking to develop new experiments.

## Development Process

### Step 1: Verifying the Repositories

**Check Repository Creation:** Ensure that all required repositories are created and accessible.

### Step 2: Understanding Development Workflow tools

To begin development, use the following workflow tools:

1. **[VS Extension](https://github.com/virtual-labs/tool-vscode-plugin):** Use the VS extension for a local development workflow.
2. **[Web VS Extension](https://github.com/virtual-labs/tool-web-ext-vscode):** Utilize the Web VS extension for an online development workflow.

#### Using Available Tools

1. **Performance Tool:** A [tool](https://github.com/virtual-labs/tool-performance) that generates performance reports for experiment codebases, providing scores, metrics, and improvement suggestions using the Lighthouse API.

2. **Validation Tool:** This [tool](https://github.com/virtual-labs/tool-validation) validates code post-experiment development by executing ESLint on JavaScript, checking HTTP links, and ensuring JSON files conform to a schema.

### Step 3: Understanding Repository Structure

Each experiment repository contains four default branches:

1. **dev:** For development and unit testing.
2. **testing:** For end-to-end testing, deployed automatically via CI/CD.
3. **gh-pages:** Automatically created during the testing branch deployment; should not be tampered with.
4. **main:** Contains production artifacts; only code and documents merged from the testing branch are added.

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

Developers should consult with the Central Platform Engineering (CPE) team to determine if a backend is necessary.

### Step 4: Beginning the Development Process

*Note: This section is for completeness and does not fall under the CPE team's responsibilities.*

1. After onboarding, developers fill in the existing files within the dev branches of the created repositories with the source code of the experiments and conduct unit testing locally, ensuring no additional files are added.
2. Developers should not delete the `gh-pages` branch, as it is required for automatically deploying the experiment along with the UI on GitHub pages for testing. The `.github` directory and the `LICENSE` file should also remain intact.
3. Developers will merge the fully tested `dev` branch into the `testing` branch, which will automatically deploy the experiment along with the UI on GitHub pages for testing.
4. Developers will receive an email about the success or failure of the deployment at the email address associated with the primary GitHub handle provided in the issue.
5. Developers then merge from a fully tested `testing` branch to the `main`

A sample experiment codebase is available [here](https://github.com/virtual-labs/ph3-exp-dev-process/tree/main/sample/experiment), and the deployed testing URL can be found [here](https://virtual-labs.github.io/ph3-exp-dev-process/). Developers will receive an email regarding the deployment's status.

### Step 5: Tagging the Release

1. Go to your repository on GitHub.
2. Click on the "Releases" link, usually found on the right side of the repository page.
3. Click the "Draft a new release" button.
4. In the "Tag version" field, enter the new tag version (e.g., v1.0.0). Follow Semantic Versioning guidelines.
5. Fill in the release title and description if necessary.
6. Click the "Publish release" button.

### Step 6: Additional Tips

#### Meeting Basic Requirements for the Experiments

- All experiments must work on HTTPS.
- Follow responsive design principles.
- Experiments should be static.
- The average page load size should be below 2MB, with no page exceeding 5MB.
- The average page load time should be below 1.5 seconds on a fast 3G connection, with no page exceeding 3 seconds.

#### Implementing Experiment Development Strategy

##### Developing Static Experiments

- Offer high performance, security, and low cost.
- The CPE team provides a framework for static experiments, including uniform UI, a styling library, analytics, and performance tools.

##### Developing Experiments Requiring Backend

- Built using JavaScript, Python, etc., with higher hosting and maintenance costs.
- Developers are responsible for UI conformity, analytics, containerization, and updates.

##### Customizing and Including Experiments

To include or customize an experiment, follow these steps:

1. **Update `experiment.json`:** Add any new items or updates to the side menu or simulation by modifying the `experiment.json` file.
2. **Fill Out Instructions:** Ensure all instructions in the side menu are complete and properly linked. For more details about the side menu, please refer to the documentation.
3. **Populate Existing Files:** Once you have the repository, make sure to populate the existing files as required. Avoid adding unnecessary files.

## Conclusion

This document provides detailed information about the development process. For best practices, please refer to this [document](https://virtual-labs.github.io/app-vlead-web/development/#best-practices). Once development is complete, to understand the process of hosting the developed experiments, please refer to this [document](https://github.com/virtual-labs/engineers-forum/blob/master/hosting-process.md).

