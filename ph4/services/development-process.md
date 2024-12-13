# Virtual Labs Development Process

## Introduction

This document provides a structured approach to creating high-quality experiments within the Virtual Labs initiative, ensuring consistency and ease of maintenance.

## Purpose

This document details the steps and best practices for lab developers to create, test, and deploy experiments effectively.

## Audience

This document is intended for lab developers and owners seeking to develop new experiments within the Virtual Labs ecosystem.

## Development Process

#### ***Step 1: Verifying the Repositories***

Ensure that all required repositories are created and accessible.

#### ***Step 2: Understanding Repository Structure***

Each experiment repository contains four default branches:

1. **dev:** For development and unit testing.
2. **testing:** For end-to-end testing, with automatic deployment to GitHub Pages.
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

Developers should verify the repository structure and consult the CPE team for backend requirements.

#### ***Step 3: Leveraging Development Workflow Tools***

The CPE Team has developed tools to streamline the experiment development process. These tools enable seamless integration of the development workflow, including local and GitHub Pages testing:

1. **[VS Code Extension](https://github.com/virtual-labs/tool-vscode-plugin):** A Visual Studio Code extension designed to simplify and enhance the local development workflow.
2. **[Web VS Code Extension](https://github.com/virtual-labs/tool-web-ext-vscode):** A web-based extension for Visual Studio Code, offering support for online development workflows.

#### ***Step 4: Initiating the Development Process***

*Note: This section is for completeness and falls outside the direct responsibilities of the CPE team.*

1. **Populate the `dev` Branch:**
Add the experiment's source code to the `dev` branch and perform local unit testing. Avoid including unnecessary files in the repository.
2. **Retain Essential Files and Branches:**
Ensure the `gh-pages` branch, `.github` directory, and `LICENSE` file are kept intact, as they are essential for deployment.
3. **Merge to testing Branch:**
Once local testing is complete, merge the `dev` branch into the `testing` branch. This triggers automatic deployment to GitHub Pages.
4. **Verify Build Logs:**
Ensure there are no errors in the build logs of your experiment. Refer to the [Steps to Create an Experiment](https://github.com/virtual-labs/ph3-exp-template/blob/main/experiment/README.md) for detailed instructions.
5. **Deployment Notifications:**
Developers will receive an email notification about the deployment status (success or failure). Notifications will be sent to the primary email address associated with their GitHub account (as provided in the issue).
6. **Handle Deployment Failures:**
If deployment fails, refer to the [Troubleshooting tips](https://github.com/virtual-labs/vlabs-systems/blob/main/src/systems-engineer-role/ci-cd-pipeline.md#troubleshooting-experiment-deployment-script) for debugging and resolving issues.
7. **Merge to main Branch:**
After successful testing, merge the fully tested `testing` branch into the `main` branch to prepare for production.

**Sample Resources:**

* Explore a [Sample Experiment Codebase](https://github.com/virtual-labs/ph3-exp-dev-process/tree/main/sample/experiment).
* Access the corresponding [Deployed Test URL](https://virtual-labs.github.io/exp-bubble-sort-iiith/).

Developers will continue to receive email updates on the deployment status throughout this process.

#### ***Step 5: Additional Development Tips***

1. **Meeting Basic Requirements for Experiments**

    - Ensure all experiments are HTTPS-enabled.
    - Follow responsive design principles.
    - Keep the average page load size below 2MB.
    - Aim for load times under 1.5 seconds on a fast 3G connection.

2. **Developing Static Experiments**

    - Focus on high performance, security, and cost-efficiency.
    - Leverage the CPE team’s framework for UI consistency and analytics.

3. **Developing Backend-Dependent Experiments**

    - Ensure UI consistency and analytics integration.
    - Manage backend hosting, updates, and maintenance effectively.

4. **Customizing the Sidemenu**

    To customize or include an experiment, follow these steps:
    - Modify the `experiment.json` file for updates to the side menu or simulation.
    - Follow the [Side Menu Documentation](https://github.com/virtual-labs/ph3-lab-mgmt/blob/master/docs/exp-side-menu.org).

#### ***Step 6: Utilizing Developer Tools***

1. **Performance Tool**
    Use the [Performance Tool](https://github.com/virtual-labs/tool-performance) for metrics and improvement suggestions using Lighthouse.
     
2. **Validation Tool**
    Validate code quality using the [Validation Tool](https://github.com/virtual-labs/tool-validation), which checks for:
    - ESLint compliance.
    - HTTP link verification.
    - JSON schema validation.

#### ***Step 7: Tagging the Release***

Once the branch has been tested and merged into `main`, the next step before hosting is tagging the experiment. Follow these steps to tag the release:

1. Navigate to your repository on GitHub.
2. Locate and click the "**Releases**" link, typically on the right-hand side of the repository page.
3. Click the "**Draft a new release**" button.
4. Enter the new tag (e.g., v1.0.0) in the "**Tag version**" field, following the [Semantic Versioning](https://semver.org/) guidelines.
5. Optionally, add a title and description summarizing the release.
6. Click the "**Publish release**" button to complete the process.

## Conclusion

This document provides a comprehensive guide to developing Virtual Labs experiments. For additional guidance:
- Refer to the [Best Practices](https://virtual-labs.github.io/app-vlead-web/development/#best-practices).
- Learn about hosting processes in the [Hosting Process Guide](https://github.com/virtual-labs/engineers-forum/blob/master/ph4/services/hosting-process.md).