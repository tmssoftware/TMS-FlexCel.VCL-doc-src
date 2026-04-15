---
uid: TXlsFile.BringToFront
description: TXlsFile.BringToFront
---

# TXlsFile\.BringToFront Method

Sends the graphical object to the top layer on the display \(z\-order\) position\. It will show above and will cover all other objects on the sheet\.


## Remarks

This will change the order of the array, so after calling BringToFront\(i\), position i will have a new object\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.BringToFront(const objectIndex: Integer); override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object to move\. \(1 based\)|


## See also

* [TXlsFile](../TXlsFile/index.md)
* [TExcelFile.SendToBack](../../FlexCel.Core/TExcelFile/SendToBack.md)
* [TExcelFile.SendForward](../../FlexCel.Core/TExcelFile/SendForward.md)
* [TExcelFile.SendBack](../../FlexCel.Core/TExcelFile/SendBack.md)

