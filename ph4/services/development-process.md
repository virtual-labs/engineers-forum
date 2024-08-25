# Virtual Labs Development Process

## Introduction

This document outlines the experiment development process for developers in the Virtual Labs project, aiming to ensure the creation of high-quality labs.

## Purpose

This document details the experiment development process for lab developers. It specifies the steps involved.

## Audience

The target audience for this document includes all lab developers and owners seeking to develop new experiments.

# Process

##  Step 1: Preparation for Development

### Verify Repositories

1. **Check Repository Creation:** Ensure all required repositories are created and accessible.

### Development Tools

To start development, use the following tools:
1. **[VS Extension](https://github.com/virtual-labs/tool-vscode-plugin):** Utilize the Web VS extension for online development.
2. **[Web VS Extension](https://github.com/virtual-labs/tool-web-ext-vscode):** Use the VS extension for local development.

## Available Tools
1. Performance Tool: A [tool](https://github.com/virtual-labs/tool-performance) that generates performance reports for experiment codebases, providing scores, metrics, and improvement suggestions, using the Lighthouse API.

2. Validation Tool: This [tool](https://github.com/virtual-labs/tool-validation) validates code post-experiment development by executing ESLint on JavaScript, checking HTTP links, and ensuring JSON files conform to a schema


## Step 2: Basic Requirements for the Experiments

- All experiments must work on HTTPS.
- Follow responsive design principles.
- Experiments should be static.
- Average page load size should be below 2MB, with no page exceeding 5MB.
- Average page load time should be below 1.5 seconds on a fast 3G connection, with no page exceeding 3 seconds.

## Step 3: Experiment Development Strategy

### Static Experiments

- Offer high performance, security, and low cost.
- The CPE team provides a framework for static experiments, including uniform UI, a styling library, analytics, and performance tools.

### Experiments Requiring Backend

- Built using JavaScript, Python, etc., with higher hosting and maintenance costs.
- Developers are responsible for UI conformity, analytics, containerization, and updates.

## Step 4: Development Process

*Note: This section is for completeness and does not fall under CPE team responsibilities.*

1. After onboarding, developers will populate the dev branches of the created repositories with the source code of the experiments and unit test the experiments locally.
2. The developer should not delete gh-pages branch. This is required for automatically deploying the experiment along with UI on GitHub pages for testing the complete experiment. They should also not delete .github directory and the LICENSE file.
3. The developer will merge the fully tested dev branch to the testing branch. This will automatically deploy the experiment along with UI on GitHub pages for testing the complete experiment.
4. The developer will receive an email about the success/failure of the deployment on the email id associated with the primary github handle provided in the issue.
5. Developers then merge from a fully tested testing branch to the main branch and tag the commit.

Note: How to Tag a Release in GitHub:
1. Go to your repository on GitHub.
2. Click on the "Releases" link, usually found on the right side of the repository page.
3. Click the "Draft a new release" button.
4. In the "Tag version" field, enter the new tag version (e.g., v1.0.0). Follow Semantic Versioning guidelines.
5. Fill in the release title and description if necessary.
6. Click the "Publish release" button.
 
	
A sample experiment codebase is available [here](https://github.com/virtual-labs/ph3-exp-dev-process/tree/main/sample/experiment), and the deployed testing URL can be found [here](https://virtual-labs.github.io/ph3-exp-dev-process/). Developers will receive an email regarding the deployment's

Please refer to  the document for [best practices](https://virtual-labs.github.io/app-vlead-web/development/#best-practices)

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

## Step 5: Experiment Customization and Inclusion

To include or customize an experiment, follow these steps:

1. **Update experiment.json:** Add any new items or updates to the side menu or simulation by modifying the experiment.json file.
2. **Fill Out Instructions:** Ensure all instructions in the side menu are complete and properly linked. For more details about the side menu, please refer to this document.
3. **Populate Existing Files:** Once you have the repository, make sure to populate the existing files as required. Avoid adding unnecessary files.

Developers should consult the CPE team to determine if a backend is necessary.

## Conclusion

For detailed information about the development process and the next steps, please refer to this [document](https://github.com/virtual-labs/engineers-forum/blob/master/hosting-process.md).
