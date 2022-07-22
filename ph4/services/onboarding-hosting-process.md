---
Title: Virtual Labs On-Boarding & Hosting Process
Author: CPE Team
Date: 9th Feb, 2022
Phase: IV

---

# Virtual Labs On-Boarding & Hosting Process
 
## Introduction

Virtual Labs is a mission mode project under the Ministry of Education (MoE). The objective of this project is to provide laboratory learning experience to the students who do not have access to adequate laboratory infrastructure. Currently there are 150+ labs developed by various institutes in the consortium. A streamlined software development life cycle process followed for the development of these labs ensures high quality labs. This document defines the on-boarding & hosting process to be followed by the developers (open source community) of the Virtual Labs project.

## Purpose

This document defines the experiment on-boarding and hosting process that should be followed by the developers of the lab while requesting the hosting of their lab on the central cloud. The roles and responsibilities of the various parties involved in the hosting process is also discussed in detail in the document.

## Motivation

A well defined experiment on-boarding and hosting process will help maintain a consistent user experience and enable experiment-authors to focus on the content. Consolidated information regarding all the deployments will also facilitate reporting.

## Audience

The target audience for this document comprises all the lab developers and owners who want to avail the hosting service provided by the Central Platform Engineering (CPE), IIITH team.

## Definitions

The following paragraphs define terminology used during the On-boarding and Hosting process.

### On-boarding
On-boarding is the process which marks the beginning of the software development of an approved lab. In this step, the CPE team creates a git repository for each experiment of the approved lab. 

### Hosting Unit
Hosting unit is the code base/repository that will be hosted in its entirety during the hosting process. It will not be possible for a part of a hosting unit to be hosted separately. A hosting unit will correspond to one public repository. A hosting unit could be a stand alone experiment or could be a lab consisting of a set of related experiments

### Hosting

Hosting is a service provided by the CPE team to publish the developed lab/experiments on a central cloud. 

### Repository Owner

Each repository, corresponding to a hosting unit, will have one designated primary owner. This owner will be the single entity responsible for all the code that resides in the repository and will have complete control over the content of repository. The owner will also be the final approval authority for a hosting request. The owner should ensure that the main branch of the repository only contains the code that needs to be hosted. The latest code in the main branch should represent the hosted experiment. 

The primary repository owner does not have to be a person. It may be any uniquely identifiable entity. It is recommended that every lab developer create a separate github handle for repository ownership. It would ensure that movement of people would not disrupt the development process. From the perspective of the CPE team, this entity will be the single point of contact for all clarifications. The CPE team will not be responsible for any confusions arising due to shared accessibility of the repo owner entity.

### Requester

A repository owner or a developer who raises a hosting request.

### Tags

