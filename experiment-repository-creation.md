# Experiment Repository Creation Process

## Creating an Experiment Repository on GitHub

## Introduction
[Github](https://github.com/) is a web-based git platform that allows developers from different [institutes](https://www.vlab.co.in/participating-institutes) to store and collaborate on [experiment code repositories](https://github.com/orgs/virtual-labs/repositories). An experiment repository is a collection of files and folders containing the experiment's code and project files of the experiment. In this guide, we will go through creating an experiment repository.

## Prerequisites
Before we start, you will need a GitHub account and access to [Virtual Labs](https://www.vlab.co.in/) Github [Organisation](https://github.com/virtual-labs).

## Steps to Create an Experiment Repository

### Step 1: Log in to GitHub
Go to the GitHub website and log in to your account.

### Step 2: Create a New Repository
To create a new repository, click on the '+' icon in the top right corner of the GitHub website. Select ['New Repository'](https://github.com/new) from the dropdown menu.

### Step 3: Set up the repository
On the 'Create a new repository page, you will need to enter the following information:

#### Repository Template
Click on the 'template' dropdown menu and select the 'virtual-labs/ph3-exp-template' template from the menu.

#### Repository Name
Enter a name for the experiment repository. Ensure the name is descriptive, follows repo name rules, and is easy to remember.

##### a) Repository name rules
- Experiment repository name should start with 'exp.'
- Second part of the repository name is the name of the experiment
- Last part would be the institute name
- The repository name should not have capital letters or symbols. Only AlphaNumeric.
> Example: Creation of Bubble Sort experiment repository for IIITH </br>
> exp-bubble-sort-iiith

#### Description
Enter the lab name and full name of the experiment in the repository description. This will help developers and other users to understand the repository.
> Example: This experiment belongs to Data Structures 1 IIITH. Full Name: Bubble Sort

#### Public or Private
Choose whether you want your repository to be public or private. Anyone can access public repositories, while you and your collaborators can only access private repositories you specify. We need to create a public repository for an experiment. 

### Step 4: Create the Repository
Once you have entered all the necessary information, click the 'Create Repository' button at the bottom of the page. Congratulations! You have just created an experiment repository.

### Step 5: Create Branches

##### a): Go to the repository
Go to the required experiment repository page and select the branch dropdown menu. You should see the default branch listed, usually named 'main.'

#####  b): Click on 'Create a New Branch
Click on the 'Create a New Branch' button to the left of the branch dropdown menu.

##### c): Enter the Branch Name
Enter a name for your new branch. The name should be descriptive, easy to remember, and indicate the branch's purpose.
- For a given experiment, only the following two branches must be created, "testing" and "dev." 

##### d): Choose the Starting branch
Choose the branch you want to start your new branch from. This is usually the default branch, but you can choose another branch if necessary. Here, we will select the 'main' branch as our base branch to create the "testing" and "dev" branches. 

##### e): Create the Branch
Click the 'Create Branch' button to create the new branch. GitHub will automatically switch to the new branch and display its contents.

### Step 6: Enable GitHub(testing) Pages

Go to the repository settings page of an experiment and scroll down to the "GitHub Pages" section. Under "Source," select the "gh-pages" branch and click "Save." The GitHub Pages site should now be live at the URL in the "GitHub Pages" section.

### Step 7: Adding Website URL & Topics

##### a): Go to the repository
Go to your repository page and click on the "About" tab.

##### b): Add Website Link
Click on the "Enter a valid URL" section below the description. Add the URL that is generated in the GitHub pages.

##### c): Add Topics
Topics are a way to categorize and discover experiment repositories. Under the 'Topics' section, we can add up to 10 topics to an experiment repository. Add the institute name and phase of the lab to the topics. i.e., 'iiith,' 'exp-ph3.'

##### d): Save Changes
After editing the repository details, website link, and topics, click the Save Changes button at the bottom of the pop-up.

### Step 8: Adding People to the experiment Repository
We must add developers to the experiment repository to collaborate on the code and website. Here are the steps to add developers:

##### a): Go to the repository
Go to the experiment repository page and click the "Settings" tab.

##### b): Manage access
Under the "Manage Access" section, click the "Invite a collaborator" button. Enter the developer's GitHub username or the email address mentioned in the issue and click "Add." The developer will receive an email invitation to collaborate on the repository.

##### c): Assign Permissions
You can assign different permissions to the developer we added. Click on the developer's name under the "Manage Access" section and select the desired permission level. The available permission levels are:

- Admin: Full read/write access to the repository, including managing collaborators and access settings.
- Write: Read/write access to the repository but cannot manage collaborators or access settings.
- Read: Read-only access to the repository.
- Triage: Can read and clone the given repository. Can also manage issues and pull requests.
- Maintain: Maintainer access to the repository.

### Conclusion
In this guide, we have walked through creating a Virtual-Labs experiment repository. Now that we have a repository, you can share it on the engineer's forum issue.

