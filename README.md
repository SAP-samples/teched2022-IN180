[![REUSE status](https://api.reuse.software/badge/github.com/SAP-samples/teched2022-IN180)](https://api.reuse.software/info/github.com/SAP-samples/teched2022-IN180)

# IN180 - Leveraging Commands from “Piper” for CI/CD Setup with SAP Integration Suite

## Description

In this session, you will learn how to use SAP Integration Suite Piper commands for building Continues integration and Continuous development pipeline. SAP Integration Suite has contributed many steps to the library for project ["**Piper**"](https://www.project-piper.io)  that help you create your own continuous integration (CI) and continuous deployment (CD) pipeline, automating various tasks. Learn how to set up CI/CD pipelines for SAP Integration Suite on Jenkins and [**Continuous Integration and Delivery service**](https://help.sap.com/docs/CICD_OVERVIEW).

## Overview

In this session you will learn how to set up a CI/CD pipeline for **SAP Integration Suite** in two ways:
1. Using a Jenkins instance and creating the pipeline yourself using **Piper** commands developed specifically for **SAP Integration Suite**.
2. Making use of SAP's [**Continuous Integration and Delivery service**](https://help.sap.com/docs/CICD_OVERVIEW), which has a ready-to-use pipeline for the **SAP Integration Suite** scenario.
 > INT180 Session presentation you can access [here](2022-SAP-TechEd-IN180.pdf)
## Requirements

The requirements to follow the exercises in this repository -  
- You are [familiar with **SAP Integration Suite**](https://help.sap.com/docs/SAP_CLOUD_PLATFORM_INTEGRATION_SUITE) and how it helps with enterprise-wide integration needs
- You have finished the [Prerequisites](/exercises/Prerequisites_for_IN180.md) section in the exercises
- You have looked through the following resources
  - [Overview of SAP Offerings for CI and CD](https://help.sap.com/docs/CICD_OVERVIEW/8cacec64ed854b2a88e9a0973e0f97a2/e9fa320181124fa9808d4446a1bf69dd.html)
  - [CI/CD for **SAP Integration Suite** using **Piper** Commands](https://blogs.sap.com/2021/06/02/ci-cd-for-sap-integration-suite-here-you-go/)
  - [CI/CD for **SAP Integration Suite** using the **SAP Continuous Integration and Delivery service**](https://blogs.sap.com/2021/08/27/sap-continuous-integration-and-delivery-for-sap-integration-suite-artifacts/)

## Integration Scenario Details
This session uses very simple integration flow. This integration flow has a timer start and hence it will be executed on deployment.
<br>![](/exercises/images/Scenario.png)
## Exercises

You can use this section as an index or table of contents. All pages have a link on top of the page to **Go back to Table of Contents** for easy navigation.

### [Prerequisites](/exercises/Prerequisites_for_IN180.md)
- [Check that git command line tool is installed](/exercises/Prerequisites_for_IN180.md#install-git-command-line-tool-by-following-the-steps-mentioned-in-this-tutorial)
- [Book the Integration Suite Tenant](/exercises/Prerequisites_for_IN180.md#book-integration-suite-tenant-by-using-the-tenant-booker-app-login--book-tenant)
- [Setup GitHub Account](/exercises/Prerequisites_for_IN180.md#setup-github-account)

### [Exercise 1 - Setup GitHub project with Integration Suite piper commands](exercises/ex1/Setup_Github_Project_Repository.md)
- [Exercise 1.1 - Clone the Session repository from GitHub](exercises/ex1/Setup_Github_Project_Repository.md#exercise-11-clone-the-session-repository-from-github)
- [Exercise 1.2 - Adding the Inline Script logic which uses Integration Suite Piper commands](exercises/ex1/Setup_Github_Project_Repository.md#exercise-12-adding-the-inline-script-logic-which-uses-integration-suite-piper-commands)
- [Exercise 1.3 - Provide YAML configuration for Integration Suite Piper commands](exercises/ex1/Setup_Github_Project_Repository.md#exercise-13-provide-yaml-configuration-for-integration-suite-piper-commands)
- [Exercise 1.4 - Rename the integration flow archive folder](exercises/ex1/Setup_Github_Project_Repository.md#exercise-14-rename-the-integration-flow-archive-folder)
- [Exercise 1.5 - Modify the integration flow manifest file](exercises/ex1/Setup_Github_Project_Repository.md#exercise-15-modify-the-integration-flow-manifest-file)
- [Exercise 1.6 - Commit the GitHub repository](exercises/ex1/Setup_Github_Project_Repository.md#exercise-16-commit-the-github-repository)


### [Exercise 2 - Run the Integration Suite CI/CD pipeline using Jenkins Job](exercises/ex2/Setup_Jenkins_Pipeline.md)
- [Exercise 2.1 - Setup Jenkins Pipeline for the Git repository](exercises/ex2/Setup_Jenkins_Pipeline.md#exercise-21-setup-jenkins-pipeline-for-the-git-repository)
- [Exercise 2.2 - Build the Jenkins Pipeline and evaluate results](exercises/ex2/Setup_Jenkins_Pipeline.md#exercise-22-build-the-jenkins-pipeline-and-evaluate-results)
- [Exercise 2.3 - Verify the results in the Integration Suite Tenant](exercises/ex2/Setup_Jenkins_Pipeline.md#exercise-23-verify-the-results-in-the-integration-suite-tenant)

### [Exercise 3 - Setup Git repository for CI/CD Service](exercises/ex3/Setup-Git-repository-for-CICD-Service.md)
- [Exercise 3.1 - Clean up Integration artifacts generated from Integration Suite CI/CD pipeline](exercises/ex3/Setup-Git-repository-for-CICD-Service.md#exercise-31-clean-up-integration-artifacts-generated-from-integration-suite-cicd-pipeline)
- [Exercise 3.2 - Commit to GitHub repository](exercises/ex3/Setup-Git-repository-for-CICD-Service.md#exercise-32-commit-to-github-repository)

### [Exercise 4 -  Run the SAP Continuous Integration and Delivery service job for Integration Suite](exercises/ex4/Run-the-Integration-Suite-CICD-job.md)
- [Exercise 4.1 - Setup CICD service Job for the Integration Suite Artifacts](exercises/ex4/Run-the-Integration-Suite-CICD-job.md#exercise-41-setup-cicd-service-job-for-the-integration-suite-artifacts)
- [Exercise 4.2 - Trigger the CI/CD service JOB and evaluate results](exercises/ex4/Run-the-Integration-Suite-CICD-job.md#exercise-42-trigger-the-cicd-service-job-and-evaluate-results)
- [Exercise 4.3 - Verify the CI/CD job execution in the Integration Suite Tenant](exercises/ex4/Run-the-Integration-Suite-CICD-job.md#exercise-43-verify-the-cicd-job-execution-in-the-integration-suite-tenant)

## How to obtain support

Support for the content in this repository is available during the actual time of the online session for which this content has been designed. Otherwise, you may request support via the [Issues](../../issues) tab.

## License
Copyright (c) 2022 SAP SE or an SAP affiliate company. All rights reserved. This project is licensed under the Apache Software License, version 2.0 except as noted otherwise in the [LICENSE](LICENSES/Apache-2.0.txt) file.
