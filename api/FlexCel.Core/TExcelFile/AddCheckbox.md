---
uid: TExcelFile.AddCheckbox
description: TExcelFile.AddCheckbox
---

# TExcelFile\.AddCheckbox Method

## Overloads

* [TExcelFile\.AddCheckbox\(TClientAnchor, TRichString, TCheckboxState, TCellAddress\)](#texcelfileaddcheckboxtclientanchor-trichstring-tcheckboxstate-tcelladdress)
* [TExcelFile\.AddCheckbox\(TClientAnchor, TRichString, TCheckboxState, TCellAddress, string\)](#texcelfileaddcheckboxtclientanchor-trichstring-tcheckboxstate-tcelladdress-string)

# TExcelFile\.AddCheckbox\(TClientAnchor, TRichString, TCheckboxState, TCellAddress\)
Adds a checkbox to the active sheet\.


## Remarks

Excel supports 2 types of checkboxes: ActiveX and internal \(In Excel you would add them from the "ActiveX" and "Forms" toolbars respectively\)
The checkboxes added by this method are of type internal\. ActiveX checkboxes are not supported\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.AddCheckbox(const anchor: <a href="../TClientAnchor/index.md">TClientAnchor</a>; const text: <a href="../TRichString/index.md">TRichString</a>; const value: <a href="../TCheckboxState.md">TCheckboxState</a>; const linkedCell: <a href="../TCellAddress/index.md">TCellAddress</a>): Integer; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**anchor**|[TClientAnchor](../TClientAnchor/index.md)|Position for the checkbox\.|
|const|**text**|[TRichString](../TRichString/index.md)|Text for the checkbox\.|
|const|**value**|[TCheckboxState](../TCheckboxState.md)|Value of the checkbox\.|
|const|**linkedCell**|[TCellAddress](../TCellAddress/index.md)|Cell that will be linked to the checkbox\. If you don't want to link the checkbox to a cell, make this parameter null\.|


## Returns

Object Index of the inserted checkbox \(1 based\)\.

## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.AddCheckbox\(TClientAnchor, TRichString, TCheckboxState, TCellAddress, string\)
Adds a checkbox to the active sheet\.


## Remarks

Excel supports 2 types of checkboxes: ActiveX and internal \(In Excel you would add them from the "ActiveX" and "Forms" toolbars respectively\)
The checkboxes added by this method are of type internal\. ActiveX checkboxes are not supported\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.AddCheckbox(const anchor: <a href="../TClientAnchor/index.md">TClientAnchor</a>; const text: <a href="../TRichString/index.md">TRichString</a>; const value: <a href="../TCheckboxState.md">TCheckboxState</a>; const linkedCell: <a href="../TCellAddress/index.md">TCellAddress</a>; const name: string): Integer; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**anchor**|[TClientAnchor](../TClientAnchor/index.md)|Position for the checkbox\.|
|const|**text**|[TRichString](../TRichString/index.md)|Text for the checkbox\.|
|const|**value**|[TCheckboxState](../TCheckboxState.md)|Value of the checkbox\.|
|const|**linkedCell**|[TCellAddress](../TCellAddress/index.md)|Cell that will be linked to the checkbox\. If you don't want to link the checkbox to a cell, make this parameter null\.|
|const|**name**|string|Name that will be given to the checkbox\.|


## Returns

Object Index of the inserted checkbox \(1 based\)\.

## See also

* [TExcelFile](../TExcelFile/index.md)

