---
uid: TExcelFile.SetColHidden
description: TExcelFile.SetColHidden
---

# TExcelFile\.SetColHidden Method

## Overloads

* [TExcelFile\.SetColHidden\(Integer, Boolean\)](#texcelfilesetcolhiddeninteger-boolean)
* [TExcelFile\.SetColHidden\(Integer, Integer, Boolean\)](#texcelfilesetcolhiddeninteger-integer-boolean)

# TExcelFile\.SetColHidden\(Integer, Boolean\)
Hides or shows a specific column\. Note: If you are hiding many columns at the same time,  you can call [SetColHidden\(Integer, Integer, Boolean\)](SetColHidden.md#texcelfilesetcolhiddeninteger-integer-boolean) as it is faster\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetColHidden(const col: Integer; const hide: Boolean); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**col**|Integer|Column index \(1 based\)\.|
|const|**hide**|Boolean|If true, column will be hidden, if false it will be visible\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.SetColHidden\(Integer, Integer, Boolean\)
Hides or shows a range of columns\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetColHidden(const col1: Integer; const col2: Integer; const hide: Boolean); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**col1**|Integer|Column index of the first column in the range\. \(1 based\)|
|const|**col2**|Integer|Column index of the last column in the range\. \(1 based\)|
|const|**hide**|Boolean|If true, column will be hidden, if false it will be visible\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

