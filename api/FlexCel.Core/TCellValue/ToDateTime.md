---
uid: TCellValue.ToDateTime
description: TCellValue.ToDateTime
---

# TCellValue\.ToDateTime Method

Returns the value as a DateTime, if it can be converted, or DateTime\(0\) if it can't\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TCellValue/index.md">TCellValue</a>.ToDateTime(const Dates1904: Boolean): TDateTime;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**Dates1904**|Boolean|Specifies if the value is expressed in Excel 1904 date system\.<br />Normally this value is false except for files created in older Macs\.<br />You can get this value on an open file with XlsFile\.Options1904Dates\.<br />|


## See also

* [TCellValue](../TCellValue/index.md)

