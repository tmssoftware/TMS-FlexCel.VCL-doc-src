---
uid: TVirtualDataTableState.CheckDuplicates
description: TVirtualDataTableState.CheckDuplicates
---

# TVirtualDataTableState\.CheckDuplicates Method

This method will be called to let you find out if master datasources share the same internal data\.
There is normally no need to do anything here, but TDataSet needs to check if there are repeated instances\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TVirtualDataTableState/index.md">TVirtualDataTableState</a>.CheckDuplicates(const source: <a href="../TVirtualDataTable/index.md">TVirtualDataTable</a>): Boolean; virtual;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**source**|[TVirtualDataTable](../TVirtualDataTable/index.md)||


## See also

* [TVirtualDataTableState](../TVirtualDataTableState/index.md)

