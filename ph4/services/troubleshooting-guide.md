# Virtual Labs GitHub Deployment: Troubleshooting and Best Practices

## Introduction
Errors during code pushes to GitHub repositories from the dev branch to testing branch for Virtual Labs experiments can disrupt the deployment process. This document outlines common issues, troubleshooting steps, and best practices to resolve them efficiently.

## Motivation
Leveraging CI/CD pipelines to deploy experiments to GitHub Pages enhances developers' productivity and instills confidence in releases by automating testing and deployment processes.

## Prerequisites
Before proceeding, ensure you have:
- A GitHub account with access to the [Virtual Labs GitHub Organisation](https://github.com/virtual-labs).
- Familiarity with the Virtual Labs deployment process.
- Basic knowledge of JSON syntax for troubleshooting configuration files.

## Target Audience
This guide is intended for Developers, Systems Engineers, DevOps Engineers, and other team members developing experiments and managing CI/CD pipelines for Virtual Labs. It assumes a foundational understanding of CI/CD workflows.

---

## Troubleshooting Experiment Deployment Scripts
This section discusses common issues, solutions, and best practices for managing GitHub Actions used to deploy experiments to GitHub Pages.

### Why are hosted virtual lab experiments not working as expected?
Potential reasons include:

- **Tag Consistency**: Ensure that the tags in the lab descriptor file match the actual tags in your codebase. Inconsistencies can cause deployment issues.
- **Code Merge Status**: Verify that the relevant code changes are merged from the testing branch into the main branch. Unmerged changes won't reflect in the hosted lab.
- **Error Logs**: Check the GitHub Actions logs for detailed error messages. These logs can provide insights into issues during the build or deployment process.

---

### How to Check Error Logs in GitHub
1. Navigate to the **Actions** tab in the GitHub repository.
2. Identify the workflow associated with the recent deployment or changes.
3. Click on the workflow run to view its details.
4. Expand the relevant job or step to inspect error logs.

---

### Common Issues and Solutions

#### 1) GitHub Pages site is not loading or displaying properly.

- **Problem**:  
  The site is inaccessible or not rendering as expected.

- **Root Cause**:  
  Misconfiguration of GitHub Pages settings.

- **Solution**:  
  1. **Verify GitHub Pages setup**:  
     Navigate to the repository's **Settings** > **Pages** section. Ensure the correct branch (e.g., `gh-pages`) is selected and published.
  2. **Check Publication Status**:  
     Confirm the site is live with a message like: _"Your site is published at [experiment site URL]."_

- **Post-Fix Verification**:  
  Access the published URL to confirm the site works as expected.

---

#### 2) Build process exits with error code 128.

- **Problem**:  
  Unexpected exit during the build process.

- **Root Cause**:  
  Extra files outside the designated simulation folder.

- **Solution**:  
  1. Inspect the repository for unnecessary files.
  2. Move required files to the simulation folder or remove unneeded files.
  3. Re-run the build process.

- **Post-Fix Verification**:  
  Ensure the build completes without errors.

---

#### 3) "404" error when accessing a Virtual Labs experiment.

- **Problem**:  
  Experiment URL returns a "404" error after a code push.

- **Root Cause**:  
  Misconfiguration of the deploy branch or build errors.

- **Solution**:  
  1. Verify the deploy branch is set to `gh-pages`.
  2. Check the `gh-pages` branch for the experiment folder.
  3. Resolve any build errors in GitHub Actions.

- **Post-Fix Verification**:  
  Access the experiment URL to confirm the issue is resolved.

---

#### 4) Pipeline worked in the last iteration but fails in the current one.

- **Problem**:  
  Pipeline failures, often due to syntax errors in JSON files.

- **Solution**:  
  1. Check and validate JSON files using a JSON validator.
  2. Review workflow configurations for syntax issues.

- **Post-Fix Verification**:  
  Fix errors and re-run the pipeline.

---

#### 5) "Cannot find module '.../experiment-descriptor.json'" error during the build process.

- **Problem**:  
  Missing or incorrect `experiment-descriptor.json` file.

- **Solution**:  
  1. Verify the file exists and is referenced correctly.
  2. Update tags and paths in the configuration.

- **Post-Fix Verification**:  
  Re-run the build process to ensure successful deployment.

---

#### 6) "MaxListenersExceededWarning" error during the lab build process.

- **Problem**:  
  Build halts due to too many event listeners being created.

- **Root Cause**:  
  Missing files or directories in one of the experiments.

- **Solution**:  
  1. Identify the problematic experiment from logs.
  2. Add any missing files or directories.

- **Post-Fix Verification**:  
  Re-run the build process to ensure completion.

---

## Lessons Learned
- Maintain consistency in tags and file structures.
- Validate JSON files before pushing code.
- Regularly monitor GitHub Actions logs to identify and resolve issues early.
- Avoid renaming critical files like `index.html`.

By following these steps, you can streamline the deployment of Virtual Labs experiments and minimize disruptions during the build and deployment process.
