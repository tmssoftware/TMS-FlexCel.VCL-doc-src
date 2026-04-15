---
uid: TExcelFile.GetNamedRange
description: TExcelFile.GetNamedRange
---

# TExcelFile\.GetNamedRange Method

## Overloads

* [TExcelFile\.GetNamedRange\(Integer\)](#texcelfilegetnamedrangeinteger)
* [TExcelFile\.GetNamedRange\(string, Integer\)](#texcelfilegetnamedrangestring-integer)
* [TExcelFile\.GetNamedRange\(string, Integer, Integer\)](#texcelfilegetnamedrangestring-integer-integer)

# TExcelFile\.GetNamedRange\(Integer\)
Returns the Named Range Definition\. If the range is not user defined \(like "Print\_Area"\) it will have a one\-char name, and the value is on the enum [TInternalNameRange](../TInternalNameRange.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetNamedRange(const index: Integer): <a href="../TXlsNamedRange/index.md">TXlsNamedRange</a>; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**index**|Integer|Index of the named range\.|


## Returns

Named Range

## See also

* [TExcelFile](../TExcelFile/index.md)
* [TInternalNameRange](../TInternalNameRange.md)

# TExcelFile\.GetNamedRange\(string, Integer\)
Returns the Named Range Definition\. If the range is not user defined \(like "Print\_Area"\) it will have a one\-char name, and the value is on the enum [TInternalNameRange](../TInternalNameRange.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetNamedRange(const Name: string; const refersToSheetIndex: Integer): <a href="../TXlsNamedRange/index.md">TXlsNamedRange</a>; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**Name**|string|Name of the range we are looking for\. Case insensitive\.|
|const|**refersToSheetIndex**|Integer|Sheet where the range refers to\. A range with the same name might be defined on more than one sheet\.<br /><br />To get the first range with the name, make refersToSheetIndex\<=0<br />Note that a name can be stored in one sheet and refer to a different sheet\. Or it might not refer to any sheet at all\. \(for example, the name "=name1\+1" doesn't refer to any sheet\.\) And you could have a name "=Sheet1\!a1" defined in sheet2\. This name will "refer to" sheet1, but be defined in sheet2\.<br /><br />While names are normally all defined globally \(sheet 0\), if you need to get the names that are stored in a specific sheet, use [GetNamedRange\(string, Integer, Integer\)](GetNamedRange.md#texcelfilegetnamedrangestring-integer-integer) instead\.|


## Returns

Named Range or null if the range does not exist\.

## See also

* [TExcelFile](../TExcelFile/index.md)
* [TInternalNameRange](../TInternalNameRange.md)

# TExcelFile\.GetNamedRange\(string, Integer, Integer\)
Returns the Named Range Definition\. If the range is not user defined \(like "Print\_Area"\) it will have a one\-char name, and the value is on the enum [TInternalNameRange](../TInternalNameRange.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetNamedRange(const Name: string; const refersToSheetIndex: Integer; const localSheetIndex: Integer): <a href="../TXlsNamedRange/index.md">TXlsNamedRange</a>; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**Name**|string|Name of the range we are looking for\. Case insensitive\.|
|const|**refersToSheetIndex**|Integer|Sheet where the range refers to\. Note that this is **not** where the name is stored\. Normally names are all stored globally \(in sheet 0\), but they refer to a specific sheet\. For example, if you define the name "=Sheet2\!a1" globally, it will be stored in sheet 0, but will refer to sheet2\.<br /><br />A name like "=Sheet1:Sheet2\!A1 doesn't refer to any sheet\.|
|const|**localSheetIndex**|Integer|Sheet where the range is stored\. A range might be stored local to a sheet, or global \(Excel default\)\.<br />To get a global range, make localSheetIndex = 0|


## Returns

Named Range or null if the range does not exist\.

## See also

* [TExcelFile](../TExcelFile/index.md)
* [TInternalNameRange](../TInternalNameRange.md)

