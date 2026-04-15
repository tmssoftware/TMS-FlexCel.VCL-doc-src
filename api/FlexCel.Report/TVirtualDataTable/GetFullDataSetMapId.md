---
uid: TVirtualDataTable.GetFullDataSetMapId
description: TVirtualDataTable.GetFullDataSetMapId
---

# TVirtualDataTable\.GetFullDataSetMapId Method

Returns an id you can use to map a column name \+ \* to something you can use in [GetFullDataSetColumn](GetFullDataSetColumn.md)

## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TVirtualDataTable/index.md">TVirtualDataTable</a>.GetFullDataSetMapId(const Column: string): Integer; virtual;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**Column**|string|We will pass here the full name of the column up to but not including the \* or \*\*\. This might be empty or somehting\.\.\.something\.\*|


## See also

* [TVirtualDataTable](../TVirtualDataTable/index.md)

