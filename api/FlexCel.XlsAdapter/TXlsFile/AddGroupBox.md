---
uid: TXlsFile.AddGroupBox
description: TXlsFile.AddGroupBox
---

# TXlsFile\.AddGroupBox Method

Adds a Group box to the active sheet\. Call [TExcelFile.AddRadioButton\(TClientAnchor, TRichString\)](../../FlexCel.Core/TExcelFile/AddRadioButton.md#texcelfileaddradiobuttontclientanchor-trichstring) to insert radio buttons inside the group box\.


## Remarks

Excel determines if a radio button is inside a group box by looking at the coordinates of both objects\.
To include a radio button inside the group box, just make sure it is entirely inside the group box\.
Object hierarchy doesn't matter here, only the positions of the group box and the radio button\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.AddGroupBox(const anchor: <a href="../../FlexCel.Core/TClientAnchor/index.md">TClientAnchor</a>; const text: <a href="../../FlexCel.Core/TRichString/index.md">TRichString</a>; const name: string): Integer; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**anchor**|[TClientAnchor](../../FlexCel.Core/TClientAnchor/index.md)|Position for the group box\.|
|const|**text**|[TRichString](../../FlexCel.Core/TRichString/index.md)|Text for the group box\.|
|const|**name**|string|Name for the inserted Group box|


## Returns

Object Index of the inserted group box \(1 based\)\.

## See also

* [TXlsFile](../TXlsFile/index.md)

