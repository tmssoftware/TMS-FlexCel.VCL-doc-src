---
uid: TExcelFile.CopyToClipboard
description: TExcelFile.CopyToClipboard
---

# TExcelFile\.CopyToClipboard Method

## Overloads

* [TExcelFile\.CopyToClipboard\(TStringBuilder, TStream\)](#texcelfilecopytoclipboardtstringbuilder-tstream)
* [TExcelFile\.CopyToClipboard\(TFlexCelClipboardFormat, TStream\)](#texcelfilecopytoclipboardtflexcelclipboardformat-tstream)

# TExcelFile\.CopyToClipboard\(TStringBuilder, TStream\)
Copies the active sheet to a clipboard stream, on native and text formats\.


## Remarks

See the copy and paste demo\.

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.CopyToClipboard(const textString: TStringBuilder; const xlsStream: TStream); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**textString**|TStringBuilder|StringBuilder where the text will be copied\. Leave it null to not copy to text\.|
|const|**xlsStream**|TStream|Stream where the xls native info will be copied\. Make it null to not copy to xls native\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.CopyToClipboard\(TFlexCelClipboardFormat, TStream\)
Copies the active sheet to a clipboard stream, on the format you specify\.


## Remarks

See the copy and paste demo\.

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.CopyToClipboard(const clipboardFormat: <a href="../TFlexCelClipboardFormat.md">TFlexCelClipboardFormat</a>; const outStream: TStream); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**clipboardFormat**|[TFlexCelClipboard&#8203;Format](../TFlexCelClipboardFormat.md)|Format you want to copy into outStream\.|
|const|**outStream**|TStream|Stream were the information will be copied\. If null nothing will be done\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

