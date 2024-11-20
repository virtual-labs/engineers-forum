
## Introduction
In instances where an error occurs during the code push to the GitHub repository for Virtual Labs experiments, a common issue may arise.

## Motivation
Using the CI\CD pipeline to deploy experiments for testing on GitHub pages will help developers increase productivity and enhance confidence in releases.

## Prerequisites
- Before we start, you will need a GitHub account and access to [Virtual Labs](https://www.vlab.co.in/) Github [Organisation](https://github.com/virtual-labs) and knowledge on [GitHub CI/CD](https://resources.github.com/ci-cd/) pipeline.

## Target Audience 
- This document is intended for Systems Engineers, DevOps Engineers, and other team members at Virtual Labs responsible for creating and managing CI\CD Pipelines organization. Also, this document expects the intended audience to have basic knowledge of CI\CD Pipelines. 

## Troubleshooting Experiment Deployment Script
- This section briefly discusses managing or troubleshooting GitHub Actions for deploying code to GitHub Pages.

## Why are the hosted virtual lab experiments not working as expected?
The reason for this may be one of the following 
  - Verify Tag Consistency: Ensure that the tags used in the lab descriptor file match the actual tags in your codebase. Inconsistencies can lead to unexpected behavior.
  - Confirm Code Merge: Verify that the code for the malfunctioning experiment(s) has been successfully merged from the testing branch into the main branch. Unmerged code changes won't be reflected in the hosted lab.
  - Error Logs: If the above steps don't resolve the issue, consult the error logs associated with the virtual lab environment. These logs can provide valuable clues about the specific cause of the problem.

### How to Check Error Logs in GitHub
- Navigate to the Actions tab in the GitHub repository.
- Locate the workflow associated with the recent deployment or changes.
- Click on the workflow run to view the details.
- Expand the relevant job or step to inspect the error logs for any issues.

### Here are sample github issues.

#### 1) Why is GitHub Pages site not loading or displaying properly?

- **Problem**:  
  GitHub Pages for an experiment repository are not working or the site is not accessible.

- **Error Description**:  
  The GitHub Pages site is not loading, which typically happens when GitHub Pages is not configured properly for the repository.

- **Root Cause**:  
  GitHub Pages may not be set up correctly for the repository, or there might be a misconfiguration that prevents the page from being published or accessed.

- **Steps to Fix**:  
  1. **Check if GitHub Pages is set up**:  
     Go to the experiment repository’s main page on GitHub.
  2. **Access repository settings**:  
     Click the "Settings" button located near the top-right corner of the page.
  3. **Scroll to GitHub Pages section**:  
     Scroll down the settings page to find the "Pages" section.
  4. **Verify publication**:  
     If GitHub Pages is set up correctly, you should see a message that says, _"Your site is published at [experiment site URL]._  
     This message confirms that the site is live and can be accessed via the provided URL.

- **Solution/Fix**:
  1. If GitHub Pages is not set up or the site is not live, configure the GitHub Pages settings:
     - Choose the correct source branch (gh-pages) for your Pages site.
     - Save the settings.
  2. Once the page is published, recheck the "GitHub Pages" section for the confirmation message and the live URL.

- **Post-Fix Verification**:  
  After configuring GitHub Pages, visit the published URL to confirm that the site is working as expected.


#### 2) Why does the build process exit with code 128?

- **Problem**:  
  The build process for the experiment exits unexpectedly with an error code 128.

- **Error Description**:  
  This error typically indicates that there are unexpected or extra files present in the repository that interfere with the build process.

- **Root Cause**:  
  The primary cause of this error is the presence of extra files outside the designated simulation folder of the experiment. Any files that are not part of the expected structure can lead to the build failing and returning an exit code of 128.

- **Solution/Fix**:  
  1. **Check for extra files**: Inspect the repository to identify any files that are not located in the designated simulation folder.
  2. **Move or remove extra files**: 
     - Move any extra files into the simulation folder if they are needed for the experiment.
     - If certain files are not necessary, remove them from the repository entirely.
  3. **Re-run the build process**: After ensuring that all files are correctly placed, attempt to build the experiment again.

- **Post-Fix Verification**:  
  Once the extra files are addressed, re-run the build process and verify that it completes successfully without exiting with code 128.

- **Lessons Learned**:  
  1. Do not add any other files in the repository.
  2. Maintain a clean repository by regularly checking for and organizing files to prevent build issues.
  3. Establish clear guidelines for file organization within the experiment to avoid similar errors in the future.
  
## 3) Why do I get a "404" error when trying to access a Virtual Labs experiment after pushing a code change?

- **Problem**:  
  After pushing a code change, attempting to access a Virtual Labs experiment results in a "404" error.

- **Error Description**:  
  A "404" error indicates that the requested resource could not be found. This typically occurs if the build process failed or if there are issues in the code that prevent the experiment from being served correctly.

- **Solution/Fix**:  
  There are a few possible solutions for this error:

  1. **Check the deploy branch**:
     - Go to the "Settings" section of the experiment repository.  
     - Scroll down to the "GitHub Pages" section.
     - Ensure that the deploy branch is set to **`gh-pages`**.  
     - If the deploy branch is incorrectly configured, update it to `gh-pages` and save the settings.

  2. **Check the `gh-pages` branch**:  
   - Go to the `gh-pages` branch of the repository.  
   - Check if it contains a directory with the experiment name.  
   - If the experiment folder exists in the `gh-pages` branch, this indicates the build has failed. You will need to verify the build status and troubleshoot further.

  3. **Verify the build status**:  
     Navigate to the latest commit in the GitHub repository and check if the build ran successfully. If the build failed, further investigation is required. If someone has renamed a file in the repository, the build will fail and show the following error:
  
     ```
     ENOENT: no such file or directory, open '/home/runner/work/exp-kronig-penney-model-dei/exp-kronig-penney-model-dei/build/exp-kronig-penney-model-dei/simulation/index.html'
     ```
     This error occurs because the build process is unable to find the file `index.html`. Ensure the file is correctly named as `index.html` to resolve the issue.

  4. **Investigate the Build Directory**:  
     Examine the directory `home/build/repo_name` for any built or unbuilt sources. Identify and address any build errors to ensure that the build process completes successfully.

  5. **Check for JSON Errors**:  
     Many issues arise from errors in JSON files. Use a JSON validator to check and resolve any syntax or structural issues in the JSON files that may be causing the build to fail.

- **Post-Fix Verification**:  
  After addressing any build errors and resolving JSON issues, re-run the build process. Once it completes successfully, attempt to access the Virtual Labs experiment again to confirm that the "404" error is resolved.

- **Lessons Learned**:  
  1. Regularly monitor build statuses after code changes to catch errors early.
  2. Validate JSON files before pushing code to minimize issues related to malformed files.
  3. Do not rename the `index.html` file.

#### 4) Pipeline worked in the last iteration but not working in this iteration. Why? (JSON)
  - Verify that your workflow file ([`.github/workflows/deployment-script.yml`](https://github.com/virtual-labs/exp-bubble-sort-iiith/blob/main/.github/workflows/deployment-script.yml) or a similar name) is correctly set up and has no syntax errors. Ensure the file structure, event triggers, job steps, and actions are adequately defined.
  - Go to the Actions tab in your GitHub repository to check the status of your GitHub Actions. Look for failed or errored workflows, and select the specific run to view more details. 
  - GitHub Actions provides logs for each workflow run. These logs contain detailed information about the execution of each step in your workflow. Examine the logs to identify any errors or warnings, which can help you pinpoint the cause of the issue.
  - Most of the issues are due to syntax issues in JSON files(Expecting the audience to know JSON).
  - Identify the JSON file and report to the developer to fix the syntax. 
    

#### 5) Why do I get the error "uncaughtException: Cannot find module '.../experiment-descriptor.json'" during the build process?

- **Problem**:  
  During the build process, an uncaught exception error is encountered, stating that the `experiment-descriptor.json` file cannot be found.

- **Error Description**:  
  The error message typically looks like this:
  error: uncaughtException: Cannot find module '/home/runner/work/lab-basic-electronics-virtual-laboratory-iitkgp/lab-basic-electronics-virtual-laboratory-iitkgp/ph3-lab-mgmt/lab_build/exprepos/ohm-law/experiment-descriptor.json'

- **Root Cause**:  
This error occurs because the build process is unable to locate the `experiment-descriptor.json` file for the specified experiment.
This issue usually happens when the experiment tag mentioned in the repository or configuration file does not exist or is incorrect.

- **Solution/Fix**:  
1. **Check the experiment with the error**:  
   Identify the specific experiment mentioned in the error (in this case, the "ohm-law" experiment) and verify its configuration.
   
2. **Verify the tags**:  
   Ensure that the tag referenced for the experiment in the build files or descriptor is correct and exists in the repository. If the tag is missing or incorrect, update the tag to match the correct one.

3. **Update the experiment configuration**:  
   After verifying the correct tag, update the relevant experiment configuration files and ensure the `experiment-descriptor.json` file is accessible for the build.

- **Post-Fix Verification**:  
Once the tag and file path are corrected, re-run the build process. If the build completes successfully, the error should no longer appear.

- **Lessons Learned**:  
1. Double-check experiment tags and ensure they are correct and consistent across configuration files.
2. Ensure all necessary files, including `experiment-descriptor.json`, are properly referenced in the build process.

  
## 6) Why does the lab build stop at one experiment with the error "MaxListenersExceededWarning: Possible EventEmitter memory leak detected"?

- **Problem**:  
  When triggering the lab build process, it stops at one experiment, and the following error is displayed:
(node:1864) MaxListenersExceededWarning: Possible EventEmitter memory leak detected. 31 finish listeners added to [PassThrough]. Use emitter.setMaxListeners() to increase limit (Use node --trace-warnings ... to show where the warning was created)


- **Error Description**:  
This error is typically related to an issue in one of the experiments within the lab. It indicates that too many event listeners are being created, which suggests that a specific experiment is missing necessary files or directories.

- **Root Cause**:  
The root cause of this issue is often that one of the experiments in the repository does not have the required files or directories needed for the build process to complete successfully. This missing file or folder is causing the build to halt and trigger the warning.

- **Solution/Fix**:  
1. **Identify the experiment**:  
   Look into the logs or identify the specific experiment where the build process stopped.
   
2. **Check for missing files or directories**:  
   Navigate to the experiment's repository and verify if it has all the necessary files and directories. In particular, ensure that critical files like `experiment-descriptor.json`, `index.html`, or other required build components are present.

3. **Add the missing files**:  
   If any files or directories are missing, add them to the experiment's repository. Ensure that all the files required for the build are included.

- **Post-Fix Verification**:  
After adding the missing files, re-run the build process. Once the build completes without any warnings or errors, the issue should be resolved.

- **Lessons Learned**:  
1. Ensure that each experiment in the repository has the required files and directories to avoid build interruptions.
2. Regularly review logs during the build process to catch and resolve errors early.
3. Consider increasing the limit for event listeners in Node.js using `emitter.setMaxListeners()` if the issue persists in certain workflows.
