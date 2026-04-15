---
uid: TExcelFile.SendToBack
description: TExcelFile.SendToBack
---

# TExcelFile\.SendToBack Method

Sends the graphical object to the bottom layer on the display \(z\-order\) position\. It will show below and will be covered by all other objects on the sheet\.


## Remarks

This will change the order of the array, so after calling SendToBack\(i\), position i will have a new object\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SendToBack(const objectIndex: Integer); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object to move\. \(1 based\)|


## See also

* [TExcelFile](../TExcelFile/index.md)
* [SendBack](SendBack.md)
* [SendForward](SendForward.md)
* [BringToFront](BringToFront.md)

