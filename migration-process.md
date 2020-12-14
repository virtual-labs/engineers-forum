# Virtual Labs Experiment Repository Migration Process

## Introduction
  Virtual Labs is a mission mode project initiated by the
  Ministry of Human Resources and Development (MHRD). The
  objective of this project is to provide laboratory
  learning experience to the students who do not have access
  to adequate laboratory infrastructure. Currently there are
  around 90 labs developed by various institutes in the
  consortium.  A streamlined software development life cycle
  process followed for the development of these labs ensures
  high quality labs. This document defines the migration
  process to be followed by the developers (open source
  community) of the Virtual Labs project.

## Purpose
  This document defines the experiment migration process 
  that should be followed by the developers of the lab while
  migrating the source code to virtual-lab organization on GitHub.
  The roles and responsibilities of the various parties
  involved in the migration process is discussed in
  detailed in the document.
  
## Motivation
   Migrating the source code of the experiments to virtual-labs 
   organization on Github will help maintain a single, consolidated, 
   common, open source version controlled lab and experiment
   repositories.
   
## Audience
  The target audience for this document is the hosting team
  at CPE, IIITH and all the lab authors and owners who want
  to avail the migration service provided by Central Platform
  Engineering Team (CPE), IIITH team.
  

## Migrating Phase 3 experiment repository sources to virtual-labs GitHub organization 

   VLEAD and the institute requesting the migration of Phase
   3 experiment repository sources to virtual-labs 
   GitHub organization will follow the process detailed below- 
   
  - Step 1 : </br>
      &nbsp;&nbsp;&nbsp;&nbsp; Institute requesting movement will raise an [issue](https://github.com/virtual-labs/engineers-forum/issues/new?assignees=&labels=Phase-3%2C+create+experiment+repos&template=experiment-repository-creation-request.md&title=Experiment+Repository+Creation+Request+for+%3Cfill+the+lab+name+here%3E) to request creation of experiment repositories for the lab. 
  - Step 2 :</br>
      &nbsp;&nbsp;&nbsp;&nbsp; They will fill the information requested for on the issue and attach R0 ( proposal of the lab) 

  - Step 3 :</br>
      &nbsp;&nbsp;&nbsp;&nbsp; VLEAD's hosting engineer will create experiment repositories for each of the experiment on the proposal on Github and share the links of the created repositories on the same issue.

  - Step 4 :</br>
      &nbsp;&nbsp;&nbsp;&nbsp; Institute requesting migration will populate the dev branches of the created repositories with the source code of the experiments and unit test the experiments locally. Institure requesting migration should **not** delete gh-pages branch. This is required for automatically deploying the experiment along with UI on GitHub pages for testing the complete experiment . They should also not delete .github directory and the LICENSE file. 
              
  - Step 5 :</br>
      &nbsp;&nbsp;&nbsp;&nbsp; Institute requesting migration will merge the fully tested dev branch to testing branch. This will automatically deploy the experiment along with UI on GitHub pages for testing the complete experiment. The Institute requesting movement will receive an email about the success/failure of the deployment on the email id associated with the primary github handle provided in the issue.  
              
  - Step 6 :</br>
      &nbsp;&nbsp;&nbsp;&nbsp; Institute requesting migration will then merge  from a fully tested testing branch to the main branch and tag the commit. 
               
  - Step 7 :</br>
      &nbsp;&nbsp;&nbsp;&nbsp; Institute requesting rehosting will then follow the [link](https://github.com/virtual-labs/engineers-forum/issues) and locate the Phase III Lab/Experiment(s) OnBoarding Request issue corresponding to the lab that they  wish to rehost.  If such an issue does not exist they will create will raise an issue of type Phase 3 Onboarding [Request](https://github.com/virtual-labs/engineers-forum/issues/new/choose). In the issue, for each experiment they will provide the Experiment Name|Experiment Source Repo link|Tag . They will also attach the R0 of the lab to the issue if not already attached. 
              
  - Step 8 :</br>
      &nbsp;&nbsp;&nbsp;&nbsp; VLEAD's hosting engineer will host the experiments and the lab and share the link on the same issue to seek approval from them.

  - Step 9 :</br>
      &nbsp;&nbsp;&nbsp;&nbsp; Institute requesting migration  will need to test the hosted link and comment on the same issue stating their approval.


## Conclusion 
  This document highlights the process to be followed while migrating experiments source code to virtual-labs organization on GitHub. It aims at collaborating contributions of the developers across the open source platform - GitHub.

