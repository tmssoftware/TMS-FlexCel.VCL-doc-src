---
uid: TFlexCelHtmlExport.ExportAllVisibleSheetsAsOneHtmlFile
description: TFlexCelHtmlExport.ExportAllVisibleSheetsAsOneHtmlFile
---

# TFlexCelHtmlExport\.ExportAllVisibleSheetsAsOneHtmlFile Method

## Overloads

* [TFlexCelHtmlExport\.ExportAllVisibleSheetsAsOneHtmlFile\(string, string, string, string\)](#tflexcelhtmlexportexportallvisiblesheetsasonehtmlfilestring-string-string-string)
* [TFlexCelHtmlExport\.ExportAllVisibleSheetsAsOneHtmlFile\(TFlexCelWriter, string, string, string, string\)](#tflexcelhtmlexportexportallvisiblesheetsasonehtmlfiletflexcelwriter-string-string-string-string)

# TFlexCelHtmlExport\.ExportAllVisibleSheetsAsOneHtmlFile\(string, string, string, string\)
Exports all visible sheets in an xls file one after the other in the same html file\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelHtmlExport/index.md">TFlexCelHtmlExport</a>.ExportAllVisibleSheetsAsOneHtmlFile(const htmlFileName: string; const relativeImagePath: string; const relativeCssFileName: string; const sheetSeparator: string); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**htmlFileName**|string|Path where the generated html file will be stored\.|
|const|**relativeImagePath**|string|Folder where images will be stored, relative to the path in htmlFileName\.<br />If for example htmlFileName is "c:\\reports\\html\\test\.htm" and relativeImagePath is "images", images will be saved in folder "c:\\reports\\html\\images"\. If this parameter is null or empty, images will be saved in the same folder as the html file\.|
|const|**relativeCssFileName**|string|Name for the Css file, with a path relative to the htmlFileName Path\.<br />if you set it to null, no css file created and the css will be stored inside each HTML file\.<br />If for example htmlFileName is "c:\\reports\\test\.htm" and relativeCssFileName is "css\\data\.css" the css file will be saved in "c:\\reports\\css\\data\.css"|
|const|**sheetSeparator**|string|An HTML string to write between all the different sheets being exported\. You can use for example \<hr /> here to add a horizontal line\. You can also use the special macros \<\#SheetName>, \<\#SheetCount>, \<\#SheetPos> \<\#PrevSheetName> and \<\#PrevSheetPos> here to enter the current sheet name,  the number of sheets and the current sheet respectively\. The macros are case insensitive, you can enter them in any combination of upper and lower case\.|


## See also

* [TFlexCelHtmlExport](../TFlexCelHtmlExport/index.md)

# TFlexCelHtmlExport\.ExportAllVisibleSheetsAsOneHtmlFile\(TFlexCelWriter, string, string, string, string\)
Exports all visible sheets in an xls file one after the other in the same html stream\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelHtmlExport/index.md">TFlexCelHtmlExport</a>.ExportAllVisibleSheetsAsOneHtmlFile(const html: <a href="../../FlexCel.Core/TFlexCelWriter/index.md">TFlexCelWriter</a>; const htmlFileName: string; const relativeImagePath: string; const relativeCssFileName: string; const sheetSeparator: string); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**html**|[TFlexCelWriter](../../FlexCel.Core/TFlexCelWriter/index.md)|Stream where the HTML file will be saved\.|
|const|**htmlFileName**|string|The filename itself won't be used \(since the html file is saved to a stream\), but it will tell the path where the generated extra files \(for example images\) will be stored, and also the way images are named\.|
|const|**relativeImagePath**|string|Folder where images will be stored, relative to the path in htmlFileName\.<br />If for example htmlFileName is "c:\\reports\\html\\test\.htm" and relativeImagePath is "images", images will be saved in folder "c:\\reports\\html\\images"\. If this parameter is null or empty, images will be saved in the same folder as the html file\.|
|const|**relativeCssFileName**|string|Name for the Css file, with a path relative to the htmlFileName Path\.<br />if you set it to null, no css file created and the css will be stored inside each HTML file\.<br />If for example htmlFileName is "c:\\reports\\test\.htm" and relativeCssFileName is "css\\data\.css" the css file will be saved in "c:\\reports\\css\\data\.css"|
|const|**sheetSeparator**|string|An HTML string to write between all the different sheets being exported\. You can use for example \<hr />\<p>Sheet \<\#SheetName>\</p> here to add a horizontal line\. You can also use the special macros \<\#SheetName>, \<\#SheetCount> and \<\#SheetPos> here to enter the current sheet name,  the number of sheets and the current sheet respectively\. The macros are case insensitive, you can enter them in any combination of upper and lower case\.|


## See also

* [TFlexCelHtmlExport](../TFlexCelHtmlExport/index.md)

