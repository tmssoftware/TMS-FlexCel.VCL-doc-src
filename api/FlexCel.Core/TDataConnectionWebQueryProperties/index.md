---
uid: TDataConnectionWebQueryProperties
description: TDataConnectionWebQueryProperties
---

# TDataConnectionWebQueryProperties Class

This element specifies the properties for a web query source\. A web query will retrieve data from HTML tables, and can also supply HTTP "Get" parameters to be processed by the web server in generating the HTML by including the parameters and parameter elements\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TDataConnectionWebQueryProperties = class(TFlexCelObject);</code></pre>

## Methods

|Name|Description|
|---|---|
|[Equals](Equals.md)|Returns true if both objects are the same\.<br />|
|[GetHashCode](GetHashCode.md)|Returns the hashcode of the object\.<br />|


## Properties

|Name|Description|
|---|---|
|[EditPage](EditPage.md)|The URL of the user\-facing web page showing the web query data\. This URL is persisted in the case that sourceData = "true" and url has been redirected to reference an XML file\.<br />Then the user\-facing page can be shown in the UI, and the XML data can be retrieved behind the scenes\.<br />|
|[HtmlFormat](HtmlFormat.md)|How to handle formatting from the HTML source when bringing web query data into the worksheet\. Relevant when SourceData is True\.<br />|
|[HtmlTables](HtmlTables.md)|Flag indicating whether web queries should only work on HTML tables\.<br />|
|[Post](Post.md)|Returns or sets the string used with the post method of inputting data into a web server to return data from a web query\.<br />|
|[Url](Url.md)|URL to use to refresh external data\.<br />|
|[Xl2000](Xl2000.md)|This flag exists for backward compatibility with older existing spreadsheet files, and is set to true if this web query was refreshed in a spreadsheet application newer than or equal to Microsoft Excel 2000\.<br />This is an optional attribute that can be ignored\.<br />|
|[TextDates](TextDates.md)|Flag indicating whether dates should be imported into cells in the worksheet as text rather than dates\.<br />|
|[Xl97](Xl97.md)|This flag exists for backward compatibility with older existing spreadhseet files, and is set to true if this web query was created in Microsoft Excel 97\.<br />This is an optional attribute that can be ignored\.<br />|
|[FirstRow](FirstRow.md)|Flag indicating whether to parse all tables inside a PRE block with the same width settings as the first row\.<br />|
|[ConsecutiveDelimiters](ConsecutiveDelimiters.md)|Flag indicating whether consecutive delimiters should be treated as just one delimiter\.<br />|
|[ParsePre](ParsePre.md)|Flag indicating whether data contained within HTML \<PRE> tags in the web page is parsed into columns when you import the page into a query table\.<br />|
|[SourceData](SourceData.md)|Flag indicating that XML source data should be imported instead of the HTML table itself\.<br />|
|[Xml](Xml.md)|true if the web query source is XML \(versus HTML\)\.<br />|
|[Tables](Tables.md)|A collection of tables in the HTML file\. This property is never null, and by modifying it you modify the parent WebQueryProperties too\.<br />|


