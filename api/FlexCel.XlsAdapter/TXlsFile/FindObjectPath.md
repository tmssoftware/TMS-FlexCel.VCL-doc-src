---
uid: TXlsFile.FindObjectPath
description: TXlsFile.FindObjectPath
---

# TXlsFile\.FindObjectPath Method

Finds an object by its name, and returns the ObjectPath you need to use this object\.
Note that if there is more than an object with the same name in the sheet, this method  will return null\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.FindObjectPath(const objectName: string): string; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectName**|string|Name of the object we are looking for\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

