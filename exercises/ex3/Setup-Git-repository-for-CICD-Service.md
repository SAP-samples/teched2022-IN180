# Exercise 3 - Setup Git repository for CI/CD Service  

In this exercise, we will prepare the Git repository for SAP Continuous Integration and Delivery service repository.

## Exercise 3.1 Clean up Integration artifacts generated from Integration Suite CI/CD pipeline

After completing these steps you will have cleaned up design time and runtime artifacts from the Integration Suite tenant.

1. Select monitoring and deployed artifacts
<br>![](/exercises/ex3/images/MonitorDeployedArtifacts.png)

2.	Search Integration flow by Login user id and Un-deploy it.
<br>![](/exercises/ex3/images/undeploy.png)

3. Navigate to CI/CD package in Design time and search of Integration flow by your login user id,  which was created by you in previous exercise. delete the integration flow.  
<br>![](/exercises/ex3/images/DeleteIflow.png)

>Please note that user has to go to Edit mode in the package to be able to delete the flow

## Exercise 3.2 Commit to GitHub repository
1. Navigate to the directory where you have cloned the git repository and change directory to <'USERID'>-flow4 in the console
<br>![](/exercises/ex3/images/NavigateToIflowDir.png)

>Execute below Git commands.

```
git init
git add -A
git config --global user.name "<USERID>"
git config --global user.email <USERID>@techedusers.com
git commit -m "IN180 Session Content"
git branch -M <USERID>-CICD
git push --set-upstream https://<Personal-access-token>@github.com/<GitHub-User>/IN180.git <USERID>-CICD
```
Replace the <'Personal-access-token'> with the token you had created in the prerequisite section and <'GitHub-User'> with your GitHub account user name.
>you can see that commit should be Successful as you see below
 <br>![](/exercises/ex3/images/repocommit.png)

2. You can also access the committed repository in the link https://github.com/teched2022demo/IN180/tree/<'USERID'>-CICD

## Summary

You've now Successfully setup the GitHub repository which we use in  **CI/CD** service in next Exercise.

Continue to - [Exercise 4 - Run the SAP Continuous Integration and Delivery service job for Integration Suite](../ex4/Run-the-Integration-Suite-CICD-job.md)
