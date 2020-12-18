# Virtual Labs Experiment Hosting Engineer Duties

## Introduction
   Virtual Labs is a mission mode project initiated by the
   Ministry of Human Resources and Development (MHRD). The
   objective of this project is to provide laboratory
   learning experience to the students who do not have access
   to adequate laboratory infrastructure. Currently there are
   around 90 labs developed by various institutes in the
   consortium.  A streamlined software development life cycle
   process followed for the development of these labs ensures
   high quality labs. This document defines various
   duties to be followed by the hosting engineer of the 
   Virtual Labs project.

## Purpose
   This document defines defines various duties that should 
   be followed by the hosting engineers of the Virtal Labs while
   hosting lab and experiments to virtual-lab organization 
   servers. The roles and responsibilities of the various 
   parties involved in the hosting process is discussed in
   detailed in the document.
  
## Motivation
   Hosting the lab and experiment to virtual-labs organization
   servers will help users to access the labs and experiments
   easily and serculy.
   
## Audience
   The target audience for this document is the hosting team
   at CPE, and IIITH.

## General Responsibilities and processes
   General responsibilities include understaing of hosting 
   engineer role, On-Boarding process, creation of Experiment 
   Repositories, and watching github engineers forum for requests.

### On-Boarding process of hosting unit 
   - Each hosting unit that needs to be hosted by the Virtual Labs hosting team, must follow an onboarding process. The repository owner of the hosting unit will need to raise an  issue of type '[on-boarding request](https://github.com/virtual-labs/engineers-forum/issues/new/)' in the engineers-forum. The issue will need to filled with the  following pieces of information :
  
   <strong>On-Boarding Request</strong> - 

  1. A non-conflicting name for the hosting unit. </br>
  2. Repository URL for the hosting unit.</br>
  3. A designated repository owner with the following details: </br>
     a. Repository owner github id</br>
     b. Repository owner email address </br>
  4. The build command for the hosting unit along with the </br>
     link to the build process documentation. </br>
  5. Hardware specification including: </br>
     a. CPU </br>
     b. Memory</br>
     c. Network bandwidth</br>
  6. Software environment specification including:</br>
     a. Host operating system with minimum compatible version</br>
     b. Any additional software packages with minimum compatile versions</br>
     c. Browser plugins required to view experiment</br>
     d. DB</br>
  
  Repository owner will be reponsible for keeping the above information current and intimating the hosting team of any updates/changes as and when needed.
   
  On receipt of an onboarding request the hosting team will verify the data and acknowledge the same as part of the request. 

  The hosting team will be responsible for storing the this information at a central location and making it available for all stakeholders.
 
