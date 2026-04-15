---
uid: TXlsFile.SendToBack
description: TXlsFile.SendToBack
---

# TXlsFile\.SendToBack Method

Sends the graphical object to the bottom layer on the display \(z\-order\) position\. It will show below and will be covered by all other objects on the sheet\.


## Remarks

This will change the order of the array, so after calling SendToBack\(i\), position i will have a new object\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SendToBack(const objectIndex: Integer); override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object to move\. \(1 based\)|


## See also

* [TXlsFile](../TXlsFile/index.md)
* [TExcelFile.SendBack](../../FlexCel.Core/TExcelFile/SendBack.md)
* [TExcelFile.SendForward](../../FlexCel.Core/TExcelFile/SendForward.md)
* [TExcelFile.BringToFront](../../FlexCel.Core/TExcelFile/BringToFront.md)