The repository owner will be responsible for tagging each merge to the main branch. The owner will have to follow [Semantic Versioning](https://semver.org/) . In short, each version is a combination of three numbers (MAJOR.MINOR.PATCH) separated by dots. The changes to these numbers represent the following:

1. MAJOR: A change incompatible with previous versions.
2. MINOR: A backwards compatible new feature.
3. PATCH: A backwards compatible bug fix.

All Virtual Labs hosting requests should specify a tag.

### Testing

The hosting process will result in a deployment with an accessible url. The responsibility of testing the deployments will lie with the repository owner. The CPE team will be responsible for providing the deployment link to the repository owner. The repository owner will be responsible for ensuring that the deployed hosting unit works as expected.

## On-boarding

### Objectives 
Offer centralised organisation and uniform repository structure

### Pre-requisites 

The on-boarding process will require the following prerequisites to be met :

1. Approved lab proposal in pdf format
2. Primary Repository Owner details 

### Process  

On-boarding is the process which marks the beginning of the software development of an approved lab. In this step, the CPE team creates a git repository for each experiment of the approved lab. 

Once the proposal is accepted by the Virtual Labs consortium, the lab developer raises an [issue](https://github.com/virtual-labs/engineers-forum/issues/new?assignees=&labels=Phase-3%2C+create+experiment+repos&template=experiment-repository-creation-request.md&title=Experiment+Repository+Creation+Request+for+%3Cfill+the+lab+name+here%3E) of type Experiment Repository Creation Request on engineers-forum repository under the  virtual-labs organization on Github. The developer attaches the pdf of the approved proposal to the request issue.

In response to this request the CPE team creates a git repository for each experiment of the proposed lab. This repository is the single source of truth for the experiment. It contains all the resources and all communication related to the experiment. The CPE team shares the urls of the newly created experiment repositories on the same Experiment Repository Creation Request issue.


#### Experiment Repository Structure

The experiment repository created by the CPE team contains 4 default branches. Each branch serves a specific purpose and has certain conventions, which must be followed by the experiment developers. The developers are free to create any extra branches as they deem necessary. The 4 default branches in an experiment repository are:

1. **dev:** This is the branch where the experiment development process starts. The developers can either directly add code to the dev branch or can merge their custom or issue specific branches to the dev branch. This branch is also used for unit testing the experiment.

2. **testing:** Once the code passes unit testing in the dev branch, it is promoted to the testing branch by raising and approving a merge request from the dev branch to the testing branch. The code in the testing branch is used for the end-to-end testing of the code. Each experiment repository has a static site hosting url where the code in the testing branch is deployed. The deployment of the code is effected through an automated CI/CD pipeline provided in the experiment repository. Each merge to the testing branch automatically deploys the experiment to the testing url. The developer receives an email about the success/failure of the deployment on the email id associated with the primary repository owner’s github handle as provided in the on-boarding request. 

3. **gh-pages:** This branch is automatically created when the automated CI/CD pipeline is triggered during the merge to testing branch. This branch should not be tampered with or deleted. 

4. **main:** The branch named as main is the identifying branch of the experiment repository. The code and the documents in the main branch are the production artefacts. The only way code and documents can be added to the main branch is by merging the testing branch to it. It is mandatory that the code in the main branch is always in the deployable condition. All the reviews and hosting will be performed strictly on the documents and code present in the main branch.

The initial structure and hierarchy of each default branch of the experiment repository is shown below. Every directory has a README.md file, which details the purpose and organization of the directory. The developer adds the development artefacts into the repository while maintaining this structure:

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
├── LICENSE
└── README.md
</pre>


## Development

**This section has been added for the completeness of this document and does not fall under the responsibilities of the CPE team.**

On completion of the on-boarding step,  the lab developer can start developing the approved experiments. The developer needs to develop the experiment, test it locally, check the source code into the experiment repository and merge the source code to the main branch of the repository.
The experiment developer can either start the development on the dev branch or create a custom branch for development. During development, the developer unit tests the code. Once the code passes unit testing, the developer raises a merge request to merge the dev branch to the testing branch.
The experiment developer should not delete the gh-pages branch. This is required for automatically deploying the experiment along with UI on GitHub pages for testing the complete experiment. They should also not delete the .github directory and the LICENSE file in any of the branches. 

Each merge to the testing branch automatically deploys the experiment to the testing url. A sample experiment code base can be found [here](https://github.com/virtual-labs/ph3-exp-dev-process/tree/main/sample/experiment) and the same experiment deployed on a testing url can be found [here](https://virtual-labs.github.io/ph3-exp-dev-process/). The developer receives an email about the success/failure of the deployment on the email id associated with the github handle provided in the lab proposal. The developer then starts testing the experiment end-to-end.
After the experiment passes the end-to-end testing, the experiment needs to be reviewed and approved as prescribed by the Vitual Labs consortium. 

### Basic requirements for the Experiments

There are certain basic technical requirements that all experiments must follow in order to maintain consistency across the complete ecosystem. Primary of these requirements are:
1. All experiments must work on https
2. All experiments must follow responsive design principles
3. All experiments should be static, without any server side components (exceptions available on merits)
4. Average load size of all page on the experiment (including the loaded 3rd party libraries) should be below 2MB with no single page with load size of more than   5MB (exceptions available on merits)
5. The average load time for all pages on the experiment should be below 1.5 seconds with no single page with load time more than 3 seconds on a fast 3G  connection (exceptions available on merits)


### Experiment Development Strategy

Virtual Labs experiments can broadly be classified into the following 2 categories from the software architecture perspective:
- Static experiments (developed using HTML/CSS/JS)
- Experiments requiring backend (developed using PHP, Python etc)

#### Static Experiments
Static experiments is the architecture style supported and promoted by the Virtual Labs. Static experiments have many advantages over the ones needing backends:
- High performance
- High security
- Low hosting cost
- Low maintenance cost
- Better caching

The CPE team maintains a framework for building static experiments and the team continuously refines, enhances and augments it. The framework dramatically reduces the developer effort required to develop an experiment by providing the following features and tooling:
- Uniform UI (For all pages except simulation)
- Styling library for the simulation page
- Experiment-level usage analytics
- Fully integrated deployment for testing
- Performance tool
- Bug reporting tool (under development)
- Rating tool (under development)

The experiment development and hosting process published by the CPE team streamlines the development of static experiments.

#### Experiments Requiring Backend

Such experiments are generally built in a language like PHP or Python, optionally using a web framework. These frameworks serve the web pages by compiling a web page template with some data in response to a user request. The primary motivation for following this model is the ease of development which results in higher costs of hosting and maintenance while providing poorer performance and security in comparison to the static experiments.

The Virtual Labs experiment development framework and process do not align with this model of experiment development. If the developers decide to follow this model, some of the things they will be responsible for are the following:

- Building the UI conforming to other virtual labs
- Instrumenting the code with analytics
- Locally testing the experiment
- Containerizing the build with complete set of dependencies
- Continuously updating the experiment to match the latest Virtual Labs styling

There are certain cases where an experiment needs to have a back-end due to non-availability of a certain kind of functionality in JavaScript. Such cases need to be discussed with the CPE team in order to decide upon the most suitable architecture.

In any case if the developer decides to go with this model, it is good to have a discussion ( initiated by posting an issue on the [engineers-forum](https://github.com/virtual-labs/engineers-forum/issues) ) with the CPE team in order to understand what level of support can be made available by the CPE team. This will avoid late surprises.

##  Hosting

### Objectives

Hosting is a service provided by the CPE team which includes the following:

1. Providing infrastructure required to serve the Lab/Experiments
2. Ensuring round the clock availability of the Lab/Experiments
3. Ensuring an acceptable infrastructure performance criteria

Following are **not** part of the On-Boarding or Hosting service:

1. Implementation: The CPE team is not responsible for any bug fixes or enhancements or implementation on the Lab/Experiment. The developers should ensure that their product is complete and functional before raising a hosting request.
2. Testing: The deployable code is a black box for the CPE team. The CPE team is not responsible for testing the deployments. The developer/owner of the Lab/Experiment is responsible for confirming that the Lab/Experiments are deployed and functioning as intended. This confirmation is part of the hosting process.
3. Approvals: The CPE team does not provide any approvals regarding the completeness of the Lab/Experiment. The developers are expected to have sought the necessary approvals regarding completeness of the Lab/Experiment before raising a hosting request.

### Pre-requisites 

Once the experiment is approved, the developer merges the testing branch to the main branch of the experiment repository. The developer also creates a tag on the main branch. This tag is used in the hosting request to uniquely identify the code to be hosted. Ater the code is merged to the main branch and the tag is created, the experiment is ready for public availability.

### Process 

After the development and approval of all the experiments listed in the proposal, which constitute the lab, is completed and the developer is ready to publish the experiments to their target audience, they raise an [issue](https://github.com/virtual-labs/engineers-forum/issues/new?assignees=&labels=Phase-3&template=lab-experiment-s--hosting-request.md&title=Lab%2FExperiment+Hosting+Request+for++) of type Lab/Experiment Hosting Request on the Engineers’ Forum repository. A hosting request is in the form of a github issue containing the following information for each experiment in the lab :
1. Experiment Name
2. Experiment Repository URL
3. Tag to be hosted 

Along with the above details for each experiment, the issue should contain the following information and documents about the lab as a whole: 

4. Contact Person details
    - Github handle of the requester
     
5. Approved Review as a pdf attachment

The CPE team picks up the source code from the tag in the experiment repository and builds all experiments with the common Virtual Labs UI. The CPE team also builds the lab as a container for all the experiments. The CPE team, then deploys the lab and all experiments to the centrally managed cloud. Once the deployment process is complete, the experiments are ready to be used by the target audience. On successful hosting, the CPE team will add the link of the newly hosted content to the hosting request issue. The requester will be responsible for the verification of the hosted link and convey their approval on the same issue. 

### Lifecycle of a Hosting Request

The hosting request will go through the following lifecycle:

1. Requester will raise a hosting request issue by duly filling in the details in the [hosting request](https://github.com/virtual-labs/engineers-forum/issues/new?assignees=&labels=Phase-3&template=lab-experiment-s--hosting-request.md&title=Lab%2FExperiment+Hosting+Request+for++). If the lab is already hosted and requires rehosting the requester will request rehosting on the original hosting request. 
2. On a successful hosting, the hosting team will add the link of the newly hosted content to the hosting request issue. 
3. On failure ( because of missing or incorrect information or repository problems,), the hosting team will respond to the requester on the same issue.  
4. The requester will be responsible for fixing the failed hosting bug and will request a rehosting on the same issue.  
5. Once the hosting is successful, the requester will be responsible for the verification of the hosted link. If the hosting is not as expected, the requester will need to specify if they would like to revert to the previous hosted image else the request will need to convey their approval on the same issue. 
6. Only on approval from the requester, the CPE team will share the hosted url for linking to the central vlabs site. 

Responsibility of approving the hosted url rests with the requester. The CPE team will not be sending reminders and will not be responsible for any time delays at the requester's end to convey their approval on hosting/rehosting. 

## FAQ

** After submitting the experiment repository creation request, can we change the Primary and Secondary GitHub Handle? ** 

The Experiment Repository Creation Request has a couple of parameters for GitHub handles, which are:

1. Primary Github Handle Details: This is the Github handle which is used to communicate all the activities in a repo and will have developer access (Write Access on Github) to the Repo.
 
2. Secondary Github Handle Details: These are Github handles which will have developer access ( Write Access on Github) to the Repo.

In principle, the Primary Github Handle is static. It should not be changed after repo creation. We strongly suggest that you create a separate handle for Virtual Labs development as the Primary Handle and have someone monitor it all the time. Since developers/students contributing to the development will keep coming and going, it'd be good to not use anyone's personal handle as the Primary Github Handle.

Secondary Github Handles are fluid. There can be any number of developers and they can be freely updated.

The process for updating both kind of handles is very simple. You can request to change the Primary or Secondary Handle by putting a comment on the same repository creation request issue. Once we receive the request, we will make corresponding changes on our configuration and update you through a comment on the same issue.


**Why should I use the Hosting Service?**

To get more for nothing. Hosting Service provides you a high-availability, high-performance deployment environment. You do not have to spend time, money, people or other resources to ensure that your website is available to your target audience. You can also take advantage of other services, like  Analytics, provided by the CPE team and monitor multiple statistics about the users and usage patterns of your Lab.

**Do I get better website performance if I use Hosting Service?**

Almost all the time. The CPE team works continuously to improve the overall and individual Lab/Experiment performance based on the Analytics data. You can compare the performance of the Labs/Experiments deployed through the hosting service to those deployed elsewhere. 

**Does the CPE team help me improve my Lab performance?**

Yes. The CPE team continuously works to improve the infrastructure in order to achieve best performance results for your Lab. The CPE team does not improve your code. 

**Does Hosting Service add any UI to my webpages?**

Yes. Hosting service adds an uniform UI to your lab and experiments but does not alter your code in any way. As the developer, you are responsible for ensuring that your Lab/Experiment is complete in all respects before you request it to be hosted. Hosting service is strictly limited to its stated objectives. 

**How can I get Analytics for my experiments?**

By working with the CPE team. Analytics service is another service provided by the CPE team. You can work with the CPE team to integrate Analytics service into your Labs. You can also get access to customized dashboards/reports in order to monitor multiple statistics about the users and usage patterns of your Lab.

**Does the CPE team test my Lab for correctness as part of hosting?**

No. It is not possible for the CPE team to test your Lab because only you understand the right definition of correctness for your Lab/Experiment. As part of hosting, the CPE team ensures that your Lab is up and accessible. You are responsible for ensuring the completeness and correctness of your code and deployment.

**Will the CPE team tell me about broken links as part of hosting?**

No. Your code is a complete blackbox for the CPE team. You are responsible for ensuring the completeness and correctness of your code and deployment.

## Conclusion

This document highlights the on-boarding and hosting process of the CPE team. It aims at collating contributions of the developers across the open source platform - GitHub. This streamlined process would help in our strive for excellence in delivering high standard labs.

## Glossary

- **Repository** : The distributed version control system - git is used here. Every time the term repository or repo is used, it refers to a git repository. A repository is an on-disk data structure which stores metadata for a set of files and/or directory structure. The whole set of information in the repository may be duplicated on every user&#39;s system or may be maintained on a single server.
- **Virtual Labs** : Virtual Labs is an initiative by MHRD under NMEICT. The objective of this project is to make engineering education engaging, enjoyable, immersive and online.


