---
uid: TExcelFile.GetFormat
description: TExcelFile.GetFormat
---

# TExcelFile\.GetFormat Method

Returns the format definition for a given format index\. **Note that this method will only return Cell formats\. If you want to read a Style format, use [GetStyle\(Integer\)](GetStyle.md#texcelfilegetstyleinteger)**

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetFormat(const XF: Integer): <a href="../TFlxFormat/index.md">TFlxFormat</a>; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**XF**|Integer|Format index 0\-Based|


## Returns

Format definition

## See also

* [TExcelFile](../TExcelFile/index.md)

