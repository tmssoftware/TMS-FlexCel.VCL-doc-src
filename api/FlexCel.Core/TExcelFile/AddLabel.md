---
uid: TExcelFile.AddLabel
description: TExcelFile.AddLabel
---

# TExcelFile\.AddLabel Method

Adds a Label to the active sheet\.


## Remarks

Excel supports 2 types of labels: ActiveX and internal \(In Excel you would add them from the "ActiveX" and "Forms" toolbars respectively\)
The labels added by this method are of type internal\. ActiveX labels are not supported\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.AddLabel(const anchor: <a href="../TClientAnchor/index.md">TClientAnchor</a>; const text: <a href="../TRichString/index.md">TRichString</a>; const name: string): Integer; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**anchor**|[TClientAnchor](../TClientAnchor/index.md)|Position for the label\.|
|const|**text**|[TRichString](../TRichString/index.md)|Text for the label\.|
|const|**name**|string|Name of the inserted label\.|


## Returns

Object Index of the inserted listbox \(1 based\)\.

## See also

* [TExcelFile](../TExcelFile/index.md)

