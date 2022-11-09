# Exercise 2 - Run the Integration Suite CI/CD pipeline using Jenkins Job

In this exercise, we will create a Jenkins pipeline and execute it. this pipeline will upload the integration flow in to SAP cloud integration Design time, deploy to the runtime and get the runtime execution status.  

## Exercise 2.1 Setup Jenkins Pipeline for the Git repository

1. Login to the Jenkins service using [instructor provided URL](http://3.234.60.205:8080/) and tenant booker app generated login credentials.
<br>![](/exercises/ex2/images/JenkinsLogin.png)
>Select **New Item**

2. Create new pipeline item using **+ New Item** Option. provide the pipeline name and select Pipeline. name will be <'USERID'>-IN180, where user id is your login user id as shown in below example. Click on **ok** to complete pipeline creation.
<br>![](/exercises/ex2/images/createpipeline.png)

3. Provide the pipeline configuration, where Definition as "Pipeline script from SCM", SCM option as "GIT" and Repository URL, i.e. https://github.com/<'GitHub-User'>/IN180.git as shown below.
  <br>![](/exercises/ex2/images/pipelineConfig.png)
 >Replace <'GitHub-User'> with your GitHub account user name.
4. Also provide the Branch specifier as your login user id and save the pipeline
  <br>![](/exercises/ex2/images/branchSpecifier.png)

## Exercise 2.2 Build the Jenkins Pipeline and evaluate results
After completing these steps you will have **Integration Suite** specific piper steps are executed, that have been configured in the config.yml file.

1. Click on build now , which will start executing the integration suite piper commands after downloading git repository in to Jenkins workspace.
  <br>![](/exercises/ex2/images/pipelineBuild.png)

2.	Click on the console output to understand the Jenkins Job execution flow
  <br>![](/exercises/ex2/images/consoleResults.png)

3. Verify the Integration Flow Execution Result - In the console you can verify last configured integration suite piper command execution result (i.e. integrationArtifactGetMplStatus command)
  <br>![](/exercises/ex2/images/mplstatus.png)


## Exercise 2.3 Verify the results in the Integration Suite Tenant

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

You've now successfully executed an CI/CD job for integration Suite,  automating various tasks such as Upload, Deploy and Message Monitoring Result check.

Continue to - [Exercise 3 - Setup Git repository for CI/CD Service](../ex3/Setup-Git-repository-for-CICD-Service.md)
