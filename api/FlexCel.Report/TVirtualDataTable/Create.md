---
uid: TVirtualDataTable.Create
description: TVirtualDataTable.Create
---

# TVirtualDataTable\.Create Constructor

Creates a new virtual datatable instance and assigns a name to it\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TVirtualDataTable/index.md">TVirtualDataTable</a>.Create(const aTableName: string; const aCreatedBy: <a href="../TVirtualDataTable/index.md">TVirtualDataTable</a>);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aTableName**|string|Name for the virtual data table\. Note that this name is \*not\* used anywhere in FlexCel code, except to report errors\.<br />The Table names that are used on reports are the ones in [TVirtualDataTableState](../TVirtualDataTableState/index.md)|
|const|**aCreatedBy**|[TVirtualDataTable](../TVirtualDataTable/index.md)|Table that created this table \(via a filter, distinct, etc\), or null if this table wasn't created from another VirtualDataTable\.|


## See also

* [TVirtualDataTable](../TVirtualDataTable/index.md)

