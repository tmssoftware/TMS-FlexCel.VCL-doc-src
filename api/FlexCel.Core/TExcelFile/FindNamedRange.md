---
uid: TExcelFile.FindNamedRange
description: TExcelFile.FindNamedRange
---

# TExcelFile\.FindNamedRange Method

Returns the index \(1 based\) on the list of named ranges for a given name and local sheet\. If the range is not found, this method will return \-1 You could use [GetNamedRange\(Integer\)](GetNamedRange.md#texcelfilegetnamedrangeinteger) to get the name definition, or directly call [GetNamedRange\(string, Integer, Integer\)](GetNamedRange.md#texcelfilegetnamedrangestring-integer-integer) to get a named range knowing its name and sheet position\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.FindNamedRange(const Name: string; const localSheetIndex: Integer): Integer; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**Name**|string|Name of the range we are looking for\. Case insensitive\.|
|const|**localSheetIndex**|Integer|Sheet where the range is stored\. A range might be stored local to a sheet, or global \(Excel default\)\.<br />To get a global range, make localSheetIndex=0|


## Returns

The index \(1 based\) in the list of named ranges, or \-1 if the range is not found\.

## See also

* [TExcelFile](../TExcelFile/index.md)

