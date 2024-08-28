# Virtual Labs Development Process

## Introduction

This document outlines the experiment development process for developers in the Virtual Labs project, aiming to ensure the creation of high-quality labs.

## Purpose

This document details the experiment development process for lab developers, specifying the steps involved in creating the experiments.

## Audience

The intended audience for this document includes all lab developers and owners who are seeking to develop new experiments.

## Development Process

***Step 1: Verifying the Repositories***

Ensure that all required repositories are created and accessible.

***Step 2: Understanding Repository Structure***

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

***Step 3: Leveraging Development Workflow Tools***

To assist developers in the experiment development process, the CPE Team has created the following Virtual Labs workflow tools. These tools integrate the development workflow, enabling testing both locally and on GitHub Pages:

1. **[VS Code Extension](https://github.com/virtual-labs/tool-vscode-plugin):** Use this VS Code extension to streamline your local development workflow.
2. **[Web VS Code Extension](https://github.com/virtual-labs/tool-web-ext-vscode):** Opt for this Web VS Code extension to support an online development workflow.

***Step 4: Initiating the Development Process***

*Note: This section is included for completeness and is outside the scope of the CPE team's responsibilities.*

1. After onboarding, developers should populate the existing files within the `dev` branches of the created repositories with the experiment’s source code. They should conduct local unit testing, ensuring no additional files are added to the repository.
2. Do not delete the `gh-pages` branch, as it is essential for automatic deployment of the experiment and UI to GitHub Pages for testing. The `.github` directory and the `LICENSE` file must also remain unchanged.
3. Once the `dev` branch is fully tested, developers should merge it into the `testing` branch. This action will automatically deploy the experiment and UI to GitHub Pages for testing.
4. Developers will receive an email notification regarding the success or failure of the deployment, sent to the email address linked to their primary GitHub handle (provided in the issue).
5. If deployment fails, developers should refer to the [Troubleshooting tips](https://github.com/virtual-labs/vlabs-systems/blob/main/src/systems-engineer-role/ci-cd-pipeline.md#troubleshooting-experiment-deployment-script) to debug the issue.
6. After successful testing, developers should merge the fully tested `testing` branch into the `main` branch.

A sample experiment codebase is available [here](https://github.com/virtual-labs/ph3-exp-dev-process/tree/main/sample/experiment), and the corresponding deployed test URL can be accessed [here](https://virtual-labs.github.io/exp-bubble-sort-iiith/). Developers will be notified of the deployment status via email.

***Step 5: Additional Development Tips***

**Meeting Basic Requirements for Experiments**

- All experiments must be accessible over HTTPS.
- Ensure responsive design principles are followed for optimal display across devices.
- Experiments should remain static for improved performance and easier maintenance.
- The average page load size should be under 2MB, with no individual page exceeding 5MB.
- Aim for an average page load time of under 1.5 seconds on a fast 3G connection, with no page taking longer than 3 seconds to load.

**Developing Static Experiments**

- Focus on high performance, security, and cost-efficiency.
- The CPE team offers a framework for developing static experiments, which includes a consistent UI, a styling library, and tools for analytics and performance optimization.

**Developing Experiments Requiring a Backend**

- Experiments with backend components (e.g., built with JavaScript, Python, etc.) involve higher hosting and maintenance costs.
- Developers are responsible for ensuring UI consistency, integrating analytics, managing containerization, and handling updates.

**Customizing and Including Experiments**

To customize or include an experiment, follow these steps:

1. **Update `experiment.json`:** Modify the `experiment.json` file to include new items or updates to the side menu or simulation.
2. **Complete Instructions:** Ensure all instructions in the side menu are fully populated and correctly linked. Refer to the [documentation](https://github.com/virtual-labs/ph3-lab-mgmt/blob/master/docs/exp-side-menu.org) for further details on managing the side menu.
3. **Populate Existing Files:** Populate the provided files in the repository as needed, without adding extra files.

***Step 6: Utilizing Developer Tools***

Once the experiment has been deployed on GitHub Pages for testing, developers can leverage the following tools to enhance their experiments:

1. **Performance Tool**: This [tool](https://github.com/virtual-labs/tool-performance) generates performance reports for the experiment's codebase, offering scores, metrics, and actionable improvement suggestions by utilizing the Lighthouse API.

2. **Validation Tool**: This [tool](https://github.com/virtual-labs/tool-validation) ensures code quality post-experiment development by running ESLint on JavaScript, verifying HTTP links, and ensuring that JSON files adhere to the appropriate schema.

***Step 7: Tagging the Release***

Once the developer has tested and merged the branch into `main`, the next step before hosting is to tag the experiment. To tag an experiment, follow these steps:

1. Navigate to your repository on GitHub.
2. On the repository page, locate and click the "Releases" link, typically found on the right-hand side.
3. Select the "Draft a new release" button.
4. In the "Tag version" field, enter the new tag (e.g., `v1.0.0`), following the Semantic Versioning guidelines.
5. Optionally, provide a title and description for the release.
6. Finally, click the "Publish release" button.

## Conclusion

This document provides detailed information about the development process. For best practices, please refer to this [document](https://virtual-labs.github.io/app-vlead-web/development/#best-practices). Once development is complete, to understand the process of hosting the developed experiments, please refer to this [document](https://github.com/virtual-labs/engineers-forum/blob/master/hosting-process.md).

