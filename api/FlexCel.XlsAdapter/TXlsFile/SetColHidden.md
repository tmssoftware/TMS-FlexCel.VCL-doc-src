---
uid: TXlsFile.SetColHidden
description: TXlsFile.SetColHidden
---

# TXlsFile\.SetColHidden Method

## Overloads

* [TXlsFile\.SetColHidden\(Integer, Boolean\)](#txlsfilesetcolhiddeninteger-boolean)
* [TXlsFile\.SetColHidden\(Integer, Integer, Boolean\)](#txlsfilesetcolhiddeninteger-integer-boolean)

# TXlsFile\.SetColHidden\(Integer, Boolean\)
Hides or shows a specific column\. Note: If you are hiding many columns at the same time,  you can call [TExcelFile.SetColHidden\(Integer, Integer, Boolean\)](../../FlexCel.Core/TExcelFile/SetColHidden.md#texcelfilesetcolhiddeninteger-integer-boolean) as it is faster\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetColHidden(const col: Integer; const hide: Boolean); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**col**|Integer|Column index \(1 based\)\.|
|const|**hide**|Boolean|If true, column will be hidden, if false it will be visible\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.SetColHidden\(Integer, Integer, Boolean\)
Hides or shows a range of columns\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetColHidden(const col1: Integer; const col2: Integer; const hide: Boolean); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**col1**|Integer|Column index of the first column in the range\. \(1 based\)|
|const|**col2**|Integer|Column index of the last column in the range\. \(1 based\)|
|const|**hide**|Boolean|If true, column will be hidden, if false it will be visible\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

