---
uid: TXlsFile.FindNamedRange
description: TXlsFile.FindNamedRange
---

# TXlsFile\.FindNamedRange Method

Returns the index \(1 based\) on the list of named ranges for a given name and local sheet\. If the range is not found, this method will return \-1 You could use [TExcelFile.GetNamedRange\(Integer\)](../../FlexCel.Core/TExcelFile/GetNamedRange.md#texcelfilegetnamedrangeinteger) to get the name definition, or directly call [TExcelFile.GetNamedRange\(string, Integer, Integer\)](../../FlexCel.Core/TExcelFile/GetNamedRange.md#texcelfilegetnamedrangestring-integer-integer) to get a named range knowing its name and sheet position\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.FindNamedRange(const Name: string; const localSheetIndex: Integer): Integer; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**Name**|string|Name of the range we are looking for\. Case insensitive\.|
|const|**localSheetIndex**|Integer|Sheet where the range is stored\. A range might be stored local to a sheet, or global \(Excel default\)\.<br />To get a global range, make localSheetIndex=0|


## Returns

The index \(1 based\) in the list of named ranges, or \-1 if the range is not found\.

## See also

* [TXlsFile](../TXlsFile/index.md)

