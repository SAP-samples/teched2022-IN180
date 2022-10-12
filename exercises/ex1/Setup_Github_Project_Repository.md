# Exercise 1 - Setup GitHub project with Integration Suite Piper commands

In this exercise, we will clone a session specific GitHub project repository, customize the project to include below details.
1. Inline scripting code using **Piper** shared library commands to automate various **Integration
   Suite** specific tasks.
2. Modify project manifest file to create instance of integration scenario based on user login information.

Finally we will commit the project to **GitHub** and use this in setting up **Jenkins** pipeline and **CI/CD** service repository in next part of the exercise.

## Exercise 1.1 Clone the Session repository from GitHub
1. Clone the Git repository using Git command - Open the console
and execute the below command.
```
git clone https://github.com/SAP-samples/teched2022-IN180.git
```
Once clone is Successful you can see the git repository in local filesystem
<br>![](/exercises/ex1/images/gitclone.png)

## Exercise 1.2 Adding the Inline Script logic which uses Integration Suite piper commands
1. Navigate to the IN180 directory from where you have cloned the git repository, you will see below structure.
  <br>![](/exercises/ex1/images/repoclonedir.png)
2. Edit the Jenkinsfile with any text editor and paste the below code

```
@Library('piper-lib-os') _

node() {
  stage('init') {
    deleteDir()
	checkout scm
	def folder = "<USERID>-flow4";
    def filePath = folder + ".zip";
    zip dir: folder, glob: '', zipFile: filePath;
  }
  stage('deployIntegrationArtifact and Get MPL Status') {
  	 setupCommonPipelineEnvironment script: this
	   integrationArtifactUpload script: this
     integrationArtifactDeploy script: this
	   integrationArtifactGetMplStatus script: this
	   print "MPL Status:"
	   print  commonPipelineEnvironment.getValue("integrationFlowMplStatus")
  }
}
```
>Replace the <'USERID'> with your tenant booker login user id and save the file.
for example, after replacement, code may look like below
```
	def folder = "I050368-flow4";
```
>Please save and close the file after modification.

Here in this script, stage('init') will prepare the integration flow zip archive,  integrationArtifactUpload piper command will upload the integration flow to the Cloud integration Designtime, integrationArtifactDeploy piper command would deploy the integration flow to runtime and integrationArtifactGetMplStatus piper command will check the integration scenario execution status.

## Exercise 1.3 Provide YAML configuration for Integration Suite Piper commands

1. Navigate to the .pipeline directory in the cloned the git repository
and edit the config.yml file.
2. insert below configuration, which has input parameters defined for each of the integration suite piper commands used.

```
steps:
  integrationArtifactDeploy:
    cpiApiServiceKeyCredentialsId: techedServiceKeyCred
    integrationFlowId: <USERID>-flow4
  integrationArtifactGetMplStatus:
    cpiApiServiceKeyCredentialsId: techedServiceKeyCred
    integrationFlowId: <USERID>-flow4
  integrationArtifactUpload:
    cpiApiServiceKeyCredentialsId: techedServiceKeyCred
    integrationFlowId: <USERID>-flow4
    integrationFlowName: <USERID>-flow4
    packageId: CICD
    filePath: <USERID>-flow4.zip
```
>Replace the <'USERID'> with your tenant booker login user id and save the file.
Replace techedServiceKeyCred with Cloud integration tenant name. The tenant name can be found in host part of the URL shown in the Tenant Booker Application.
Please note that, the Jenkins is already configured with credentials for the Tenant access (for example 'teched-eu01').

Please save and close the file after modification.

Here cpiApiServiceKeyCredentialsId provides the service key, which is configured in the Jenkins server as a secret text and its used  by the piper command to consume the Cloud integration Odata APIs.  
integrationFlowId provides unique ID of the integration flow, integrationFlowName provides the name of the integration flow and packageId talks about the name of the integration package in the cloud integration design time.

## Exercise 1.4 Rename the integration flow archive folder
Navigate to the directory where you have cloned the git repository and rename flow4 folder to <'USERID'>-flow4, where replace the <'USERID'>  with your login user id( for ex: I050368-flow4, where I050368 is your login id)
<br>![](/exercises/ex1/images/folderRename.png)

## Exercise 1.5 Modify the integration flow manifest file
Navigate to the directory where you have cloned the git repository and open the MANIFEST.MF file located in IN180/<'USERID'>-flow4/META-INF.
rename flow4  to <'USERID'>-flow4 for Bundle-SymbolicName, Origin-Bundle-SymbolicName, Origin-Bundle-Name, Bundle-Name attributes. here replace the <'USERID'>  with your login user id. save the manifest file.
after the change , it will look like below (assuming login id is I050368)

<br>![](/exercises/ex1/images/manifest.png)

## Exercise 1.6 Commit the GitHub repository
1. In your console, execute the following Git commands to create a new branch in the repository with your repo changes.

```
git init
git add -A
git config --global user.name "<USERID>"
git config --global user.email <USERID>@techedusers.com
git commit -m "IN180 Session Content"
git branch -M <USERID>
git push --set-upstream https://<Personal-access-token>@github.com/<GitHub-User>/IN180.git <USERID>
```
>Replace the <'USERID'> with your login user id.

Replace the <'Personal-access-token'> with the token you had created in the prerequisite section and <'GitHub-User'> with your GitHub account user name.

you can see that the commit was successful if your logs look like this:
 <br>![](/exercises/ex1/images/repoCommit.png)

3. You can also access the branch you created with the link https://github.com/<'GitHub-User'>/IN180/
<br>![](/exercises/ex1/images/sessionrepo.png)

## Summary

You've now successfully setup the GitHub repository which we will use in **Jenkins** pipeline and **SAP Continuous Integration and Delivery service** later.

Continue to - [Exercise 2 - Run the Integration Suite CI/CD pipeline using Jenkins Job](../ex2/Setup_Jenkins_Pipeline.md)
