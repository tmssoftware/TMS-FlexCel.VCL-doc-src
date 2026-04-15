---
uid: TXlsFile.AddCheckbox
description: TXlsFile.AddCheckbox
---

# TXlsFile\.AddCheckbox Method

Adds a checkbox to the active sheet\.


## Remarks

Excel supports 2 types of checkboxes: ActiveX and internal \(In Excel you would add them from the "ActiveX" and "Forms" toolbars respectively\)
The checkboxes added by this method are of type internal\. ActiveX checkboxes are not supported\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.AddCheckbox(const anchor: <a href="../../FlexCel.Core/TClientAnchor/index.md">TClientAnchor</a>; const text: <a href="../../FlexCel.Core/TRichString/index.md">TRichString</a>; const value: <a href="../../FlexCel.Core/TCheckboxState.md">TCheckboxState</a>; const linkedCell: <a href="../../FlexCel.Core/TCellAddress/index.md">TCellAddress</a>; const name: string): Integer; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**anchor**|[TClientAnchor](../../FlexCel.Core/TClientAnchor/index.md)|Position for the checkbox\.|
|const|**text**|[TRichString](../../FlexCel.Core/TRichString/index.md)|Text for the checkbox\.|
|const|**value**|[TCheckboxState](../../FlexCel.Core/TCheckboxState.md)|Value of the checkbox\.|
|const|**linkedCell**|[TCellAddress](../../FlexCel.Core/TCellAddress/index.md)|Cell that will be linked to the checkbox\. If you don't want to link the checkbox to a cell, make this parameter null\.|
|const|**name**|string|Name that will be given to the checkbox\.|


## Returns

Object Index of the inserted checkbox \(1 based\)\.

## See also

* [TXlsFile](../TXlsFile/index.md)

