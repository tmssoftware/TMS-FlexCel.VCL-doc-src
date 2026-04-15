---
uid: TExcelFile.GetPageHeaderOrFooterAsHtml
description: TExcelFile.GetPageHeaderOrFooterAsHtml
---

# TExcelFile\.GetPageHeaderOrFooterAsHtml Method

Converts a section of a page header or footer into an HTML string\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetPageHeaderOrFooterAsHtml(const section: string; const imageTag: string; const pageNumber: Integer; const pageCount: Integer; const htmlVersion: <a href="../THtmlVersion.md">THtmlVersion</a>; const encoding: TEncoding; const onFont: <a href="../IHtmlFontEvent/index.md">IHtmlFontEvent</a>): string; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**section**|string|Text to convert\. You will normally get this parameter calling [FillPageHeaderOrFooter](FillPageHeaderOrFooter.md)|
|const|**imageTag**|string|Tag to call an image for the section\. It must be in the form: "\<img src=\.\.\.>" and you can get the image with [GetHeaderOrFooterImage\(THeaderAndFooterKind, THeaderAndFooterPos, TXlsImgType, TStream\)](GetHeaderOrFooterImage.md#texcelfilegetheaderorfooterimagetheaderandfooterkind-theaderandfooterpos-txlsimgtype-tstream) \. If null or empty, no img tag will be present in the resulting HTML, even if the section includes an image\.|
|const|**pageNumber**|Integer|Page we are printing\. This parameter will be used if you have text like "Page 1 of 3" in the header\.<br /><br />If you are exporting to HTML, this value should be 1, since there are no page breaks in an HTML doc\.|
|const|**pageCount**|Integer|Number of pages in the document\. This parameter will be used if you have text like "Page 1 of 3" in the header\.<br /><br />If you are exporting to HTML, this value should be 1, since there are no page breaks in an HTML doc|
|const|**htmlVersion**|[THtmlVersion](../THtmlVersion.md)|Version of HTML we are targeting\. In HTML 4<br />is valid and<br />is not\. In XHtml the inverse is true\.|
|const|**encoding**|TEncoding|Code page used to encode the string\. Normally this is UTF\-8|
|const|**onFont**|[IHtmlFontEvent](../IHtmlFontEvent/index.md)|Method that can customize the fonts used in the resulting string\. It can be null if you don't want to do any modification to the fonts\.|


## Returns

An HTML string with the section\.

## See also

* [TExcelFile](../TExcelFile/index.md)

