---
uid: TExcelFile.CopyToClipboardFormat
description: TExcelFile.CopyToClipboardFormat
---

# TExcelFile\.CopyToClipboardFormat Method

## Overloads

* [TExcelFile\.CopyToClipboardFormat\(TXlsCellRange, TStringBuilder, TStream\)](#texcelfilecopytoclipboardformattxlscellrange-tstringbuilder-tstream)
* [TExcelFile\.CopyToClipboardFormat\(TFlexCelClipboardFormat, TXlsCellRange, TStream\)](#texcelfilecopytoclipboardformattflexcelclipboardformat-txlscellrange-tstream)

# TExcelFile\.CopyToClipboardFormat\(TXlsCellRange, TStringBuilder, TStream\)
Copies a range on the active sheet to a clipboard stream, on native and text formats\.


## Remarks

See the copy and paste demo\.

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.CopyToClipboardFormat(const range: <a href="../TXlsCellRange/index.md">TXlsCellRange</a>; const textString: TStringBuilder; const xlsStream: TStream); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**range**|[TXlsCellRange](../TXlsCellRange/index.md)|Range with the cells to copy\.|
|const|**textString**|TStringBuilder|StringBuilder where the text will be copied\. Leave it null to not copy to text\.|
|const|**xlsStream**|TStream|Stream where the xls native info will be copied\. If null no native data will be copied\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.CopyToClipboardFormat\(TFlexCelClipboardFormat, TXlsCellRange, TStream\)
Copies a range on the active sheet to a clipboard stream, on the specified format\.


## Remarks

See the copy and paste demo\.

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.CopyToClipboardFormat(const clipboardFormat: <a href="../TFlexCelClipboardFormat.md">TFlexCelClipboardFormat</a>; const range: <a href="../TXlsCellRange/index.md">TXlsCellRange</a>; const outStream: TStream); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**clipboardFormat**|[TFlexCelClipboard&#8203;Format](../TFlexCelClipboardFormat.md)|Format you want to copy into outStream\.|
|const|**range**|[TXlsCellRange](../TXlsCellRange/index.md)|Range with the cells to copy\.|
|const|**outStream**|TStream|Stream where the clipboard info will be copied\. If null, nothing will be copied\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