### Hosting Process of hosting unit
   A repository owner/developer (requester ) will have to
   raise an issue of type '[hosting request](https://github.com/virtual-labs/engineers-forum/issues/new/choose)' in the GitHub repository [engineers-forum](https://github.com/virtual-labs/engineers-forum) under Virtual-Labs organisation for hosting of a hosting unit. The issue will need to filled with the following pieces of information:
  
   1. Repository URL
   2. Branch to be deployed
   3. Tag to be deployed
   4. Contact email address and github handle to be used in cases of clarifications
   
   A hosting request will be tied to this information. This issue will be a single source of truth for that hosting request.  All communication related to the hosting will be recorded on the raised hosting request.


### Instructions to Host a Lab with Experiments
  In this section, we will discuss hosting a Lab with Experiments.

  - Step 1:
     [Phase-3-Lab-Template](https://github.com/virtual-labs/Phase-3-Lab-Template) to be cloned initially on the server.

  - Step 2:
     After cloning the repo the hosting person should go through the [README](https://github.com/virtual-labs/Phase-3-Lab-Template/blob/master/README.org) file of [Phase-3-Lab-Template](https://github.com/virtual-labs/Phase-3-Lab-Template) repository.

  - Step 3:
  Run the following command to initialize a lab descriptor file that contains all the required fields, without any values. In the below command <path/to/lab/repo> should be replaced with the actual path to the local lab repository mentioned in the first step.
	       
	     ` npm run labgen -- init <path/to/lab/repo> `
	   

  - Step 4:
  Fill all the values in the <path/to/lab/repo>/lab-descriptor.json file generated above by taking data from R0 file and create a pull-request to get the lab-descriptor approved.

  - Step 5:
  After getting approval from the legitimate authority, generate lab and build experiments.

  - Step 6: 
  From the Phase-3-Lab-Template repository, run the following. This will generate the lab pages using the verified lab-descriptor.json from the lab repository and push the generated content to remote.
	      
	      ` npm run labgen -- generate <path/to/lab/repo> `
	      

  - Step 7: Finally host lab and experiments. From the Phase-3-Lab-Template repository, run the following. This will copy the lab pages to /var/www/html/<lab-name>, then builds and copy experiments listed in the lab-descriptor to /var/www/html/<lab-name>/<exp>.
	     
	     ` npm run labgen -- deploy <path/to/lab/repo> `
	     

### Commencing the (re)hosting request 

   VLEAD and the institute requesting the rehosting of Phase 3 lab while changing the content of the lab will follow the process detailed below- 
   

  - Step 1: 
  Institute requesting rehosting will follow the [link](https://github.com/virtual-labs/engineers-forum/issues) and locate the Phase III Lab/Experiment(s) OnBoarding Request issue corresponding to the lab that they  wish to edit.

  - Step 2: They will comment on the issue with the content that they like to add to the lab pages following the format - Lab Section Name - New content

  - Step 3: VLEAD's hosting engineer will host the lab with the requested changes and share the link on the same issue to seek approval from institute requesting rehosting. 

  - Step 4: Institute requesting rehosting will need to test the hosted link and on their approval the hosted link will be shared with IITD (to be added to vlab.co.in).

### (Re)Hosting Lab and Experiments
  In this section, we will discuss (re)hosting a Lab and Experiments.

  - Step 1: Check for [Phase-3-Lab-Template](https://github.com/virtual-labs/Phase-3-Lab-Template) and lab repo on the server.

  - Step 2: Look for the content to be updated(ie., lab or experiments).

  - Step 3:
   lab-descriptor.json has fields like 'deployLab' under lab name and 'deploy' under experiment. When these fields are set true, the particular lab or experiment will be deployed.

  - Step 4: 
  Mark the values as true or false in the <path/to/lab/repo>/lab-descriptor.json file(present in the lab repo) and create a pull-request to get the lab-descriptor approved.

  - Step 5: 
  After getting approval from the legitimate authority, generate lab, and build experiments.

  - Step 6: 
  From the Phase-3-Lab-Template repository, run the following. This will generate the lab pages using the verified lab-descriptor.json from the lab repository and push the generated content to remote.
	      
	     `npm run labgen -- generate <path/to/lab/repo>`
	      
  - Step 7: 
  Finally host lab and experiments. From the Phase-3-Lab-Template repository, run the following. This will copy the lab pages to /var/www/html/<lab-name>, then builds and copy experiments listed in the lab-descriptor to /var/www/html/<lab-name>/<exp>.
	      
	      ` npm run labgen -- deploy <path/to/lab/repo>`

### Steps for creating a new lab entry(Phase 3)
- Build and deploy sources to correct path i.e., (/var/www/html/example-lab) {Hosting Engineer}
- Check for example-lab and sources at /var/www/html/example-lab/ {Hosting Engineer}
- If step 1 and step 2 are true then go to step 4 else go to step 1 {Hosting Engineer}
- Hosting Engineer needs to raise a request to System Engineer
- Add entry to virtual host file in apache configuration(Phase3) {Systems Engineer}
- Reload the apache server {Systems Engineer}
- Add entry to ALB {Raj}
- Finally, add entry in DNS server {Systems Engineer}
- Reload DNS server {Systems Engineer}

#### NOTE
- Do not add entries without sources as it will create duplicate date in analytics.
- When modifying entries, try modifying before 9:00 AM or after 5:00 PM, it will give buffer time if something goes wrong and wont effect live users.

### Post Hosting Tasks
- In this section, we will look at the tasks to be done after hosting
  a unit,
- <strong> Task I - Testing </strong>
  - A quick SMOKE TEST to be performed on the hosted unit. We will
    talk about this in the next section.
- <strong>Task II - Updating hosting request</strong>
  - After successfuly hosting a unit, go to the hosting request and
    update the request with the following:
    + Hosted URL
    + Branch
    + Tag 
    + Approval

- <strong>Task III - Updating central hosting sheet</strong> 
  - Final task would be to update the [central hosting sheet](https://docs.google.com/spreadsheets/d/1WXJA_1QkLg-5S0YYBRKyhEXwOgTSbKvm972Fy-thCUc/edit#gid=129834454) with the
    following:
    + Hosted URL
    + Current Tag
    + Previous Tag
    + Hosting request date
    + Hosting Date
    + Link to Hosting Request
    + Requester
    + Status(Approval)
    + Number of Experiment
    + Added to analytics server 

### Instructions to fill the lab-descriptor while hosting
   The following are the instructions to fill or update the lab-descriptor.json file which is used to host a lab. Make Sure that everything in the JSON file is updated correctly before sending it for verification and hosting

#### Section I - Lab
	
   1. Name: Should be Discipline name  
   2. Link: - Crosscheck the discipline link from vlab.co.in and update correctly
   		<strong>- Discipline Should be in the following format:</strong>
			- Mechanical Engineering
			- Computer Science and Engineering
			- Electronics and Communication Engineering
			- Electrical Engineering
			- Civil Engineering
			- Chemical Sciences
			- Biotechnology and Biomedical Engineering
			- Physical Sciences
			- Chemical Engineering
			- Humanity
			- Metallurgical and Materials Engineering
			- Design Engineering
			- Aerospace Engineering

Lab Name: Should be same in the JSON file, GitHub repo name and in /var/www/html/

Phase: Should be the number that the lab belongs to Phase 3 or so
	
Deploy:  Should be true if we are hosting a lab and exp or only a lab. If we want to host only exp then it should be false
	
College Name(Institute Name): Update from the R0 file (which is given in the request for hosting issue)

The following are the supported institutes and their ids (to be given in the url along with the lab id. Ex:- cse01-iiith) 

- <strong> Institute Names and their Id’s:</strong>

	- IIITHyderabad - iiith
	- Amrita - au
		- IIT Delhi -iitd
		- IIT Kanpur - iitk
		- IIT Guwahati - iitg
		- IIT Roorkee - iitr
		- IIT Bombay - iitb
		- COEP -coep
		- Dayalbagh - dei 
		- IIT Kharagpur - iitkgp
		- NIT Karnataka -nitk

	Base URL: Crosscheck the lab domain in the reverse proxy and update correctly in the json
	
	Introduction: from R0 file 

#### Section II - Experiment
	
   1. Name: experiment name from R0 file
   2. Short Name: it should be in small letters and not more than 4 words or can give exp repo name from GitLab (if it has only 4 words)
   3. Repo: give the experiment repo URL from GitLab
   4. Tag: for every request for hosting, a repo should have a new tag
   5. Deploy: Should be true if we are hosting a lab and exp or only exp. If we want to host only lab then it should be false


#### Section III 
   Target Audience, Objective and Courses Alignment: Should be updated from the R0 file.

   - <strong>Recommendations</strong>

   - Condition 1: if we get a hosting request to update only the lab content, then a hosting person should host only the lab but not the experiments content. In the JSON file, deployLab should be true in the lab section and deploy should be false in the experiments section.

   - Condition 2:  if we get a hosting request to update only the experiment content, then a hosting person should host only the experiments but not the lab. In the JSON file, deployLab should be false in the lab section and deploy should be true in the experiments section.
	
   - Condition 3: If the lab is hosted multiple times with spelling mistakes or so, then the multiple labs will be created in the analytics and we will lose the lab/experiments usage.

   - Condition 4: After hosting the lab, test it thoroughly compared with analytics data.

#### Sample JSON file
```
{
  "broadArea": {
    "name": "Electronics and Communication Engineering",
    "link": "http://www.vlab.co.in/broad-area-electronics-and-communications"
  },
  "lab": "Digital Electronics IITR",
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

### Lifecycle of a Hosting Request
    
   - The hosting request will go through the following lifecycle:

   1.  Requester will raise a hosting request issue by duly filling in the details in the '[hosting request](https://github.com/virtual-labs/engineers-forum/issues/new/choose)'.
   2.  The hosting team will attach the url of the corresponding onboarding request to the hosting request. If the onboarding request is not found ( by searching on the repo url), then the hosting team will add its findings and label the issue as *Failed*.
   3.  If requester is not the repository owner, the hosting team will seek approval from the repository owner. This will be through the above created GitHub hosting request issue.
   4.  The hosting team will honour the hosting request only on receiving the approval from repository owner else will label the hosting request issue as *Not Approved* 
   5.  On a successful hosting, the hosting team will add the link of the newly hosted content to the hosting request issue. They will also label the issue as *Hosted*.
   6.  However, on failure ( because of missing or incorrect information or repository problems,), the hosting team will label the issue as *Failed*.
   7.  The requester will be responsible for fixing the failed hosting bug and will need to raise a new '[hosting request](https://github.com/virtual-labs/engineers-forum/issues/new/choose)' to get the unit hosted.
   8.  Once the hosting is successful, the requester will be responsible for the verification of the hosted link.  If the hosting is not as expected, the requester should change the label from *Hosted* to *Reopened*. The requester will also need to specify if he/she would like to revert to the previous hosted image.
   9.  An issue with *Reopened* label will by default host the repository and branch/tag as specified in the hosting request initially. However, if the requester has specifically requested a revert, the previously hosted image will be restored and issue will be labelled as *Reverted*.
   10.  If the requester wants to revert to any earlier branch/tag, a new '[hosting request](https://github.com/virtual-labs/engineers-forum/issues/new/choose)' will need to be raised to get the unit hosted.
   11. Requester will be responsible for closing a hosting request issue by changing the issue status from Open to Closed when the issue is labelled as *Hosted* or *Reopened* or *Reverted* or *Not Approved*.

### Labels & Status of a Hosting Request 

   At any given time a hosting issue should be marked with only one of the following labels. To change the label of an issue, the current label of the issue should be unchecked and the new label should be checked.

   *Hosted* :  This label indicates that the hosting request has been successful and the hosted url has been shared in the hosting request issue. This label is used only by the hosting team. 
   
   *Failed* : This label indicates that the hosting request has not been successful. This label is used only by the hosting team.

   *Reopened* : This label is used by the requester to indicate that the hosting url provided on a successful hosting of the hosting unit is not passing the validation.
   
   *Not Approved* : This label indicates that the hosting request issue raised by the requester was not approved by the Repository Owner.  This label is used only by the hosting team.
    
   *Reverted* :  This label indicates that the hosting request has been successfully revert to the previous hosted image. This label is used only by the hosting team. 
    
   Apart from the above mentioned labels a hosting request issue can either be in a closed or open status as provided by GitHub. 

   *Open* : This status indicates that a new hosting request issue has been raised and is waiting for the services of the hosting team. All issues are in this status when they are created on GitHub.

   *Closed* : This status indicates that a hosting request has been serviced by the hosting team and is labelled as *Hosted* or *Reopened* or *Reverted* or *Not Approved*.


## Process to be followed for creating of Experiment Repositories
   Steps to be followed by VLEAD's Hosting Engineer

   - Step 1 : </br>
   &nbsp;&nbsp;&nbsp;&nbsp; On receiving a [request](https://github.com/virtual-labs/engineers-forum/issues) for creation of experiment repositories for the lab, VLEAD's hosting engineer will create the experiment(s) repository from the [ph3-exp-template](https://github.com/virtual-labs/ph3-exp-template) repository.
               
   - Step 2 : </br>
   &nbsp;&nbsp;&nbsp;&nbsp; VLEAD's hosting engineer will create two branches - dev and testing from the main branch in the created experiment repositories.
              
              
   - Step 3 : </br>
   &nbsp;&nbsp;&nbsp;&nbsp; VLEAD's hosting engineer will add the Github Handle of the experiment developer provided in the request issue to the newly created experiment repository with maintainer access. VLEAD's hosting engineer will also add developer’s common email address to github notification center.

   - Step 4 : </br>
   &nbsp;&nbsp;&nbsp;&nbsp; VLEAD's hosting engineer will comment on the repository creation request providing the links to the created repositories. 


## Process to be followed for OnBoarding Request 
   VLEAD and the requesting institute follow the process detailed below for hosting of labs which have been developed with each experiment having its own repository. All the Phase 3 and above labs and experiments hosted on AWS will have a common UI  and report analytics at both lab and experiment level. 

  - Step 1 :
   &nbsp;&nbsp;&nbsp;&nbsp; IIITH will create lab repo for the lab that is ready ( marked in green) in the 200224_Deliverable_Status_Phase3 sheet shared by IITB and also populate the lab urls in the sheet.

  - Step 2 :
   &nbsp;&nbsp;&nbsp;&nbsp; Requesting institute will raise an issue of type Phase 3 Onboarding [Request](https://github.com/virtual-labs/engineers-forum/issues/new/choose) and fill the lab name and lab url ( as populated in the excel sheet by IIITH) and attach the R0 of the lab.

  - Step 3 :
   &nbsp;&nbsp;&nbsp;&nbsp; Requesting institute will tag the head of the master branch of all the experiments in that lab as mentioned in the 200224_Deliverable_Status_Phase3 as v1.0.0.

  - Step 4 :
   &nbsp;&nbsp;&nbsp;&nbsp; IIITH will populate the received Phase 3 Onboarding  [Request](https://github.com/virtual-labs/engineers-forum/issues/new/choose) with experiment details ( name, url, tag, branch and build command) and Owner details and request for approval from the requesting institute. It will be assumed by IIITH that no special hardware or software is required for the running of the experiments.  Requesting institute will have to specially state if this is not the case.

  - Step 5 :
   &nbsp;&nbsp;&nbsp;&nbsp; Requesting institute will validate the above data and approve the same on the received Phase 3 Onboarding [Request](https://github.com/virtual-labs/engineers-forum/issues/new/choose) .

  - Step 6 :
   &nbsp;&nbsp;&nbsp;&nbsp; On approval from requesting institute, IIITH will host all the experiments and populate the lab landing page information (Introduction, Objective, List of experiments, target audience, course alignment ) from the R0 shared by IITB in the Phase 3 Onboarding [Request](https://github.com/virtual-labs/engineers-forum/issues/new/choose).

  - Step 7 :
   &nbsp;&nbsp;&nbsp;&nbsp; IIITH will host the lab and share the hosted url link as part of the onboarding request issue and seek approval from the github handle of the owner of the lab ( as recorded in the onboarding request)

  - Step 8 :
   &nbsp;&nbsp;&nbsp;&nbsp; On approval from the Lab owner, IIITH will share the link with IIT Delhi.


### Rehosting Process for Phase III Lab 
   VLEAD and the institute requesting the rehosting of Phase
   3 lab while changing the content of the lab will follow
   the process detailed below- 
   

  - Step 1 :
   &nbsp;&nbsp;&nbsp;&nbsp; Institute requesting rehosting will follow the [link](https://github.com/virtual-labs/engineers-forum/issues) and locate the Phase III Lab/Experiment(s) OnBoarding Request issue corresponding to the lab that they  wish to rehost.

  - Step 2 :
   &nbsp;&nbsp;&nbsp;&nbsp; They will comment on the issue with the content that they like to add to the lab pages following the format - Lab Section Name - New content

  - Step 3 :
   &nbsp;&nbsp;&nbsp;&nbsp; VLEAD's hosting engineer will host the lab with the requested changes and share the link on the same issue to seek approval from institute requesting rehosting. 

  - Step 4 :
   &nbsp;&nbsp;&nbsp;&nbsp; Institute requesting rehosting will need to test the hosted link and on their approval the hosted link will be shared with IITD (to be added to vlab.co.in).


### Rehosting Process for Phase III Experiments    
   VLEAD and the institute requesting the rehosting of Phase 3 lab after changing the content of experiment will follow the process detailed below-

  - Step 1  :
   &nbsp;&nbsp;&nbsp;&nbsp; Institute requesting rehosting will make the necessary changes to the experiment content in the experiment repository on Github (virtual-labs organization) or GitLab (IITB server) as per the process followed during experiment development.  After they make the changes to the experiment sources , they will need to tag it.

  - Step 2 :
   &nbsp;&nbsp;&nbsp;&nbsp; Institute requesting will then follow the [link](https://github.com/virtual-labs/engineers-forum/issues) and locate the Phase III Lab/Experiment(s) OnBoarding Request issue corresponding to the lab containing the experiment that they wish to rehost.

  - Step 3 :
   &nbsp;&nbsp;&nbsp;&nbsp; Institute requesting will comment on the same Phase III Lab/Experiment(s) OnBoarding Request with the following text "Request to rehost the experiment <exp repo link> with the tag <tag number>". Institute requesting may include more than one experiment ( belonging to the same lab) rehosting request at a time.

  - Step 4 :
   &nbsp;&nbsp;&nbsp;&nbsp; VLEAD's hosting engineer will host the experiments and share the link on the same issue to seek approval from them.

  - Step 5 :
   &nbsp;&nbsp;&nbsp;&nbsp; Institute requesting rehosting will need to test the hosted link and comment on the same issue stating their approval.
