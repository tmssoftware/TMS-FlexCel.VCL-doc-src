---
uid: TExcelFile.AddRadioButton
description: TExcelFile.AddRadioButton
---

# TExcelFile\.AddRadioButton Method

## Overloads

* [TExcelFile\.AddRadioButton\(TClientAnchor, TRichString\)](#texcelfileaddradiobuttontclientanchor-trichstring)
* [TExcelFile\.AddRadioButton\(TClientAnchor, TRichString, string\)](#texcelfileaddradiobuttontclientanchor-trichstring-string)

# TExcelFile\.AddRadioButton\(TClientAnchor, TRichString\)
Adds a radio button to the active sheet\. Call [AddGroupBox\(TClientAnchor, TRichString\)](AddGroupBox.md#texcelfileaddgroupboxtclientanchor-trichstring) to insert a group box for grouping the radio buttons\.


## Remarks

Excel supports 2 types of radio buttons: ActiveX and internal \(In Excel you would add them from the "ActiveX" and "Forms" toolbars respectively\)
The radio buttons added by this method are of type internal\. ActiveX radio buttons are not supported\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.AddRadioButton(const anchor: <a href="../TClientAnchor/index.md">TClientAnchor</a>; const text: <a href="../TRichString/index.md">TRichString</a>): Integer; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**anchor**|[TClientAnchor](../TClientAnchor/index.md)|Position for the radio button\.|
|const|**text**|[TRichString](../TRichString/index.md)|Text for the radio button\.|


## Returns

Object Index of the inserted radio button \(1 based\)\.

## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.AddRadioButton\(TClientAnchor, TRichString, string\)
Adds a radio button to the active sheet\. Call [AddGroupBox\(TClientAnchor, TRichString\)](AddGroupBox.md#texcelfileaddgroupboxtclientanchor-trichstring) to insert a group box for grouping the radio buttons\.


## Remarks

Excel supports 2 types of radio buttons: ActiveX and internal \(In Excel you would add them from the "ActiveX" and "Forms" toolbars respectively\)
The radio buttons added by this method are of type internal\. ActiveX radio buttons are not supported\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.AddRadioButton(const anchor: <a href="../TClientAnchor/index.md">TClientAnchor</a>; const text: <a href="../TRichString/index.md">TRichString</a>; const name: string): Integer; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**anchor**|[TClientAnchor](../TClientAnchor/index.md)|Position for the radio button\.|
|const|**text**|[TRichString](../TRichString/index.md)|Text for the radio button\.|
|const|**name**|string|Name of the inserted radio button\.|


## Returns

Object Index of the inserted radio button \(1 based\)\.

## See also

* [TExcelFile](../TExcelFile/index.md)

