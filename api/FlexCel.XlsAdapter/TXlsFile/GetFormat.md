---
uid: TXlsFile.GetFormat
description: TXlsFile.GetFormat
---

# TXlsFile\.GetFormat Method

Returns the format definition for a given format index\. **Note that this method will only return Cell formats\. If you want to read a Style format, use [TExcelFile.GetStyle\(Integer\)](../../FlexCel.Core/TExcelFile/GetStyle.md#texcelfilegetstyleinteger)**

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetFormat(const XF: Integer): <a href="../../FlexCel.Core/TFlxFormat/index.md">TFlxFormat</a>; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**XF**|Integer|Format index 0\-Based|


## Returns

Format definition

## See also

* [TXlsFile](../TXlsFile/index.md)

