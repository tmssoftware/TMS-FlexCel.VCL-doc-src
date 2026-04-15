---
uid: TXlsFile.AddRadioButton
description: TXlsFile.AddRadioButton
---

# TXlsFile\.AddRadioButton Method

Adds a radio button to the active sheet\. Call [TExcelFile.AddGroupBox\(TClientAnchor, TRichString\)](../../FlexCel.Core/TExcelFile/AddGroupBox.md#texcelfileaddgroupboxtclientanchor-trichstring) to insert a group box for grouping the radio buttons\.


## Remarks

Excel supports 2 types of radio buttons: ActiveX and internal \(In Excel you would add them from the "ActiveX" and "Forms" toolbars respectively\)
The radio buttons added by this method are of type internal\. ActiveX radio buttons are not supported\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.AddRadioButton(const anchor: <a href="../../FlexCel.Core/TClientAnchor/index.md">TClientAnchor</a>; const text: <a href="../../FlexCel.Core/TRichString/index.md">TRichString</a>; const name: string): Integer; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**anchor**|[TClientAnchor](../../FlexCel.Core/TClientAnchor/index.md)|Position for the radio button\.|
|const|**text**|[TRichString](../../FlexCel.Core/TRichString/index.md)|Text for the radio button\.|
|const|**name**|string|Name of the inserted radio button\.|


## Returns

Object Index of the inserted radio button \(1 based\)\.

## See also

* [TXlsFile](../TXlsFile/index.md)

