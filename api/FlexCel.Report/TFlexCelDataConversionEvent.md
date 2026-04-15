---
uid: TFlexCelDataConversionEvent
description: TFlexCelDataConversionEvent
---

# TFlexCelDataConversionEvent Anonymous method

A function to convert a class, record or array into a value FlexCel can write in the template\.


"v": Value to be converted\.


"ConvertedValue": In this variable you need to return the converted value\.


## Syntax

**Unit:** [FlexCel.Report](index.md)

<pre><code class="lang-delphi hljs">TFlexCelDataConversionEvent = reference to function(const v: <a href="TFlexCelDataConversionArgs/index.md">TFlexCelDataConversionArgs</a>; out ConvertedValue: <a href="TReportValue/index.md">TReportValue</a>): Boolean;</code></pre>
