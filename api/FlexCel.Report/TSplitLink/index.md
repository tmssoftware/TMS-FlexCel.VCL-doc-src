---
uid: TSplitLink
description: TSplitLink
---

# TSplitLink Class

Specifies a "Split" relation between two tables\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">TSplitLink = class(TFlexCelObject);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Create a new TSplitLink with the given values\.<br />|


## Properties

|Name|Description|
|---|---|
|[SplitCount](SplitCount.md)|Split the detail every "SplitCount" number of records\. If for example Splitcount is 5 and  the detail table has 14 registers, it should be split as 5 records, 5 records, 4 records\.<br />|
|[ParentDataSource](ParentDataSource.md)|Table that acts as a parent on the split relationship\. Read its [TVirtualData&#8203;Table&#8203;State.&#8203;Position](../TVirtualDataTableState/Position.md) to know which group of splitted records to return\.<br />|


