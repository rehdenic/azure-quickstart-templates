---
description: This template creates a resource group with a storage account, Azure Synapse, and Apache Spark Pools to enable a Data Lakehouse lab environment. This template was modified in a fork from its original version that can be found under https://github.com/Azure/azure-quickstart-templates to suit the Data Lake Workshop performed at the Swiss Data Science Conference by Allgeier (Schweiz) AG
---
# SDS Workshop Lab Setup - Azure Synapse Data Lakehouse

[![Deploy To Azure](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazure.svg?sanitize=true)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Falxdean%2Fazure-quickstart-templates%2Fmaster%2Fquickstarts%2Fmicrosoft.synapse%2Fsynapse-poc%2Fazuredeploy.json) 

![Synapse Analytics](images/synapse1.png)

This template deploys necessary resources to run an Azure Synapse Data Lakehouse environment. 

This template deploys the following:

- An Azure Synapse Workspace
  - (OPTIONAL) Allows All connections in by default (Firewall IP Addresses)
  - Allows Azure Services to access the workspace by default  
- Apache Spark Pool
  - Auto-paused set to 15 minutes of idling
- Azure Data Lake Storage Gen2 account
  - Azure Synapse Workspace identity given Storage Blob Data Contributor to the Storage Account
    - A new File System inside the Storage Account to be used by Azure Synapse
- Grants the Workspace identity CONTROL to all SQL pools and SQL on-demand pool

## Purpose

This template allows the attendee to deploy a Proof-of-Concept environment of Azure Synapse Analytics with some pre-set parameters. This allows more time to focus on the labs at hand and learn about Data Lakehouse concepts.


## Prerequisites

- Owner to the Azure Subscription being deployed. This is for creation of a separate Proof-of-Concept Resource Group and to delegate roles necessary for this proof of concept

`Tags: Microsoft.Resources/deployments, Microsoft.Storage/storageAccounts, blobServices/containers, Microsoft.Synapse/workspaces, SystemAssigned, firewallrules, managedIdentitySqlControlSettings, Microsoft.Synapse/workspaces/bigDataPools, Microsoft.Authorization/roleAssignments, InitializeVariable, Object, Integer, Http, ManagedServiceIdentity, ParseJson, , string, If, Until, SetVariable, Wait, Recurrence, `
