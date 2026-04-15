---
uid: TFlexCelHtmlExport.ExportAllVisibleSheetsAsTabs
description: TFlexCelHtmlExport.ExportAllVisibleSheetsAsTabs
---

# TFlexCelHtmlExport\.ExportAllVisibleSheetsAsTabs Method

This method will export all the visible sheets on an xls file to an html file, writing each sheet in a different file\.
This is equivalent to calling Export on every sheet\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelHtmlExport/index.md">TFlexCelHtmlExport</a>.ExportAllVisibleSheetsAsTabs(const htmlPath: string; const htmlFileNamePrefix: string; const htmlFileNamePostfix: string; const relativeImagePath: string; const relativeCssFileName: string; const sheetSelector: <a href="../TSheetSelector/index.md">TSheetSelector</a>; const freeSheetSelectorAfterUse: Boolean = True; const OnSheetName: <a href="../../FlexCel.Core/TOnSheetNameEventHandler.md">TOnSheetNameEventHandler</a> = nil);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**htmlPath**|string|Path where html files will be stored\. \(one per sheet in the workbook\)|
|const|**htmlFileNamePrefix**|string|This is a string that will be added to every file generated, at the beggining of the filename\.<br />For example, if htlmFileNamePrefix = "test\_" and htmlFileNamePostfix = "\.html", "sheet1" will be exported as "test\_sheet1\.html"\.<br />If generating a single file \(MHTML format\), htmlFileNamePrefix \+ htmlFileNamePostFix will be used, without a sheet name\.<br />Note that you can change the sheetname to some other string in the OnSheetName event, so the final name will be htmlFileNamePrefix \+ "string returned in OnSheetName" \+ htmlFileNamePostfix\.|
|const|**htmlFileNamePostfix**|string|This is a string that will be added to every file generated, at the end of the filename\. Make sure you include the extension here\.<br />For example, if htlmFileNamePrefix = "test\_" and htmlFileNamePostfix = "\.html", "sheet1" will be exported as "test\_sheet1\.html" If generating a single file \(MHTML format\), htmlFileNamePrefix \+ htmlFileNamePostFix will be used, without a sheet name\.|
|const|**relativeImagePath**|string|Folder where images will be stored, relative to the htmlPath\.<br />If for example htmlPath is "c:\\reports\\html" and relativeImagePath is "images", images will be saved in folder "c:\\reports\\html\\images"\. If this parameter is null or empty, images will be saved in the same folder as the html files\.|
|const|**relativeCssFileName**|string|Name for the Css file, with a path relative to the htmlPath\. Note that the css will be shared among all sheets, so only one file will be created\.<br />if you set it to null, no css file created and the css will be stored inside each HTML file\. It is recommended that you provide an extenal name here, so the CSS is shared webpages are smaller\. If for example htmlpath is "c:\\reports" and relativeCssFileName is "css\\data\.css" the css file will be saved in "c:\\reports\\css\\data\.css"|
|const|**sheetSelector**|[TSheetSelector](../TSheetSelector/index.md)|Information about how to draw the tabs that will allow you to switch between the sheets\.<br />Set it to null if you do not want to include a sheet selector\.|
|const|**freeSheetSelectorAfterUse**|Boolean|**Optional**: Default value is True<br /><br />If true \(the default\) this method will free the sheetselector you pass as a parameter when it finsihes, so you don't need to free it yourself\.<br />If you have the sheetselector stored in a variable and want to reuse it, set this variable to false, or the variable will be invalid after calling this method\.<br />|
|const|**OnSheetName**|[TOnSheetName&#8203;Event&#8203;Handler](../../FlexCel.Core/TOnSheetNameEventHandler.md)|**Optional**: Default value is nil<br /><br />Use this event to customize the filename for the created files, and use something different than the sheet name\.|


## See also

* [TFlexCelHtmlExport](../TFlexCelHtmlExport/index.md)

