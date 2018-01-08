---
title: "COUNT (Azure Stream Analytics) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-10-02"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "stream-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
applies_to: 
  - "Azure"
ms.assetid: 494f899f-2ea7-4990-9a65-3881d9995b33
caps.latest.revision: 11
author: "SnehaGunda"
ms.author: "sngun"
manager: "jhubbard"
---
# COUNT (Azure Stream Analytics)
  Returns the number of items in a group. COUNT always returns a bigint data type value.  
  
 **Syntax**  
  
```  
COUNT ( { [ [ALL | DISTINCT] expression ] | * } ) 
  
```  
  
## Arguments  
**ALL**

Applies the aggregate function to all values. ALL is the default.

**DISTINCT**

Specifies that COUNT returns the number of unique non-null values.

 **expression**  
  
 Is an expression of any type or a column name. Aggregate functions and sub queries are not permitted.  
  
 **\***  
  
Specifies that all events should be counted to return the total number of events in a group. COUNT(**\***) takes no parameters. COUNT(**\***) does not require an expression parameter because, by definition, it does not use information about any particular column. COUNT(**\***) returns the number of events without getting rid of duplicates. It counts each event separately. This includes events that contain null values.

## Remarks

 - COUNT(*) returns the number of events including NULL values and duplicates.

 - COUNT(ALL expression) and COUNT(expression) evaluates expression for each event in a group and returns the number of non-null values.

 - COUNT(DISTINCT expression) evaluates expression for each event in a group and returns the number of unique, non-null values.
 - COUNT(input_stream) is equivalent to COUNT() and COUNT(*), but COUNT(DISTINCT input_stream) counts only unique events.

  
## Return Types  
 bigint  
  
## Examples  

```  
SELECT System.TimeStamp AS OutTime, TollId, COUNT(*)   
FROM Input TIMESTAMP BY EntryTime  
GROUP BY TollId, TumblingWindow(minute,3)  
  
```  
  
  