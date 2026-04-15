---
uid: TWorkspace.Add
description: TWorkspace.Add
---

# TWorkspace\.Add Method

Adds a file to the workspace\. Whenever you recalculate any file in this workspace, all linked files will be recalculated too\.
**Note that you can't add two files with the same name or same reference twice to this collection\.**

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TWorkspace/index.md">TWorkspace</a>.Add(const FileName: string; const xls: <a href="../TExcelFile/index.md">TExcelFile</a>);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**FileName**|string|Name that this file will have in the workspace\. When recalculating a linked formula, this name will be used\.<br />If you want to include paths in the name you can too, but it is normally unnecessary since FlexCel will search for the simple filename anyway\.<br />You only need to include paths if you have 2 files with the same name in different folders used in the recalculation\.|
|const|**xls**|[TExcelFile](../TExcelFile/index.md)|Excel file to add\.|


## See also

* [TWorkspace](../TWorkspace/index.md)

