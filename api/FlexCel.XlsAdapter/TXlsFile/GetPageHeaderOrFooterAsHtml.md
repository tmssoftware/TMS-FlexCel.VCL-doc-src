---
uid: TXlsFile.GetPageHeaderOrFooterAsHtml
description: TXlsFile.GetPageHeaderOrFooterAsHtml
---

# TXlsFile\.GetPageHeaderOrFooterAsHtml Method

Converts a section of a page header or footer into an HTML string\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetPageHeaderOrFooterAsHtml(const section: string; const imageTag: string; const pageNumber: Integer; const pageCount: Integer; const htmlVersion: <a href="../../FlexCel.Core/THtmlVersion.md">THtmlVersion</a>; const encoding: TEncoding; const onFont: <a href="../../FlexCel.Core/IHtmlFontEvent/index.md">IHtmlFontEvent</a>): string; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**section**|string|Text to convert\. You will normally get this parameter calling [TExcelFile.FillPageHeaderOrFooter](../../FlexCel.Core/TExcelFile/FillPageHeaderOrFooter.md)|
|const|**imageTag**|string|Tag to call an image for the section\. It must be in the form: "\<img src=\.\.\.>" and you can get the image with [TExcelFile.GetHeaderOrFooterImage\(THeaderAndFooterKind, THeaderAndFooterPos, TXlsImgType, TStream\)](../../FlexCel.Core/TExcelFile/GetHeaderOrFooterImage.md#texcelfilegetheaderorfooterimagetheaderandfooterkind-theaderandfooterpos-txlsimgtype-tstream) \. If null or empty, no img tag will be present in the resulting HTML, even if the section includes an image\.|
|const|**pageNumber**|Integer|Page we are printing\. This parameter will be used if you have text like "Page 1 of 3" in the header\.<br /><br />If you are exporting to HTML, this value should be 1, since there are no page breaks in an HTML doc\.|
|const|**pageCount**|Integer|Number of pages in the document\. This parameter will be used if you have text like "Page 1 of 3" in the header\.<br /><br />If you are exporting to HTML, this value should be 1, since there are no page breaks in an HTML doc|
|const|**htmlVersion**|[THtmlVersion](../../FlexCel.Core/THtmlVersion.md)|Version of HTML we are targeting\. In HTML 4<br />is valid and<br />is not\. In XHtml the inverse is true\.|
|const|**encoding**|TEncoding|Code page used to encode the string\. Normally this is UTF\-8|
|const|**onFont**|[IHtmlFontEvent](../../FlexCel.Core/IHtmlFontEvent/index.md)|Method that can customize the fonts used in the resulting string\. It can be null if you don't want to do any modification to the fonts\.|


## Returns

An HTML string with the section\.

## See also

* [TXlsFile](../TXlsFile/index.md)

