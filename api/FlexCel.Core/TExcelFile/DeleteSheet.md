---
uid: TExcelFile.DeleteSheet
description: TExcelFile.DeleteSheet
---

# TExcelFile\.DeleteSheet Method

## Overloads

* [TExcelFile\.DeleteSheet\(Integer\)](#texcelfiledeletesheetinteger)
* [TExcelFile\.DeleteSheet\(string\)](#texcelfiledeletesheetstring)
* [TExcelFile\.DeleteSheet\(Integer, Integer\)](#texcelfiledeletesheetinteger-integer)

# TExcelFile\.DeleteSheet\(Integer\)
Deletes the active sheet and aSheetCount\-1 sheets more to the right\.
It will change all formula references to that sheet to invalid, and might change the active sheet so it remains valid\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.DeleteSheet(const aSheetCount: Integer); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aSheetCount**|Integer|The number of sheets to delete from the active sheet\.|


## See also

* [TExcelFile](../TExcelFile/index.md)
* [ClearSheet](ClearSheet.md)

# TExcelFile\.DeleteSheet\(string\)
Deletes the sheet with name aSheetName\.
It will change all formula references to that sheet to invalid, and might change the active sheet so it remains valid\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.DeleteSheet(const aSheetName: string); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aSheetName**|string|The name of the sheet to delete\.|


## See also

* [TExcelFile](../TExcelFile/index.md)
* [ClearSheet](ClearSheet.md)

# TExcelFile\.DeleteSheet\(Integer, Integer\)
Deletes sheet aSheet and aSheetCount\-1 sheets more to the right\.
It will change all formula references to that sheet to invalid, and might change the active sheet so it remains valid\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.DeleteSheet(const aSheet: Integer; const aSheetCount: Integer); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aSheet**|Integer|First sheet to delete \(1\-based\)\.|
|const|**aSheetCount**|Integer|The number of sheets to delete\.|


## See also

* [TExcelFile](../TExcelFile/index.md)
* [ClearSheet](ClearSheet.md)

