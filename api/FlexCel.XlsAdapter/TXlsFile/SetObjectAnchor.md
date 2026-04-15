---
uid: TXlsFile.SetObjectAnchor
description: TXlsFile.SetObjectAnchor
---

# TXlsFile\.SetObjectAnchor Method

Sets the object placement\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetObjectAnchor(const objectIndex: Integer; const objectPath: string; const objectAnchor: <a href="../../FlexCel.Core/TClientAnchor/index.md">TClientAnchor</a>); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1\-based\)|
|const|**objectPath**|string|Object path for the shape if this is a grouped shape\.|
|const|**objectAnchor**|[TClientAnchor](../../FlexCel.Core/TClientAnchor/index.md)|Coordinates of the object\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

