---
title: "Exabeam Advanced Analytics connector for Microsoft Sentinel"
description: "Learn how to install the connector Exabeam Advanced Analytics to connect your data source to Microsoft Sentinel."
author: cwatson-cat
ms.topic: how-to
ms.date: 02/23/2023
ms.service: microsoft-sentinel
ms.author: cwatson
---

# Exabeam Advanced Analytics connector for Microsoft Sentinel

The [Exabeam Advanced Analytics](https://www.exabeam.com/ueba/advanced-analytics-and-mitre-detect-and-stop-threats/) data connector provides the capability to ingest Exabeam Advanced Analytics events into Azure Sentinel. Refer to [Exabeam Advanced Analytics documentation](https://docs.exabeam.com/) for more information.

## Connector attributes

| Connector attribute | Description |
| --- | --- |
| **Kusto function alias** | ExabeamEvent |
| **Kusto function url** | https://aka.ms/sentinel-Exabeam-parser |
| **Log Analytics table(s)** | Syslog (Exabeam)<br/> |
| **Data collection rules support** | [Workspace transform DCR](../../azure-monitor/logs/tutorial-workspace-transformations-portal.md) |
| **Supported by** | [Microsoft Corporation](https://support.microsoft.com) |

## Query samples

**Top 10 Clients (Source IP)**
   ```kusto
ExabeamEvent
 
   | summarize count() by SrcIpAddr
 
   | top 10 by count_
   ```



## Vendor installation instructions


> [!NOTE]
   >  This data connector depends on a parser based on a Kusto Function to work as expected. [Follow these steps](https://aka.ms/sentinel-Exabeam-parser) to create the Kusto Functions alias, **ExabeamEvent**


> [!NOTE]
   >  This data connector has been developed using Exabeam Advanced Analytics i54 (Syslog)

1. Install and onboard the agent for Linux or Windows

Install the agent on the server where the Exabeam Advanced Analytic logs are generated or forwarded.

> Logs from Exabeam Advanced Analytic deployed on Linux or Windows servers are collected by **Linux** or **Windows** agents.




2. Configure the logs to be collected

Configure the custom log directory to be collected


3. Configure Exabeam event forwarding to Syslog

[Follow these instructions](https://docs.exabeam.com/en/advanced-analytics/i56/advanced-analytics-administration-guide/125371-configure-advanced-analytics.html#UUID-6d28da8d-6d3e-5aa7-7c12-e67dc804f894) to send Exabeam Advanced Analytics activity log data via syslog.



## Next steps

For more information, go to the [related solution](https://azuremarketplace.microsoft.com/en-us/marketplace/apps/azuresentinel.azure-sentinel-solution-exabeamadvancedanalytics?tab=Overview) in the Azure Marketplace.
