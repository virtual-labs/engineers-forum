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

### Why isn't the experiment link working as expected?

Potential reasons include:

- **Invalid JSON Files**: Errors in experiment JSON files can disrupt deployment. Use tools like [jsonlint.com](http://jsonlint.com/) to validate and correct them.
- **File Renaming/Addition**: Adding or renaming files in the repository may trigger GitHub to nest files in a subdirectory on the `gh-pages` branch, breaking links. Ensure consistent naming and structure.
- **Incorrect GitHub Pages Setup**: Navigate to GitHub Settings → Build and Deployment → Ensure that the Branch is set to gh-pages. If the setting is different then the experiment link will not work.
- **GitHub Actions Logs**: Check the GitHub Actions logs for detailed error messages. These logs can provide insights into issues during the build or deployment process.

---

### How to Check Error Logs in GitHub while pushing the code from dev branch to testing branch?

1. Open your repository on GitHub.
2. In the top navigation bar, click on the "Actions" tab.
3. This will take you to the GitHub Actions page, where you can view workflows, logs, and any running or completed actions.
4. Identify the workflow associated with the recent deployment or changes.
5. Click on the workflow run to view its details.
6. Expand the relevant job or step to inspect error logs.

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
  Unexpected exit during the build process with exit code 128.

- **Root Cause**:  
  The issue arises due to extra files outside the designated simulation folder. During the experiment build process, some files may inadvertently be added to the repository. Specifically, the problem occurs when the plugin directory and the build directory are checked into the repository.

- **Solution**:
  - If you are using the VS Code extension, make sure to delete the build directory using the clean button from the extension, before pushing your code to the repo using the next buttons.
  - If you are building through command-line, make sure to delete the build directory and other unnecessary files, before committing the entire code into the GitHub repository.
  - Inspect the repository for unnecessary files and if found, please remove of them from version control.
    Add the following in the .gitignore file so in future they are not accidentally checked-in.

```
     node_modules/
     package.json
     package-lock.json
     build/
     DS_Store
```

- Re-run the build process.

- **Post-Fix Verification**:  
  Ensure the build completes without errors.

---

#### 3) "404" error when accessing a Virtual Labs experiment.
 
- **Reason 1**:  
    The experiment build fails because of invalid json file.

- **Root Cause**:

  - Misconfiguration of the deploy branch or build errors.
  - A common build error involves an invalid JSON file or an invalid. While GitHub Actions might show the process as completed, these compatibility errors won’t halt the build. As a result, the repository may create a subfolder and push all files into it, leading to a broken experiment link.
    
- **Solution**:

  1. Verify the deploy branch is set to **gh-pages**.
  2. To set deploy branch to **gh-pages** open the setting of experiment repository. Navigate to **Pages** under **code and automation**. Click to open.
  3. Locate the **Branch** under the **Build and deployment** head.If the deploy branch is incorrectly configured, update it to **gh-pages** and save the settings.
  4. Open the experiment repository where the error occurred.
  5. Navigate to the "**Actions**" tab on GitHub.
  6. Locate the the latest workflow, titled **Merge pull request #(some number) from virtual-labs/dev** and click it to open.
  7. It will redirect to the **Summary** of the workflow. Click on **build** under **Jobs**. This will open steps of the build.
  8. Expand the Step titled **Run git clone --depth=1 https://github.com/virtual-labs/ph3-lab-mgmt** and inspect the build logs. You will see the following error ```error: uncaughtException: /home/runner/work/exp-repo-name/exp-repo-name/build/exp-repo-name/filename.json: Unexpected token 	 in JSON at position 203
  9. Open the error json file which as mentioned log.
  10. Make changes to the above file in the dev branch and merge it to the testing branch.
  11. Check if your build was successful in https://virtual-labs.github.io/**_your-repo-name_**/

- **Post-Fix Verification**:
  
  - Access the experiment URL to confirm the issue is resolved.
  - Commit and push the corrected file to the repository.

- **Reason 2**:
  
  - The experiment build fails because of unrecognized Unicode character

- **Root Cause**:
  
  - Common build error involves an invalid or unrecognized Unicode character. While GitHub Actions might show the process as completed, these compatibility errors won’t halt the build. As a result, the repository may create a subfolder and push all files into it, leading to a broken experiment link.

- **Solution**:
  1. Open the experiment repository where the error occurred.
  2. Navigate to the "**Actions**" tab on GitHub.
  3. Locate the the latest workflow, titled **Merge pull request #(some number) from virtual-labs/dev** and click it to open.
  4. It will redirect to the **Summary** of the workflow. Click on **build** under **Jobs**. This will open steps of the build. 
  5. Expand the Step titled **Run git clone --depth=1 https://github.com/virtual-labs/ph3-lab-mgmt** and inspect the build logs. You will see the following error ```error: uncaughtException: Font metrics not found for font: .
Error: Font metrics not found for font: .```
  6.  To identify the file containing an unrecognized Unicode character: Open your browser and go to:
       https://virtual-labs.github.io/**_your-repo-name_/_your-repo-name_**/
   7. Use the side menu to navigate through each page.
   8. Look for any page that appears blank—this indicates that the build likely failed just before rendering that page.
   9. Identify the corresponding .md file for the blank page  or the page before that and inspect it for any unrecognized Unicode characters that may be causing the issue.
   10. Identify the specific file where the unrecognized character error is reported.
   11. Make changes to the above file in the dev branch and merge it to the testing branch.
   12. Check if your build was successful in https://virtual-labs.github.io/**_your-repo-name_**/

- **Post-Fix Verification**:
  
  Access the experiment URL to confirm the issue is resolved.
  Commit and push the corrected file to the repository.
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
  2. If the file is not present, copy [default-experiment-descriptor.json](https://github.com/virtual-labs/ph3-lab-mgmt/blob/master/default-experiment-descriptor.json) into your experiment's root directory.
  3. Rename the file as experiment-descriptor.json
  4. Update tags and paths in the configuration.

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

#### 7) Merging of the code from dev to testing branch failed with error code 1.

- **Problem**:  
  While merging code from dev to testing the build process failed with error exit code 1.

- **Root Cause**:  
  The repository might be using an outdated deployment script, especially if the repository was created several years ago. This outdated script may not properly reference or include the required module (exp.js) and is likely incompatible with the current deployment environment or standards, leading to the `MODULE_NOT_FOUND error`.

<img src="https://raw.githubusercontent.com/virtual-labs/engineers-forum/refs/heads/master/ph4/services/module-not-found.png" alt="module not found" width="1243" height="572">

- **Solution**:

  1. Please replace the deployment script in your experiment repository (placed at the path - `your-experiment-repository/.github/workflows/deployment-script.yml`) with latest deployment script is available [here](https://github.com/virtual-labs/ph3-exp-template/blob/main/.github/workflows/deployment-script.yml).
  2. Push this udpated deployment script to the repo. This will update the deployment script in the repo. Now try to merge code again.

- **Post-Fix Verification**:  
  Ensure the merge completes without errors.

## Lessons Learned

- Maintain consistency in tags and file structures.
- Always validate JSON files before committing.
- Regularly check GitHub Actions logs to catch issues early.
- Avoid renaming critical files like `index.html`.
- Keep deployment scripts up to date with the latest template.

By following these steps, you can streamline the deployment of Virtual Labs experiments and minimize distruptions during the build and deployment process.
