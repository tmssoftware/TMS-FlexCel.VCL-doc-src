---
uid: TExcelTypes.ConvertToAllowedObject
description: TExcelTypes.ConvertToAllowedObject
---

# TExcelTypes\.ConvertToAllowedObject Method

Converts an object to a native Excel datatype, that is: Number, String, Null, bool or Error\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TExcelTypes/index.md">TExcelTypes</a>.ConvertToAllowedObject(const o: <a href="../TCellValue/index.md">TCellValue</a>; const Dates1904: Boolean): <a href="../TCellValue/index.md">TCellValue</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**o**|[TCellValue](../TCellValue/index.md)|Object to convert\.|
|const|**Dates1904**|Boolean|True if using 1904 as start date\. Excel for windows normally uses 1900\.|


## See also

* [TExcelTypes](../TExcelTypes/index.md)

