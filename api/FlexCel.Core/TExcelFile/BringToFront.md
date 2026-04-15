---
uid: TExcelFile.BringToFront
description: TExcelFile.BringToFront
---

# TExcelFile\.BringToFront Method

Sends the graphical object to the top layer on the display \(z\-order\) position\. It will show above and will cover all other objects on the sheet\.


## Remarks

This will change the order of the array, so after calling BringToFront\(i\), position i will have a new object\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.BringToFront(const objectIndex: Integer); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object to move\. \(1 based\)|


## See also

* [TExcelFile](../TExcelFile/index.md)
* [SendToBack](SendToBack.md)
* [SendForward](SendForward.md)
* [SendBack](SendBack.md)

