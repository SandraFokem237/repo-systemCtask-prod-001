---
page_type: task assignment
description: "Create and test an Azure App Service with App Insights and Storage using ARM"
products:
- Azure App service
- App Insights
- Storage Account
- GitHub Actions
languages:
- dotnet
---
# Sample ASP.NET Core application using GitHub Actions for CI/CD workflow and Azure Load testing for test automation

# Steps to create an a web app and use Github Actions for CI/CD Workflow

## Pre-requisites
* Create a new Web App in Azure Portal with runtime stack as .NET and OS as Windows
* Local code
* Github repository linked to the local code
* Copy Publish Profile Settings of the app

### Create an ASP.NET App Service in Azure

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2Fazure-quickstart-templates%2Fmaster%2F101-webapp-windows-ASPNET%2Fazuredeploy.json" target="_blank">
    <img src="https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazure.png"/>
</a>
<a href="http://armviz.io/#/?load=https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2Fazure-quickstart-templates%2Fmaster%2F101-webapp-windows-ASPNET%2Fazuredeploy.json" target="_blank">
    <img src="https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/visualizebutton.png"/>
</a>

This template deploys a web app with ASP.NET support. The web app with ASP.NET is an app service that allows you to deploy your ASP.NET website. This will deploy a free tier Windows App Service Plan where you will host your App Service.
And should look like this
![intial web app](https://github.com/SandraFokem237/repo_systemCtask_prod_001/assets/145476727/a2efe861-4bd0-4ab9-b2d6-1da04e2d5a7f)

## Configure secrets in the GH repo:
* In the GH repo with Application code, [Define a new secret](https://github.com/Azure/actions-workflow-samples/blob/master/assets/create-secrets-for-GitHub-workflows.md) under repository by navigating to **settings** > **secrets** > **Add a new secret** 
* Paste the contents for the downloaded publish profile file into the secret's value field
* Now in the workflow file in your branch: `.github/workflows/workflow.yml` replace the secret for the input `publish-profile:` of the deploy Azure WebApp action

## test your workflow
* Commit a change in the app code. 
* You should see a new GitHub Action initiated in **Actions** tab.
* At the end of the execution, navigate to the App URL to visualise the change introduced.

## new web with local code for this assignment
![image](https://github.com/SandraFokem237/repo_systemCtask_prod_001/assets/145476727/7ce2d3e7-baf7-47ed-9b0c-ac22cc44b9a9)

