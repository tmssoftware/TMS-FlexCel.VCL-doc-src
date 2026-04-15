---
uid: TExcelFile.GetNamedRangeData
description: TExcelFile.GetNamedRangeData
---

# TExcelFile\.GetNamedRangeData Method

## Overloads

* [TExcelFile\.GetNamedRangeData\(Integer, string, Boolean, Boolean\)](#texcelfilegetnamedrangedatainteger-string-boolean-boolean)
* [TExcelFile\.GetNamedRangeData\(Integer, Integer, string, string, Integer, Boolean, Boolean\)](#texcelfilegetnamedrangedatainteger-integer-string-string-integer-boolean-boolean)

# TExcelFile\.GetNamedRangeData\(Integer, string, Boolean, Boolean\)
Internal use\. We could call GetNamedRange, but this one is faster\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetNamedRangeData(const nameIndex: Integer; out externalName: string; out isAddin: Boolean; out Error: Boolean): TParsedTokenList; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**nameIndex**|Integer||
|out|**externalName**|string||
|out|**isAddin**|Boolean||
|out|**Error**|Boolean||


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.GetNamedRangeData\(Integer, Integer, string, string, Integer, Boolean, Boolean\)
Internal use\. We could call GetNamedRange, but this one is faster\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetNamedRangeData(const externSheetIndex: Integer; const externNameIndex: Integer; out externalBook: string; out externalName: string; out sheetIndexInOtherFile: Integer; out isAddin: Boolean; out Error: Boolean): TParsedTokenList; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**externSheetIndex**|Integer||
|const|**externNameIndex**|Integer||
|out|**externalBook**|string||
|out|**externalName**|string||
|out|**sheetIndexInOtherFile**|Integer||
|out|**isAddin**|Boolean||
|out|**Error**|Boolean||


## See also

* [TExcelFile](../TExcelFile/index.md)

