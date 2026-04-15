---
uid: TFlexCelReport.ResolveString
description: TFlexCelReport.ResolveString
---

# TFlexCelReport\.ResolveString Method

This is the method that does the parsing\. Could be made virtual and override it on a descendant class to support  self defined Tags\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TFlexCelReport/index.md">TFlexCelReport</a>.ResolveString(const s: <a href="../../FlexCel.Core/TCellValue/index.md">TCellValue</a>; const XF: Integer; const CurrentBand: TBand; const Row: Integer; const Col: Integer): <a href="../TOneCellValue/index.md">TOneCellValue</a>; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**s**|[TCellValue](../../FlexCel.Core/TCellValue/index.md)|String to parse\.|
|const|**XF**|Integer|Original XF of the cell\. The value returned might change it, if for example there is a \#FormatCell tag\.|
|const|**CurrentBand**|TBand|The band we are currently in\.|
|const|**Row**|Integer|Row where the cell is\.|
|const|**Col**|Integer|Column where the cell is\.|


## Returns

A parsed class, with values replaced by tags found on s\.

## See also

* [TFlexCelReport](../TFlexCelReport/index.md)

