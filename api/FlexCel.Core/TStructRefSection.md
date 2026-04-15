---
uid: TStructRefSection
description: TStructRefSection
---

# TStructRefSection Enumeration

This enum contains the possible values that can go into a structured reference\.
You can combine multiple values, but not all combinations make sense\. For example \#Data \+ \#Headers it fine, but \#All \+ \#Headers is just \#All\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|All|0|The structured reference applies to the whole table\. This is equivalent to \[\#All\]\.<br />|
|Headers|1|The structured reference applies to the headers of the table\. This is equivalent to \[\#Headers\]\.<br />|
|Data|2|The structured reference applies to data \(all the table without headers or totals\) of the table\. This is equivalent to \[\#Data\]\.<br />|
|Totals|3|The structured reference applies to the totals row of the table\. This is equivalent to \[\#Totals\]\.<br />|
|ThisRow|4|The structured reference applies to the row of the table where the reference is\. This is equivalent to @ or \[\#This row\]\.<br />|


