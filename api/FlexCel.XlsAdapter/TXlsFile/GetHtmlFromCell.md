---
uid: TXlsFile.GetHtmlFromCell
description: TXlsFile.GetHtmlFromCell
---

# TXlsFile\.GetHtmlFromCell Method

Returns the contents of formatted cell as HTML\.
Conditional formats are not applied \(unless includeCellFormatting is true\): you need to call [TExcelFile.ConditionallyModifyFormat\(TFlxFormat, Integer, Integer, Boolean, IDrawingConditionalFormat\)](../../FlexCel.Core/TExcelFile/ConditionallyModifyFormat.md#texcelfileconditionallymodifyformattflxformat-integer-integer-boolean-idrawingconditionalformat) to the cell style to get the cell with cf applied\.
If [TExcelFile.ShowFormulaText](../../FlexCel.Core/TExcelFile/ShowFormulaText.md) is true, it will return the formula text instead of the value\.
For a list of HTML tags that might be returned, see the **Remarks** section\.


## Remarks

Text will be returned as standard HTML, on the version specified\. This means that  for example a \< sign will be returned as "&amp;lt;"\. For a list of all "&amp;" possible symbols consult any HTML reference\. &amp;\[HexadecimalUnicodeCharacer\] might be returned too\.


Multiple spaces will be returned as "&amp;nbsp;" \(non breaking space\) and line breaks will be returned as
tags\.



The tags that might be returned by this method are:  If htmlStyle is Simple:
* **b** \- Bold\.
* **i** \- Italics\.
* **u** \- Underline\.
* **s** \- Strikeout\.
* **sub** \- Subscript\.
* **sup** \- Superscript\.
* **font** \- Change the used font\. This tag behaves as normal HTML, and you can specify  *color*, *face*, *point\-size* or *size* as attributes\. Size might be between 1 and 7,  and the size in points are 8, 9, 12, 14, 18, 24, 34 for each size\. You can also specify relative sizes \(for example \-1\)


If htmlStyle is CSS: The equivalent CSS style commands to the ones listed under htmlStyle = Simple\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetHtmlFromCell(const row: Integer; const col: Integer; const htmlVersion: <a href="../../FlexCel.Core/THtmlVersion.md">THtmlVersion</a>; const htmlStyle: <a href="../../FlexCel.Core/THtmlStyle.md">THtmlStyle</a>; const encoding: TEncoding; const includeCellFormatting: Boolean): string; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Cell Row \(1 based\)|
|const|**col**|Integer|Cell Column \(1 based\)|
|const|**htmlVersion**|[THtmlVersion](../../FlexCel.Core/THtmlVersion.md)|Version of the HTML returned\. In XHTML, single tags have a "/" at the end, while in 4\.0 they don't\.|
|const|**htmlStyle**|[THtmlStyle](../../FlexCel.Core/THtmlStyle.md)|Specifies if to use simple tags or CSS for the returned HTML\.|
|const|**encoding**|TEncoding|Encoding for the returned string\. Use UTF\-8 if in doubt\.|
|const|**includeCellFormatting**|Boolean|If true, the result will include the cell formatting in the formatting\. So if for example a cell is formatted as bold, and the string inside doesn't have formatting, this method will return "\<b>Text\</b>" when includeCellFormatting is true, and just "Text" when it is false\. If this parameter is true, it will also consider the conditional formatting of the cell\.|


## Returns

An HTML formatted string with the cell contents\.

## See also

* [TXlsFile](../TXlsFile/index.md)

