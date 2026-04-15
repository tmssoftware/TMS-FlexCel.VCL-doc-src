---
uid: TVirtualDataTableState.GetValueAndResync
description: TVirtualDataTableState.GetValueAndResync
---

# TVirtualDataTableState\.GetValueAndResync Method

This method will be called when you need to ensure the position of the datasource is correct\.
Normally there is no need to do anything here, but for example TDataSet must ensure that the position of the TDataSet is the correct one, since a child might be using the same DataSet instance and have moved it\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TVirtualDataTableState/index.md">TVirtualDataTableState</a>.GetValueAndResync(const column: Integer): <a href="../TReportValue/index.md">TReportValue</a>; virtual;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**column**|Integer||


## See also

* [TVirtualDataTableState](../TVirtualDataTableState/index.md)

