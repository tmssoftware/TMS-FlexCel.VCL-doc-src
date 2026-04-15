---
uid: TExcelFile.AddGroupBox
description: TExcelFile.AddGroupBox
---

# TExcelFile\.AddGroupBox Method

## Overloads

* [TExcelFile\.AddGroupBox\(TClientAnchor, TRichString\)](#texcelfileaddgroupboxtclientanchor-trichstring)
* [TExcelFile\.AddGroupBox\(TClientAnchor, TRichString, string\)](#texcelfileaddgroupboxtclientanchor-trichstring-string)

# TExcelFile\.AddGroupBox\(TClientAnchor, TRichString\)
Adds a Group box to the active sheet\. Call [AddRadioButton\(TClientAnchor, TRichString\)](AddRadioButton.md#texcelfileaddradiobuttontclientanchor-trichstring) to insert radio buttons inside the group box\.


## Remarks

Excel determines if a radio button is inside a group box by looking at the coordinates of both objects\.
To include a radio button inside the group box, just make sure it is entirely inside the group box\.
Object hierarchy doesn't matter here, only the positions of the group box and the radio button\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.AddGroupBox(const anchor: <a href="../TClientAnchor/index.md">TClientAnchor</a>; const text: <a href="../TRichString/index.md">TRichString</a>): Integer; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**anchor**|[TClientAnchor](../TClientAnchor/index.md)|Position for the group box\.|
|const|**text**|[TRichString](../TRichString/index.md)|Text for the group box\.|


## Returns

Object Index of the inserted group box \(1 based\)\.

## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.AddGroupBox\(TClientAnchor, TRichString, string\)
Adds a Group box to the active sheet\. Call [AddRadioButton\(TClientAnchor, TRichString\)](AddRadioButton.md#texcelfileaddradiobuttontclientanchor-trichstring) to insert radio buttons inside the group box\.


## Remarks

Excel determines if a radio button is inside a group box by looking at the coordinates of both objects\.
To include a radio button inside the group box, just make sure it is entirely inside the group box\.
Object hierarchy doesn't matter here, only the positions of the group box and the radio button\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.AddGroupBox(const anchor: <a href="../TClientAnchor/index.md">TClientAnchor</a>; const text: <a href="../TRichString/index.md">TRichString</a>; const name: string): Integer; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**anchor**|[TClientAnchor](../TClientAnchor/index.md)|Position for the group box\.|
|const|**text**|[TRichString](../TRichString/index.md)|Text for the group box\.|
|const|**name**|string|Name for the inserted Group box|


## Returns

Object Index of the inserted group box \(1 based\)\.

## See also

* [TExcelFile](../TExcelFile/index.md)

