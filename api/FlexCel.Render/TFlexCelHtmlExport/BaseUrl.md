---
uid: TFlexCelHtmlExport.BaseUrl
description: TFlexCelHtmlExport.BaseUrl
---

# TFlexCelHtmlExport.BaseUrl Property

If this property is not null, all hyperlinks stating with this value will be converted to relative links, by removing this string from them\.

Hyperlinks in Excel must be absolute by default, so this property is a way to get relative hyperlinks\.

For example, if BaseUrl is "https://www\.tmssoftware\.com/" and an Excel file has a link "https://www\.tmssoftware\.com/test\.html" the link in the generated HTML file will be "test\.html"

## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TFlexCelHtmlExport/index.md">TFlexCelHtmlExport</a>.BaseUrl: string</code></pre>

## See also

* [TFlexCelHtmlExport](../TFlexCelHtmlExport/index.md)

