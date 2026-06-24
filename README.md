# Project-04--azure-monitoring-log-analytics-project

# Azure Monitoring, Log Analytics, Event Hub & Stream Analytics Project

## Project Overview

This project demonstrates centralized monitoring and log collection for Azure Virtual Machines deployed across multiple Azure regions.

## Architecture

* 2 Azure Virtual Machines (Different Regions)
* Azure Monitor
* Log Analytics Workspace (LAW)
* Event Hub Namespace
* Azure Stream Analytics
* Azure Storage Account

## Objectives

* Centralize logs from multiple Azure VMs
* Monitor VM health and activity
* Send logs to Log Analytics Workspace
* Stream logs through Event Hub
* Archive logs in Storage Account
* Query logs using KQL

## Resources Created

1. Resource Group
2. Log Analytics Workspace
3. Event Hub Namespace & Event Hub
4. Azure Stream Analytics Job
5. Storage Account
6. Virtual Machine - Region 1
7. Virtual Machine - Region 2

## Configuration Steps

### Step 1: Create Log Analytics Workspace

Created a centralized workspace for log collection.

### Step 2: Create Event Hub

Configured Event Hub to receive diagnostic logs.

### Step 3: Create Storage Account

Configured Storage Account for log archival.

### Step 4: Enable Diagnostic Settings

Configured both VMs to send logs to:

* Log Analytics Workspace
* Event Hub
* Storage Account

### Step 5: Configure Stream Analytics

Connected Event Hub as input source and verified incoming logs.

### Step 6: Verify Log Collection

Executed KQL queries in Log Analytics Workspace.

## Sample KQL Queries

### VM Heartbeat

```kusto
Heartbeat
| summarize LastHeartbeat=max(TimeGenerated) by Computer
```

### Event Logs

```kusto
Event
| where TimeGenerated > ago(24h)
| project TimeGenerated, Computer, EventLevelName
```

## Skills Demonstrated

* Azure Monitor
* Log Analytics Workspace
* Event Hub
* Azure Stream Analytics
* Azure Storage Account
* Azure Virtual Machines
* Diagnostic Settings
* KQL Queries
* Multi-Region Monitoring

## Outcome

Successfully implemented centralized monitoring for Azure Virtual Machines deployed across different Azure regions and validated log ingestion through Log Analytics Workspace, Event Hub, and Storage Account.
