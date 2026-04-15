---
uid: TExcelFile.FindObjectPath
description: TExcelFile.FindObjectPath
---

# TExcelFile\.FindObjectPath Method

Finds an object by its name, and returns the ObjectPath you need to use this object\.
Note that if there is more than an object with the same name in the sheet, this method  will return null\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.FindObjectPath(const objectName: string): string; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectName**|string|Name of the object we are looking for\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

