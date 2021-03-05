# Virtual Labs Experiment Hosting Engineer Duties

## Introduction
   Virtual Labs is a mission mode project initiated by the
   Ministry of Human Resources and Development (MHRD). The objective of this project is to provide a laboratory learning experience to the students who do not have access to adequate laboratory infrastructure, currently, there are around 90 labs developed by various institutes in the consortium.  A streamlined software development life cycle process followed for the development of these labs ensures high-quality labs. This document defines various
   duties to be followed by the hosting engineer of the 
   Virtual Labs project.

## Purpose
   This document defines various duties that should 
   be followed by the hosting engineers of the Virtual Labs while
   hosting lab and experiments to virtual-lab organization 
   servers. The roles and responsibilities of the various 
   parties involved in the hosting process is discussed in
   detailed in the document.
  
## Motivation
   Hosting the lab and experiment to virtual-labs organization
   servers will help users to access the labs and experiments
   easily and securely.
   
## Audience
   The target audience for this document is the hosting team
   at CPE, and IIITH.

## General Responsibilities and processes
   General responsibilities include the understanding of hosting responsibilities,
   On-Boarding/hosting of labs/experiments, creation of Experiment Repositories, and monitoring 
   GitHub engineers forum for requests.

### Hosting of Labs/ Experiments
1. When a request of type [Phase II Rehosting Request](https://github.com/virtual-labs/engineers-forum/issues/new?assignees=&labels=Hosting%2C+Phase-2&template=phase-ii-hosting-request.md&title=Hosting%2FRehosting+Request+for+%3CLab+Name%3E), [Phase III Lab/Experiment(s) OnBoarding Request](https://github.com/virtual-labs/engineers-forum/issues/new?assignees=&labels=On-Boarding%2C+Phase-3&template=phase-iii-onboarding.md&title=Phase+III+Lab%2FExperiment%28s%29+OnBoarding+Request+for+%3Cfill+your+lab+name+here%3E), or [Experiment Repository Creation Request](https://github.com/virtual-labs/engineers-forum/issues/new?assignees=&labels=Phase-3%2C+create+experiment+repos&template=experiment-repository-creation-request.md&title=Experiment+Repository+Creation+Request+for+%3Cfill+the+lab+name+here%3E) is raised on engineer's forum then the hosting engineer has to do the following to host a unit.


### Phase II Rehosting Request
 When an issue of phase II rehosting request is raised, the hosting engineer has to do the following,

- Step 1: Go to the [issue](https://github.com/virtual-labs/engineers-forum/issues) in the [engineers forum](https://github.com/virtual-labs/engineers-forum)

- Step 2: Check for the tag and branch as mentioned the issue

- Step 3: If the mentioned tag and branch exist then go to step 4, else comment on the same issue regarding the tag and branch

- Step 4: Copy the sources on the server and rehost in their respective server

- Step 5: After rehosting, perform a build verification test by visiting the hosted URL

- Step 6: If the build verification test is passed then go to step 7 else rebuild and rehost on the server

- Step 7: Acknowledge the rehosting request by sharing the rehosting details on the [issue](https://github.com/virtual-labs/engineers-forum/issues)

- Step 8: Finally fill the [hosting info sheet](https://docs.google.com/spreadsheets/d/1WXJA_1QkLg-5S0YYBRKyhEXwOgTSbKvm972Fy-thCUc/edit#gid=1738859394) on google sheets

### Phase III Lab/Experiment(s) OnBoarding Request

 When an issue of phase III lab/experiment(s) onboarding request or rehosting request is raised, the hosting engineer has to do the following,


#### Phase III OnBoarding(Hosting) Request
 When an issue of phase III hosting request is raised, the hosting engineer has to do the following,

- Step 1: Create a lab repository on [GitHub Virtual Labs](https://github.com/virtual-labs/) organization

- Step 2: Clone the lab repository along with [Phase-3-Lab-Template](https://github.com/virtual-labs/ph3-lab-mgmt) on the server

- Step 3: After cloning the repo the hosting engineer should go through the [README](https://github.com/virtual-labs/ph3-lab-mgmt/blob/master/README.org) file of [Phase-3-Lab-Template repository](https://github.com/virtual-labs/ph3-lab-mgmt)

- Step 4: Run the following command to initialize a lab descriptor file that contains all the required fields, without any values. In the below command <path/to/lab/repo> should be replaced with the actual path to the local lab repository mentioned in the first step.

    ``` npm run labgen -- init <path/to/lab/repo> ```

- Step 5: Fill the lab descriptor file by following [this document](https://github.com/virtual-labs/ph3-lab-mgmt/blob/master/lab-descriptor-instructions.md)

- Step 6: Confirm the obtained information by commenting on the exp name with the link, tag, and branch and repo owner details on the issue asking for approval. [Use this as referal](https://github.com/virtual-labs/engineers-forum/issues/569#issuecomment-618197675).

- Step 7: If the developer approves the data provided then go to step 8

- Step 8: Host lab and experiments. From the Phase-3-Lab-Template repository, run the following. This will copy the lab pages to /var/www/html/<lab-name>, then builds and copy experiments listed in the lab-descriptor to /var/www/html/lab-name/exp
    
    ``` npm run labgen -- deploy <path/to/lab/repo> ```

- Step 9:  After hosting, perform a build verification test by visiting the hosted URL

- Step 10: If the build verification test is passed then go to step 11 else rebuild and rehost

- Step 11: Acknowledge the hosting request by sharing the hosting details on the issue

- Step 12: Finally fill the [hosting info sheet](https://docs.google.com/spreadsheets/d/1WXJA_1QkLg-5S0YYBRKyhEXwOgTSbKvm972Fy-thCUc/edit#gid=129834454)


#### Phase III Rehosting Request

 When an issue of phase III rehosting request is raised, the hosting engineer has to do the following,

- Step 1: Go to the [issue](https://github.com/virtual-labs/engineers-forum/issues) in the [engineers forum](https://github.com/virtual-labs/engineers-forum)

- Step 2: Check for the tag and branch as mentioned the issue

- Step 3: If the mentioned tag and branch exist then go to step 4, else comment on the same issue regarding the tag and branch

- Step 4: Update the lab descriptor file with correct tags

- Step 5: From the Phase-3-Lab-Template repository, run the following. This will generate the lab pages using the verified lab-descriptor.json from the lab repository and push the generated content to the server 
   
   ```  npm run labgen -- deploy <path/to/lab/repo> ``` 

- Step 6: Unit will be rehosted after successful completion of step 5

- Step 7: After rehosting, perform a build verification test by visiting the hosted URL

- Step 8: If the build verification test is passed then go to step 9 else rebuild and rehost on the server

- Step 9: Acknowledge the rehosting request by sharing the rehosting details on the [issue](https://github.com/virtual-labs/engineers-forum/issues)

- Step 10: Finally fill the [hosting info sheet](https://docs.google.com/spreadsheets/d/1WXJA_1QkLg-5S0YYBRKyhEXwOgTSbKvm972Fy-thCUc/edit#gid=129834454)


### Experiment Repository Creation Request

 Steps to be followed by VLEAD's Hosting Engineer

- Step 1: On receiving a [request](https://github.com/virtual-labs/engineers-forum/issues) for creation of experiment repositories for the lab, VLEAD's hosting engineer should the experiment(s) repository from the [ph3-exp-template](https://github.com/virtual-labs/ph3-exp-template) repository.

- Step 2: VLEAD's hosting engineer should create two branches - dev and testing from the main branch in the created experiment repositories.

- Step 3: VLEAD's hosting engineer should add the Github Handle of the developer provided in the request issue to the newly created experiment repository with maintainer access. VLEAD's hosting engineer should also add the developer’s common email address to the GitHub notification center.

- Step 4: VLEAD's hosting engineer should add about section and GitHub pages link to the experiment

- Step 5: VLEAD's hosting engineer should comment on the repository creation request providing the links to the created repositories.


### Monitoring of GitHub 
1. Hosting Requests
2. Repo Creation requests
3. Permission issues 
4. Rehosting Requests



### Lifecycle of a Hosting Request
    
   - The hosting request will go through the following lifecycle:

   1.  Requester will raise a hosting request issue by duly filling in the details in the '[hosting request](https://github.com/virtual-labs/engineers-forum/issues/new/choose)'.
   2.  The hosting team will attach the URL of the corresponding onboarding request to the hosting request. If the onboarding request is not found ( by searching on the repo URL), then the hosting team will add its findings and label the issue as *Failed*.
   3.  If the requester is not the repository owner, the hosting team will seek approval from the repository owner. This will be through the above created GitHub hosting request issue.
   4.  The hosting team will honor the hosting request only on receiving the approval from the repository owner else will label the hosting request issue as *Not Approved* 
   5.  On a successful hosting, the hosting team will add the link of the newly hosted content to the hosting request issue. They will also label the issue as *Hosted*.
   6.  However, on failure ( because of missing or incorrect information or repository problems,), the hosting team will label the issue as *Failed*.
   7.  The requester will be responsible for fixing the failed hosting bug and will need to raise a new '[hosting request](https://github.com/virtual-labs/engineers-forum/issues/new/choose)' to get the unit hosted.
   8.  Once the hosting is successful, the requester will be responsible for the verification of the hosted link.  If the hosting is not as expected, the requester should change the label from *Hosted* to *Reopened*. The requester will also need to specify if he/she would like to revert to the previous hosted image.
   9.  An issue with the *Reopened* label will by default host the repository and branch/tag as specified in the hosting request initially. However, if the requester has specifically requested a revert, the previously hosted image will be restored and the issue will be labeled as *Reverted*.
   10.  If the requester wants to revert to an earlier branch/tag, a new '[hosting request](https://github.com/virtual-labs/engineers-forum/issues/new/choose)' will need to be raised to get the unit hosted.
   11. Requester will be responsible for closing a hosting request issue by changing the issue status from Open to Closed when the issue is labeled as *Hosted* or *Reopened* or *Reverted* or *Not Approved*.

## Instructions to fill the lab-descriptor while hosting
The following are the instructions to fill or update the lab-descriptor.json file which is used to host a lab. Make Sure that everything in the JSON file is updated correctly before sending it for verification and hosting

### Section I - Lab
Name: Should be Discipline name

Link: - Crosscheck the discipline link from vlab.co.in and update correctly - Discipline Should be in the following format: - Mechanical Engineering - Computer Science and Engineering - Electronics and Communication Engineering - Electrical Engineering - Civil Engineering - Chemical Sciences - Biotechnology and Biomedical Engineering - Physical Sciences - Chemical Engineering - Humanity - Metallurgical and Materials Engineering - Design Engineering - Aerospace Engineering

Lab Name: Should be same in the JSON file, GitHub repo name, and in /var/www/html/

Phase: Mention 2 for phase 2 labs, 3 for phase labs and 4 for phase 4 labs

Deploy: This should be true if we are hosting a lab and exp or only a lab. If we want to host the only exp then it should be false

College Name(Institute Name): Update from the R0 file (which is given in the request for hosting issue) Double check college name as analytics is depended on it

The following are the supported institutes and their ids (to be given in the lab id. Ex:- cse01-iiith)

#### Institute Names and their Id’s:

- [x] IIITHyderabad - iiith
- [x] Amrita - au
- [x] IIT Delhi - iitd
- [x] IIT Kanpur - iitk
- [x] IIT Guwahati - iitg
- [x] IIT Roorkee - iitr
- [x] IIT Bombay - iitb
- [x] COEP - coep
- [x] Dayalbagh - dlbg
- [x] IIT Kharagpur - iitkgp
- [x] NIT Karnataka -nitk

The following are the supported institutes and their URL (Ex:- xyz-iiith)
#### Institute Names and their URL 

- [x] IIITHyderabad - iiith
- [x] Amrita - amrt
- [x] IIT Delhi - iitd
- [x] IIT Kanpur - iitk
- [x] IIT Guwahati - iitg
- [x] IIT Roorkee - iitr
- [x] IIT Bombay - iitb
- [x] COEP - coep
- [x] Dayalbagh - dei
- [x] IIT Kharagpur - iitkgp
- [x] NIT Karnataka -nitk

Base URL: Crosscheck the lab domain in the reverse proxy and update correctly in the JSON


Introduction: from R0 file

### Section II - Experiment
1. Name: Experiment name from R0 file
2. Short Name: Short name should be in small letters and not more than 4 words or can give exp repo name from GitLab (if it has only 4 words)
3. Repo: Give the experiment repo URL from GitHub or GitLab
4. Tag: For every request of hosting, the repo should have a new tag
5. Deploy: This should be true if we are hosting a lab and exp or only exp. If we want to host the only lab then it should be false

### Section III
Target Audience, Objective, and Courses Alignment: Should be updated from the R0 file.

 - Recommendations

 - Condition 1: if we get a hosting request to update only the lab content, then a hosting person should host only the lab but not the content of the experiments. In the JSON file, deployLab should be true in the lab section, and deploy should be false in the experiments section.

 - Condition 2: if we get a hosting request to update only the experiment content, then a hosting person should host only the experiments but not the lab. In the JSON file, deployLab should be false in the lab section, and deploy should be true in the experiments section.

 - Condition 3: If the lab is hosted multiple times with spelling mistakes or so, then the multiple labs will be created in the analytics and we will lose the lab/experiments usage.

 - Condition 4: if we find the lab name conflicting with the other lab then we should contact the requesting institute and request to review/change the lab name.

 - Condition 5: After hosting the lab, test it thoroughly compared with analytics data.

#### Sample JSON file

``` {
  "broadArea": {
    "name": "Electronics and Communication Engineering",
    "link": "http://www.vlab.co.in/broad-area-electronics-and-communications"
  },
  "lab": "Digital Electronics IITR",
  "display_lab_name": "Digital Electronics 1",
  "phase": 3,
  "collegeName": "IITR",
  "baseUrl": "de-iitr.vlabs.ac.in",
  "introduction": "Welcome to the Digital Electronics Lab",
  "experiments": [
    {
      "name": "Verification and interpretation of truth table for AND, OR, NOT, NAND, NOR, Ex-OR, Ex-NOR gates",
      "short-name": "truth-table-gates",
      "repo": "https://github.com/virtual-labs/exp-truth-table-gates-iitr",
      "tag": "v1.0.0",
      "deploy": true
    },
    {
      "name": "Construction of half and full adder using XOR and NAND gates and verification of its operation",
      "short-name": "half-full-adder",
      "repo": "https://github.com/virtual-labs/exp-half-full-adder-iitr",
      "tag": "v1.0.0",
      "deploy": true
    },
    {
      "name": "Verify the truth table of one bit and two bit comparator using logic gates",
      "short-name": "comparator-using-logic-gates",
      "repo": "https://github.com/virtual-labs/exp-comparator-using-logic-gates-iitr",
      "tag": "v1.0.0",
      "deploy": true
    }
  ],
  "targetAudience": {
    "UG": ["B. Tech./ B.E in Electronics and Communications"],
    "PG": [
      "MS/Ph. D. Beginners in Electronics and Communications and related topics"
    ]
  },
  "objective": "To learn and understand the basic concepts of digital electronics.",
  "courseAlignment": {
    "description": "The syllabi of this lab aligns to the following universities in India.",
    "universities": [
      "Uttarakhand Technical University Uttarakhand",
      "Himachal Pradesh Technical University Himachal Pradesh",
      "Central Library, H.N.B.Garhwal University Uttarakhand",
      "I. K. Gujral Punjab Technical University Punjab",
      "Graphic Era University, Dehradun Uttarakhand",
      "Quantum University Uttarakhand",
      "Bhagwant University, Ajmer Rajasthan",
      "Dr. A.P.J. Abdul Kalam Technical University, Lucknow, Uttar Pradesh Uttar Pradesh"
    ]
  }
}
```


## Important documents
 The hosting engineer should have good knowledge of the following documents. (*Mandatory) 

- 1. Hosting-process-ph3 - https://github.com/virtual-labs/ph3-lab-mgmt/blob/master/hosting-process-ph3.org

- 2. Hosting-process - https://github.com/virtual-labs/engineers-forum/blob/master/hosting-process.org

- 3. lab-descriptor - https://github.com/virtual-labs/ph3-lab-mgmt/blob/master/lab-descriptor.org

- 4. migration-process - https://github.com/virtual-labs/engineers-forum/blob/master/migration-process.md
