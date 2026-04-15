---
uid: TXlsFile.SetCellFromHtml
description: TXlsFile.SetCellFromHtml
---

# TXlsFile\.SetCellFromHtml Method

Enters an HTML formatted string into a cell, and tries to match the Excel formats with the HTML formatting tags\.
Note that the rich text inside Excel is more limited than xls \(you are limited to only changing font attributes\), so many tags from the HTML tags might be ignored\. Whenever a tag is not understood or cannot be mapped into Excel, it will just be omitted\. For a list of supported tags, see the **Remarks** section\.


## Remarks

Any tag \(between brackets\) will be stripped from the entered text\. If you want to enter a \< sign, you need to enter "&amp;lt;"\. For a list of all "&amp;" possible symbols consult any HTML reference\. &amp;\[HexadecimalUnicodeCharacer\] are supported too\.

All tags are case insensitive\.

Spaces will be eliminated from the string as in normal HTML\. To enter a "hard" space you can enter "&amp;nbsp;" \(non breaking space\)\. Also, if text is inside "pre" tags, spaces will be preserved\.



The supported tags are:
* **b** or **strong** \- Bold\.
* **i** or **em**\- Italics\.
* **u** \- Underline\.
* **s** or **strike**\- Strikeout\.
* **sub** \- Subscript\.
* **sup** \- Superscript\.
* **tt** \- Use monospace font\.
* **pre** \- Preserve spaces and returns\. On normal mode, if you have 2 spaces on a string, only one will be kept\.
* **font** \- Change the used font\. This tag behaves as normal HTML, and you can specify  *color*, *face*, *point\-size* or *size* as attributes\. Size might be between 1 and 7,  and the size in points are 8, 9, 12, 14, 18, 24, 34 for each size\. You can also specify relative sizes \(for example \-1\)
* **h1**\.\.**h6** \- Header fonts\.
* **small** \- Use a smaller font\. This is equivalent to \<font size = '\-1'>
* **big** \- Use a bigger font\. This is equivalent to \<font size = '\+1'>
* **ul** \- Unordered list\.
* **ol** \- Ordered list\.
* **li** \- List item\.



## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetCellFromHtml(const row: Integer; const col: Integer; const htmlText: string; const XF: Integer); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Cell Row \(1 based\)|
|const|**col**|Integer|Cell Column \(1 based\)|
|const|**htmlText**|string|Text with an HTML formatted string\.|
|const|**XF**|Integer|Format for the cell\. It can be \-1 to keep the existing format\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

