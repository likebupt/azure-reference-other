---
title: Azure Monitor Logs reference - WVDManagement
description: Reference for WVDManagement table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 9/17/2020
---

# WVDManagement

 Windows Virtual Desktop Management Activity

## Categories

- Windows Virtual Desktop
## Solutions

- LogManagement
## Resource types

- Desktop Virtualization workspaces
- Desktop Virtualization Host Pools
- Desktop Virtualization Application Groups




## Columns

|Column|Type|Description|
|---|---|---|
|CorrelationId|string|The activity Id.|
|ObjectsCreated|int|The number of objects that were created.|
|ObjectsDeleted|int|The number of objects that were deleted.|
|ObjectsFetched|int|The number of objects that were fetched.|
|ObjectsUpdated|int|The number of objects that were updated.|
|_ResourceId|string|A unique identifier for the resource that the record is associated with|
|Route|string|The route for the management request.|
|SourceSystem|string||
|TenantId|string||
|TimeGenerated|datetime|The timestamp (UTC) of the event.|
|Type|string|The name of the table|
|UserName|string|The user that initiated the management request.|
