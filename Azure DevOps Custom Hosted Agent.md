# Agenda
- Setting up Self-Hosted build host 

- Create your Personal Access Token [PAT]

- Enable System Assigned Managed Identity on Linux VM

- Create Role Assignment on your Azure Machine Learning Workspace

- Add Linux VM as Self-Hosted to Azure DevOps Agent

- Create Service Connection based on Managed Identity

- Configure your YML based Pipeline

# Setting up Self-Hosted build host 
Provision Windows [ Windows Server 2016 ] or Linux VM (Ubuntu 18.04 or 16.04 preferable) on Azure and install DevOps build Agent on this Linux VM.

While installing build agent , it will ask you for PAT [ Personal Access Token ] – refer next slide or below link on setting up build agent

Install all necessary software like Python 3+ [version > 3.6] libraries like Pandas, Numpy,  AzureML etc and restart your build agent in the Linux VM.

Select ‘Default’ as agent pool, while creating Build Agent. It will ask to place your build agent in which  Pool. 

Validate all necessary installations and configurations.

Installing Build Agent on Linux VM:   https://docs.microsoft.com/en-us/azure/devops/pipelines/agents/v2-linux?view=azure-devops


Check Python version on your Self-Hosted VM:
Go to Linux terminal and type 
Python -V

