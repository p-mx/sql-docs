---
title: Manage databases with Azure Automation
description: Learn about how the Azure Automation service can be used to manage Azure SQL Database at scale.
author: WilliamDAssafMSFT
ms.author: wiassaf
ms.reviewer: randolphwest, mathoma
ms.date: 08/24/2023
ms.service: sql-database
ms.subservice: deployment-configuration
ms.topic: conceptual
ms.custom: sqldbrb=1
---

# Manage databases in Azure SQL Database by using Azure Automation

[!INCLUDE [appliesto-sqldb](../includes/appliesto-sqldb.md)]

> [!div class="op_single_selector"]
> * [Azure SQL Database](automation-manage.md?view=azuresql-db&preserve-view=true)
> * [Azure SQL Managed Instance](../managed-instance/automation-manage.md?view=azuresql-mi&preserve-view=true)

This guide introduces you to the Azure Automation service, and how it can be used to simplify the management of databases in Azure SQL Database.

## About Azure Automation

[Azure Automation](https://azure.microsoft.com/services/automation/) is an Azure service for simplifying cloud management through process automation. Using Azure Automation, long-running, manual, error-prone, and frequently repeated tasks can be automated to increase reliability, efficiency, and time to value for your organization. For information on getting started, see [Azure Automation intro](/azure/automation/automation-intro).

Azure Automation provides a workflow execution engine with high reliability and high availability, and that scales to meet your needs as your organization grows. In Azure Automation, processes can be kicked off manually, by third-party systems, or at scheduled intervals so that tasks happen exactly when needed.

Lower operational overhead and free up IT / DevOps staff to focus on work that adds business value by moving your cloud management tasks to be run automatically by Azure Automation.

## How Azure Automation can help manage your databases

With Azure Automation, you can manage databases in Azure SQL Database by using the [latest Az PowerShell cmdlets](/powershell/azure/install-azure-powershell) that are available in [Azure Az PowerShell](/powershell/azure/new-azureps-module-az). Azure Automation has these Azure Az PowerShell cmdlets immediately available, so that you can perform all of your SQL Database management tasks within the service. You can also pair these cmdlets in Azure Automation with the cmdlets for other Azure services, to automate complex tasks across Azure services and across third-party systems.

Azure Automation also has the ability to communicate with Azure SQL logical servers directly, by issuing SQL commands using PowerShell.

The runbook and module galleries for [Azure Automation](/azure/automation/automation-runbook-gallery) offer a variety of runbooks from Microsoft and the community that you can import into Azure Automation. To use one, download a runbook from the gallery, or you can directly import runbooks from the gallery, or from your Automation account in the Azure portal.

For a tutorial, see [Manage databases in Azure SQL Database using Azure Automation](/azure/automation/manage-sql-server-in-automation).

>[!NOTE]
> The Automation runbook may run from a range of IP addresses at any datacenter in an Azure region. To learn more, see [Automation region DNS records](/azure/automation/how-to/automation-region-dns-records).

## Authentication via managed identities

On 30 September 2023, Azure Automation Classic Run As accounts will be retired. Instead, use managed identities for authentication for existing and new runbooks. Managed identities provide the same functionality as Run As accounts, plus:

- Secure authentication to any Azure service that supports Azure Active Directory (Azure AD) authentication.
- Minimized management overhead with easy access to resources.
- Simplified runbooks with no requirement to use multi-line code.

Since April 2023, the creation of new Run As accounts in Azure Automation is no longer possible.

For more information on this required action, visit [Migrate from an existing Run As account to Managed Identities](/azure/automation/migrate-run-as-accounts-managed-identity?tabs=run-as-account).

## Other automation methods

Instead of SQL Agent, Azure SQL Database can use an [elastic job agent](elastic-jobs-overview.md) to execute T-SQL statements on a schedule. For more information on the differences between SQL Agent and elastic jobs, see [Automate management tasks in Azure SQL](job-automation-overview.md).

## Next steps

For a tutorial and samples, see [Manage databases in Azure SQL Database using Azure Automation](/azure/automation/manage-sql-server-in-automation).

Now that you've learned the basics of Azure Automation and how it can be used to manage Azure SQL Database, follow these links to learn more about Azure Automation:

- [Azure Automation Overview](/azure/automation/automation-intro)
- [My first runbook](/azure/automation/learn/powershell-runbook-managed-identity)