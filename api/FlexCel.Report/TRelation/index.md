---
uid: TRelation
description: TRelation
---

# TRelation Class

A data relation between two tables\. Different from standard \.NET datarelations, this class is not tied to ADO\.NET, and allows you to specify relationships between any arbitrary VirtualDataTable objects\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">TRelation = class(TFlexCelObject);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new relation with the given values\.<br />|


## Properties

|Name|Description|
|---|---|
|[ParentColumns](ParentColumns.md)|And array of colum indexes on the Master table that are related to the detail ChildColumns\[0\] is related to ParentColumns\[0\], ChildColumns\[1\] to ParentColunns\[1\], and so on\.<br />|
|[ChildColumns](ChildColumns.md)|And array of colum indexes on the Detail table that are related to the master\.<br />ChildColumns\[0\] is related to ParentColumns\[0\], ChildColumns\[1\] to ParentColunns\[1\], and so on\.<br />|
|[ParentTable](ParentTable.md)|Table that acts as a master on a Master\-Detail relationship\.<br />|
|[ChildTable](ChildTable.md)|Table that acts as a detail on a Master\-Detail relationship\.<br />|


