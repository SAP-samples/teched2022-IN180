# Exercise 4 - Run the SAP Continuous Integration and Delivery service job for Integration Suite

In this exercise, we will create and run the SAP Continuous Integration and Delivery service job. this job will upload the integration flow in to SAP cloud integration Design time, deploy to the runtime and get the runtime execution status.

## Exercise 4.1 Setup CICD service Job for the Integration Suite Artifacts

1. Login to the SAP Continuous Integration and Delivery service using [instructor provided URL](https://techedio2019.cicd.cfapps.eu10.hana.ondemand.com/ui/index.html) and tenant booker app generated login credentials.
<br>![](/exercises/ex4/images/cicdLogin.png)

2. Click on Repositories tab and add new repository.
<br>![](/exercises/ex4/images/createRepo.png)

3. Provide repository details and remove the WEBHOOK Event Receiver.
```
Name = <USERID>-CICD
Clone URL = https://github.com/<'GitHub-User'>/IN180.git
```
Remove WEBHOOK Event Receiver
<br>![](/exercises/ex4/images/RemoveWebhook.png)
>Repository configuration
<br>![](/exercises/ex4/images/repodetails.png)

 >click on **Add** button which will create a new repository.

4. Navigate to Jobs Tab and create a new job
<br>![](/exercises/ex4/images/JobsTab.png)

5. Creating a new SAP Continuous Integration and Delivery job with  generic details as shown below
```
Job Name = <USERID>-Job
Branch = <USERID>-CICD
Repository = <USERID>-CICD
Pipeline = SAP Integration Suite Artifacts
```
<br>![](/exercises/ex4/images/cicdjobcreate.png)
>Note:- Replace <'USERID'> with your login user id.

6. Provide the job configuration for SAP Integration Suite pipeline General Parameters.  
```
Flow ID = <USERID>-flow4
Design Time Authentication = techedServiceKeyCred
```
<br>![](/exercises/ex4/images/generalparameters.png)
>Note:- Replace <'USERID'> with your login user id.
>Replace techedServiceKeyCred with Cloud integration tenant name.
Please note that, the CI/CD Service is already configured with credentials for the Tenant access (for example 'teched-eu01').

7. Turn on the Upload and Deploy command and provide the configuration.
```
Flow Name = <USERID>-flow4
Package ID = CICD
```
<br>![](/exercises/ex4/images/createjob.png)

>Click on **Create** to create a new CI/CD job.

## Exercise 4.2 Trigger the CI/CD service JOB and evaluate results
1. Select the CI/CD Job you have just created and trigger the build
<br>![](/exercises/ex4/images/triggerJob.png)

2. All the Steps or Stages in the job should be Successfully completed
 <br>![](/exercises/ex4/images/jobcomplete.png)

3. You can also verify the Job execution log for more details.
<br>![](/exercises/ex4/images/joblog.png)

## Exercise 4.3 Verify the CI/CD job execution in the Integration Suite Tenant

After completing above steps, we can verify in the integration suite tenant that Integration flow artifact created in the Design time , also deployed in the runtime and in the message monitoring status its execution is successful


1. Login to the SAP Cloud integration tenant with tenant booker app provided credentials.
>Tenant Booker Application
<br>![](/exercises/ex2/images/TenantBooker.png)
>SAP Integration Suite Tenant
<br>![](/exercises/ex2/images/cpilogin.png)

2. In the design time search and open the package **CICD**, move to the tab Artifacts and verify that your user-specific flow was created.
<br>![](/exercises/ex2/images/designtime.png)

3. Select Manage Integration Content under monitoring integration scenarios.
<br>![](/exercises/ex2/images/manageIntegrationContent.png)

4. Verify in the runtime for deployed integration artifacts, integration flow deployed or not!.
 <br>![](/exercises/ex2/images/runtime.png)

5. First click on Monitor Message processing link for deployed integration artefact
<br>![](/exercises/ex2/images/MonitorMessageProcessing.png)

6. Finally we can check the Message monitoring for the execution status of the integration flow.
<br>![](/exercises/ex2/images/messagemonitor.png)

## Summary

You've now successfully created/executed an SAP Continuous Integration and Delivery service job for integration Suite, automating various tasks such as Upload, Deploy and Message Monitoring Status check.
