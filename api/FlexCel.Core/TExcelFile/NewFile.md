---
uid: TExcelFile.NewFile
description: TExcelFile.NewFile
---

# TExcelFile\.NewFile Method

## Overloads

* [TExcelFile\.NewFile](#texcelfilenewfile)
* [TExcelFile\.NewFile\(Integer\)](#texcelfilenewfileinteger)
* [TExcelFile\.NewFile\(Integer, TExcelFileFormat\)](#texcelfilenewfileinteger-texcelfileformat)

# TExcelFile\.NewFile
Creates a new empty file, with 3 empty sheets\.


## Remarks

The file created will have empty properties, \(author, description, etc\)\.
If you want to create a more personalized file when you call NewFile  \(for example with a given Author, or the sheets names on your language\), there are 2 options:
1. Don't use NewFile, but open an existing file you can modify\.
2. Or, you can replace the file "EmptyWorkbook\.xls" \(on xlsadapter folder\) with your own and recompile\.<br />



## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.NewFile; overload;</code></pre>

## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.NewFile\(Integer\)
Creates a new empty file, with the specified number of sheets\.


## Remarks

The file created will have empty properties, \(author, description, etc\)\.
If you want to create a more personalized file when you call NewFile  \(for example with a given Author, or the sheets names on your language\), there are 2 options:
1. Don't use NewFile, but open an existing file you can modify\.
2. Or, you can replace the files "EmptyWorkbook\.xls", "EmptyWorkbook2007\.xls" and "EmptyWorkbook2010\.xls" \(on xlsadapter folder\) with your own and recompile\.<br />



## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.NewFile(const aSheetCount: Integer); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aSheetCount**|Integer|Number of sheets for the new file\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.NewFile\(Integer, TExcelFileFormat\)
Creates a new empty file, with the specified number of sheets\.


## Remarks

The file created will have empty properties, \(author, description, etc\)\.
If you want to create a more personalized file when you call NewFile  \(for example with a given Author, or the sheets names on your language\), there are 2 options:
1. Don't use NewFile, but open an existing file you can modify\.
2. Or, you can replace the files "EmptyWorkbook\.xls", "EmptyWorkbook2007\.xls" and "EmptyWorkbook2010\.xls" \(on xlsadapter folder\) with your own and recompile\.<br />



## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.NewFile(const aSheetCount: Integer; const fileFormat: <a href="../TExcelFileFormat.md">TExcelFileFormat</a>); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aSheetCount**|Integer|Number of sheets for the new file\.|
|const|**fileFormat**|[TExcelFileFormat](../TExcelFileFormat.md)|Different Excel versions save different empty files\. By default, FlexCel will create a new file that looks like a file created by Excel 2003, but you can change the version of the new file created with this parameter\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

