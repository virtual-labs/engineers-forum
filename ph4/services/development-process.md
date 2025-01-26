# Virtual Labs Development Process

## Introduction

This document outlines a structured approach to creating high-quality experiments for the Virtual Labs initiative, ensuring consistency, maintainability, and scalability.

## Purpose

The purpose of this document is to guide lab developers through the processes of creating, testing, and deploying experiments effectively..

## Audience

This document is intended for lab developers and owners seeking to develop new experiments within the Virtual Labs ecosystem.

## Development Process

#### ***Step 1: Verifying the Repositories***

Ensure all required repositories for the experiment are created and accessible. Collaborate with the CPE team if repository setup assistance is needed.

#### ***Step 2: Understanding Repository Structure***

Each experiment repository contains four default branches:

1. **dev:** For development and unit testing.
2. **testing:** For end-to-end testing, with automatic deployment to GitHub Pages.
3. **gh-pages:** Automatically created during the `testing` branch deployment; should not be tampered with.
4. **main:** Contains production artifacts; only code and documents merged from the `testing` branch are added.

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

**Note**: This structure may vary slightly depending on the specific requirements of the experiment. Any additional files should be documented and approved.

#### ***Step 3: Leveraging Development Workflow Tools***

The CPE Team has created tools to streamline the experiment development process, ensuring smooth integration of development workflows with local and GitHub Pages testing:

1. **[VS Code Extension](https://vlead.vlabs.ac.in/development/#authoring-environment):** A Visual Studio Code extension that simplifies and enhances the local development workflow for creating experiments.
2. **[Web VS Code Extension](https://github.com/virtual-labs/tool-web-ext-vscode/blob/main/README.md):** A web-based Visual Studio Code extension that supports online experiment development workflows. 

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

#### ***Step 5: Additional Features***

1. **Experiment UI Side Menu Customization**
Explains the customizable [side menu](https://github.com/virtual-labs/ph3-lab-mgmt/blob/master/docs/exp-side-menu.md) that aids navigation, highlights the current page, and organizes nested units via experiment-descriptor.json.

2. **Quiz Implementation in Virtual Labs**
Details the JSON-based [quiz structure](https://github.com/virtual-labs/ph3-lab-mgmt/blob/master/docs/quiz.md) with features like difficulty levels, explanations, images, and version 2.0 enhancements for pretests, posttests, and learning units.

3. **Experiment Build Process Framework**
Describes the Virtual Labs experiment structure, detailing learning units, tasks, content types, and descriptor-based webpage generation while addressing current limitations. More details [here](https://github.com/virtual-labs/ph3-lab-mgmt/blob/master/docs/exp-build-process.md).

4. **Math Rendering with KaTeX Integration**
Introduces [KaTeX support](https://github.com/virtual-labs/ph3-lab-mgmt/blob/master/docs/latex.md) in Markdown and Assessment (JSON) files, enabling seamless mathematical expression rendering via the "LaTeXinMD": true descriptor flag.

5. **Validation Tools for Experiment Development**
Provides [validation tools](https://github.com/virtual-labs/ph3-lab-mgmt/blob/master/docs/content-validation.md) for error detection and debugging, covering code consistency, descriptor and JSON validation, HTTP link checks, and a user-friendly UI.

6. **CSS and JS Module Integration in Experiments**
Enables enhanced functionality and personalized rendering by [integrating custom CSS/JS files or CDN links](https://github.com/virtual-labs/ph3-lab-mgmt/blob/master/docs/custom-modules.md) through the `experiment-descriptor.json`.

7. **Performance Tool for Experiment Developers**
 Helps developers better enhance the pages they are building by giving them comprehensive insights into the various aspects of their pages. It allows developers to improve the overall user experience. It generates [performance reports](https://github.com/virtual-labs/tool-performance) which include various scores and metrics as well as suggestions for improvement.

8. **Plugin Architecture for Virtual Labs**
Separates core functions from features like analytics, feedback, and content rendering, ensuring modularity, independent development, and extensibility. More details [here](https://github.com/virtual-labs/ph3-lab-mgmt/blob/master/docs/plugins.org).

9. **Experiment Model Classes and Enum Validations**
Details the experiment model’s classes and enums, covering unit and content types, build environments, and validation for modular and extensible system design.


#### ***Step 6: Tagging the Release***

Once the branch has been tested and merged into `main`, the next step before hosting is tagging the experiment. Follow these steps to tag the release:

1. Navigate to your repository on GitHub.
2. Locate and click the "**Releases**" link, typically on the right-hand side of the repository page.
3. Click the "**Draft a new release**" button.
4. Enter the new tag (e.g., v1.0.0) in the "**Tag version**" field, following the [Semantic Versioning](https://semver.org/) guidelines.
5. Optionally, add a title and description summarizing the release.
6. Click the "**Publish release**" button to complete the process.

#### Do's:

    - Ensure all experiments are HTTPS-enabled.
    - Follow responsive design principles.
    - Focus on high performance, security, and cost-efficiency.
    - Leverage the CPE team’s framework for UI consistency and analytics.
    - Maintain UI consistency and integrate analytics effectively.

#### Don'ts:
    - Avoid creating experiments with page sizes exceeding 2MB or slow load times that degrade user experience.
    - Refrain from allowing load times to exceed 1.5 seconds on a fast 3G connection.
    - Do not neglect backend maintenance and updates, as this can lead to inefficiencies or system downtime.


## Conclusion

This document provides a comprehensive guide to developing Virtual Labs experiments. For additional guidance:
- Refer to the [Best Practices](https://virtual-labs.github.io/app-vlead-web/development/#best-practices).
- Learn about hosting processes in the [Hosting Process Guide](https://github.com/virtual-labs/engineers-forum/blob/master/ph4/services/hosting-process.md).
