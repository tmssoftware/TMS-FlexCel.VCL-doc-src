---
uid: THtmlFontEventArgs
description: THtmlFontEventArgs
---

# THtmlFontEventArgs Class

Arguments passed on FlexCel\.Render\.FlexCelHtmlExport\.OnHtmlFont\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">THtmlFontEventArgs = class(EventArgs);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new Argument\.<br />|


## Properties

|Name|Description|
|---|---|
|[Workbook](Workbook.md)|TCoreExcelFile with the cell we are exporting\.<br />|
|[CellFont](CellFont.md)|Font we want to process\.<br />|
|[FontFamily](FontFamily.md)|Use this property to return the new font you want for the cell, if you need to replace it\.<br />Note that you can return more than one font here, and the format for this string is the format on a font selector "font\-family" in a CSS stylesheet\.<br />You could, for example, return the string @"Baskerville, "Heisi Mincho W3", Symbol, serif" here\. Look for a complete description of  the "font\-family" descriptor in the CSS reference\. \([http:&#8203;//&#8203;www.&#8203;w3.&#8203;org/&#8203;TR/&#8203;REC-&#8203;CSS2/&#8203;)](http://www.w3.org/TR/REC-CSS2/))|


