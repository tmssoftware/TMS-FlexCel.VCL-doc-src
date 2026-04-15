---
uid: TGetIncludeEventArgs.Create
description: TGetIncludeEventArgs.Create
---

# TGetIncludeEventArgs\.Create Constructor

Creates a new Argument\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TGetIncludeEventArgs/index.md">TGetIncludeEventArgs</a>.Create(const aExcelFile: <a href="../../FlexCel.Core/TExcelFile/index.md">TExcelFile</a>; const aFileName: string; const aIncludeData: TBytes);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aExcelFile**|[TExcelFile](../../FlexCel.Core/TExcelFile/index.md)|The ExcelFile that has the report doing the include\.|
|const|**aFileName**|string|File that we are trying to include\.|
|const|**aIncludeData**|TBytes|The included file as an array of bytes\. If you return null, the file will be searched on disk\.|


## See also

* [TGetIncludeEventArgs](../TGetIncludeEventArgs/index.md)

