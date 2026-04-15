---
uid: TExcelFile.Export
description: TExcelFile.Export
---

# TExcelFile\.Export Method

## Overloads

* [TExcelFile\.Export\(TTextWriter, TXlsCellRange, Char, Boolean\)](#texcelfileexportttextwriter-txlscellrange-char-boolean)
* [TExcelFile\.Export\(string, TXlsCellRange, Char, Boolean, TEncoding\)](#texcelfileexportstring-txlscellrange-char-boolean-tencoding)
* [TExcelFile\.Export\(TStream, TXlsCellRange, Char, Boolean, TEncoding\)](#texcelfileexporttstream-txlscellrange-char-boolean-tencoding)
* [TExcelFile\.Export\(TTextWriter, TXlsCellRange, Char, Boolean, string\)](#texcelfileexportttextwriter-txlscellrange-char-boolean-string)
* [TExcelFile\.Export\(TTextWriter, TXlsCellRange, Integer, Int32Array, Boolean\)](#texcelfileexportttextwriter-txlscellrange-integer-int32array-boolean)
* [TExcelFile\.Export\(string, TXlsCellRange, Integer, Int32Array, Boolean, TEncoding\)](#texcelfileexportstring-txlscellrange-integer-int32array-boolean-tencoding)
* [TExcelFile\.Export\(TStream, TXlsCellRange, Integer, Int32Array, Boolean, TEncoding\)](#texcelfileexporttstream-txlscellrange-integer-int32array-boolean-tencoding)
* [TExcelFile\.Export\(TTextWriter, TXlsCellRange, Integer, Int32Array, Boolean, Boolean\)](#texcelfileexportttextwriter-txlscellrange-integer-int32array-boolean-boolean)
* [TExcelFile\.Export\(string, TXlsCellRange, Integer, Int32Array, Boolean, TEncoding, Boolean\)](#texcelfileexportstring-txlscellrange-integer-int32array-boolean-tencoding-boolean)
* [TExcelFile\.Export\(TStream, TXlsCellRange, Integer, Int32Array, Boolean, TEncoding, Boolean\)](#texcelfileexporttstream-txlscellrange-integer-int32array-boolean-tencoding-boolean)
* [TExcelFile\.Export\(TTextWriter, TXlsCellRange, Integer, Int32Array, Boolean, Boolean, string\)](#texcelfileexportttextwriter-txlscellrange-integer-int32array-boolean-boolean-string)

# TExcelFile\.Export\(TTextWriter, TXlsCellRange, Char, Boolean\)
Exports a range of cells from the active sheet into a text file \(character delimited columns\)\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.Export(const aTextWriter: TTextWriter; const range: <a href="../TXlsCellRange/index.md">TXlsCellRange</a>; const delimiter: Char; const exportHiddenRowsOrColumns: Boolean); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aTextWriter**|TTextWriter|TextWriter where we want to save the file\.|
|const|**range**|[TXlsCellRange](../TXlsCellRange/index.md)|Range of cells to export\. If you want to export the full sheet, set it to null\.|
|const|**delimiter**|Char|Character used to delimit the fields in the exported file\. You might normally use a comma \(','\) or a tab here\.|
|const|**exportHiddenRowsOrColumns**|Boolean|If true, hidden rows and columns will be exported\. If false, they will be ignored\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.Export\(string, TXlsCellRange, Char, Boolean, TEncoding\)
Exports a range of cells from the active sheet into a text file \(character delimited columns\)\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.Export(const fileName: string; const range: <a href="../TXlsCellRange/index.md">TXlsCellRange</a>; const delimiter: Char; const exportHiddenRowsOrColumns: Boolean; const fileEncoding: TEncoding); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**fileName**|string|File where we want to save the data\.|
|const|**range**|[TXlsCellRange](../TXlsCellRange/index.md)|Range of cells to export\. If you want to export the full sheet, set it to null\.|
|const|**delimiter**|Char|Character used to delimit the fields in the exported file\. You might normally use a comma \(','\) or a tab here\.|
|const|**exportHiddenRowsOrColumns**|Boolean|If true, hidden rows and columns will be exported\. If false, they will be ignored\.|
|const|**fileEncoding**|TEncoding|Encoding for the generated file\. If you are unsure, you can use TUTF8EncodingNoBom\.Instance here\. Note that to create a file with BOM \(byte order marker\) you need to specify an encoding here, the same as you do with a StreamWriter\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.Export\(TStream, TXlsCellRange, Char, Boolean, TEncoding\)
Exports a range of cells from the active sheet into a text file \(character delimited columns\)\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.Export(const aStream: TStream; const range: <a href="../TXlsCellRange/index.md">TXlsCellRange</a>; const delimiter: Char; const exportHiddenRowsOrColumns: Boolean; const fileEncoding: TEncoding); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aStream**|TStream|Stream where we want to save the file\.|
|const|**range**|[TXlsCellRange](../TXlsCellRange/index.md)|Range of cells to export\. If you want to export the full sheet, set it to null\.|
|const|**delimiter**|Char|Character used to delimit the fields in the exported file\. You might normally use a comma \(','\) or a tab here\.|
|const|**exportHiddenRowsOrColumns**|Boolean|If true, hidden rows and columns will be exported\. If false, they will be ignored\.|
|const|**fileEncoding**|TEncoding|Encoding for the generated file\. If you are unsure, you can use TUTF8EncodingNoBom\.Instance here\. Note that to create a file with BOM \(byte order marker\) you need to specify an encoding here, the same as you do with a StreamWriter\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.Export\(TTextWriter, TXlsCellRange, Char, Boolean, string\)
Exports a range of cells from the active sheet into a text file \(character delimited columns\)\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.Export(const aTextWriter: TTextWriter; const range: <a href="../TXlsCellRange/index.md">TXlsCellRange</a>; const delimiter: Char; const exportHiddenRowsOrColumns: Boolean; const newLine: string); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aTextWriter**|TTextWriter|TextWriter where we want to save the file\.|
|const|**range**|[TXlsCellRange](../TXlsCellRange/index.md)|Range of cells to export\. If you want to export the full sheet, set it to null\.|
|const|**delimiter**|Char|Character used to delimit the fields in the exported file\. You might normally use a comma \(','\) or a tab here\.|
|const|**exportHiddenRowsOrColumns**|Boolean|If true, hidden rows and columns will be exported\. If false, they will be ignored\.|
|const|**newLine**|string|String used to separate lines\. If not specified, this will be the string used in the OS\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.Export\(TTextWriter, TXlsCellRange, Integer, Int32Array, Boolean\)
Exports a range of cells from the active sheet into a text file \(fixed length columns\)\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.Export(const aTextWriter: TTextWriter; const range: <a href="../TXlsCellRange/index.md">TXlsCellRange</a>; const charactersForFirstColumn: Integer; const columnWidths: TArray&lt;Int32>; const exportHiddenRowsOrColumns: Boolean); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aTextWriter**|TTextWriter|TextWriter where we want to save the file\.|
|const|**range**|[TXlsCellRange](../TXlsCellRange/index.md)|Range of cells to export\. If you want to export the full sheet, set it to null\.|
|const|**charactersForFirstColumn**|Integer|This value only has effect if columnWidths is null\. It will specify how many characters to use for the first column, and all other columns will be determined according to their ratio with the first\.<br />For example, if the first column is 150 pixels wide and you specify "8" for this parameter, the first column will be padded to 8 characters when exporting\.<br />If the second column is 300 pixels wide, then it will be padded to 16 characters and so on\. As this might not be 100%% exact and depend in pixel measurements, you might want to specify columnWidths parameter instead of using this one\.<br /><br />Note: Setting this parameter to a negative value will assume the text in the columns is already padded, and won't attempt to do any padding\.<br />Use this value if your data is padded in the spreadsheet itself\.<br />|
|const|**columnWidths**|TArray\<Int32>|Array with the number of characters that will be assigned to every column when exporting\. Supplying this array allows you to specify exactly how many characters you want for every field, and that might be really necessary to interop with other applications\.<br />But you can also leave this parameter null and specify "charactersForFirstColumn" to let FlexCel calculate how many characters to apply for every field\.|
|const|**exportHiddenRowsOrColumns**|Boolean|If true, hidden rows and columns will be exported\. If false, they will be ignored\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.Export\(string, TXlsCellRange, Integer, Int32Array, Boolean, TEncoding\)
Exports a range of cells from the active sheet into a text file \(fixed length columns\)\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.Export(const fileName: string; const range: <a href="../TXlsCellRange/index.md">TXlsCellRange</a>; const charactersForFirstColumn: Integer; const columnWidths: TArray&lt;Int32>; const exportHiddenRowsOrColumns: Boolean; const fileEncoding: TEncoding); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**fileName**|string|File where we want to save the data\.|
|const|**range**|[TXlsCellRange](../TXlsCellRange/index.md)|Range of cells to export\. If you want to export the full sheet, set it to null\.|
|const|**charactersForFirstColumn**|Integer|This value only has effect if columnWidths is null\. It will specify how many characters to use for the first column, and all other columns will be determined according to their ratio with the first\.<br />For example, if the first column is 150 pixels wide and you specify "8" for this parameter, the first column will be padded to 8 characters when exporting\.<br />If the second column is 300 pixels wide, then it will be padded to 16 characters and so on\. As this might not be 100%% exact and depend in pixel measurements, you might want to specify columnWidths parameter instead of using this one\.<br /><br />Note: Setting this parameter to a negative value will assume the text in the columns is already padded, and won't attempt to do any padding\.<br />Use this value if your data is padded in the spreadsheet itself\.<br />|
|const|**columnWidths**|TArray\<Int32>|Array with the number of characters that will be assigned to every column when exporting\. Supplying this array allows you to specify exactly how many characters you want for every field, and that might be really necessary to interop with other applications\.<br />But you can also leave this parameter null and specify "charactersForFirstColumn" to let FlexCel calculate how many characters to apply for every field\.|
|const|**exportHiddenRowsOrColumns**|Boolean|If true, hidden rows and columns will be exported\. If false, they will be ignored\.|
|const|**fileEncoding**|TEncoding|Encoding for the generated file\. If you are unsure, you can use TUTF8EncodingNoBom\.Instance here\. Note that to create a file with BOM \(byte order marker\) you need to specify an encoding here, the same as you do with a StreamWriter\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.Export\(TStream, TXlsCellRange, Integer, Int32Array, Boolean, TEncoding\)
Exports a range of cells from the active sheet into a text file \(fixed length columns\)\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.Export(const aStream: TStream; const range: <a href="../TXlsCellRange/index.md">TXlsCellRange</a>; const charactersForFirstColumn: Integer; const columnWidths: TArray&lt;Int32>; const exportHiddenRowsOrColumns: Boolean; const fileEncoding: TEncoding); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aStream**|TStream|Stream where we want to save the file\.|
|const|**range**|[TXlsCellRange](../TXlsCellRange/index.md)|Range of cells to export\. If you want to export the full sheet, set it to null\.|
|const|**charactersForFirstColumn**|Integer|This value only has effect if columnWidths is null\. It will specify how many characters to use for the first column, and all other columns will be determined according to their ratio with the first\.<br />For example, if the first column is 150 pixels wide and you specify "8" for this parameter, the first column will be padded to 8 characters when exporting\.<br />If the second column is 300 pixels wide, then it will be padded to 16 characters and so on\. As this might not be 100%% exact and depend in pixel measurements, you might want to specify columnWidths parameter instead of using this one\.<br /><br />Note: Setting this parameter to a negative value will assume the text in the columns is already padded, and won't attempt to do any padding\.<br />Use this value if your data is padded in the spreadsheet itself\.<br />|
|const|**columnWidths**|TArray\<Int32>|Array with the number of characters that will be assigned to every column when exporting\. Supplying this array allows you to specify exactly how many characters you want for every field, and that might be really necessary to interop with other applications\.<br />But you can also leave this parameter null and specify "charactersForFirstColumn" to let FlexCel calculate how many characters to apply for every field\.|
|const|**exportHiddenRowsOrColumns**|Boolean|If true, hidden rows and columns will be exported\. If false, they will be ignored\.|
|const|**fileEncoding**|TEncoding|Encoding for the generated file\. If you are unsure, you can use TUTF8EncodingNoBom\.Instance here\. Note that to create a file with BOM \(byte order marker\) you need to specify an encoding here, the same as you do with a StreamWriter\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.Export\(TTextWriter, TXlsCellRange, Integer, Int32Array, Boolean, Boolean\)
Exports a range of cells from the active sheet into a text file \(fixed length columns\)\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.Export(const aTextWriter: TTextWriter; const range: <a href="../TXlsCellRange/index.md">TXlsCellRange</a>; const charactersForFirstColumn: Integer; const columnWidths: TArray&lt;Int32>; const exportHiddenRowsOrColumns: Boolean; const exportTextOutsideCells: Boolean); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aTextWriter**|TTextWriter|TextWriter where we want to save the file\.|
|const|**range**|[TXlsCellRange](../TXlsCellRange/index.md)|Range of cells to export\. If you want to export the full sheet, set it to null\.|
|const|**charactersForFirstColumn**|Integer|This value only has effect if columnWidths is null\. It will specify how many characters to use for the first column, and all other columns will be determined according to their ratio with the first\.<br />For example, if the first column is 150 pixels wide and you specify "8" for this parameter, the first column will be padded to 8 characters when exporting\.<br />If the second column is 300 pixels wide, then it will be padded to 16 characters and so on\. As this might not be 100%% exact and depend in pixel measurements, you might want to specify columnWidths parameter instead of using this one\.<br /><br />Note: Setting this parameter to a negative value will assume the text in the columns is already padded, and won't attempt to do any padding\.<br />Use this value if your data is padded in the spreadsheet itself\.<br />|
|const|**columnWidths**|TArray\<Int32>|Array with the number of characters that will be assigned to every column when exporting\. Supplying this array allows you to specify exactly how many characters you want for every field, and that might be really necessary to interop with other applications\.<br />But you can also leave this parameter null and specify "charactersForFirstColumn" to let FlexCel calculate how many characters to apply for every field\.|
|const|**exportHiddenRowsOrColumns**|Boolean|If true, hidden rows and columns will be exported\. If false, they will be ignored\.|
|const|**exportTextOutsideCells**|Boolean|If true and the cell text spans over more than one empty cell to the right, that text will be exported\. When false \(the default\) only text that fits in the cell will be exported\.<br />When this value is true the printout will look better, but it will not be possible to reimport the data as the columns are lost\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.Export\(string, TXlsCellRange, Integer, Int32Array, Boolean, TEncoding, Boolean\)
Exports a range of cells from the active sheet into a text file \(fixed length columns\)\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.Export(const fileName: string; const range: <a href="../TXlsCellRange/index.md">TXlsCellRange</a>; const charactersForFirstColumn: Integer; const columnWidths: TArray&lt;Int32>; const exportHiddenRowsOrColumns: Boolean; const fileEncoding: TEncoding; const exportTextOutsideCells: Boolean); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**fileName**|string|File where we want to save the data\.|
|const|**range**|[TXlsCellRange](../TXlsCellRange/index.md)|Range of cells to export\. If you want to export the full sheet, set it to null\.|
|const|**charactersForFirstColumn**|Integer|This value only has effect if columnWidths is null\. It will specify how many characters to use for the first column, and all other columns will be determined according to their ratio with the first\.<br />For example, if the first column is 150 pixels wide and you specify "8" for this parameter, the first column will be padded to 8 characters when exporting\.<br />If the second column is 300 pixels wide, then it will be padded to 16 characters and so on\. As this might not be 100%% exact and depend in pixel measurements, you might want to specify columnWidths parameter instead of using this one\.<br /><br />Note: Setting this parameter to a negative value will assume the text in the columns is already padded, and won't attempt to do any padding\.<br />Use this value if your data is padded in the spreadsheet itself\.<br />|
|const|**columnWidths**|TArray\<Int32>|Array with the number of characters that will be assigned to every column when exporting\. Supplying this array allows you to specify exactly how many characters you want for every field, and that might be really necessary to interop with other applications\.<br />But you can also leave this parameter null and specify "charactersForFirstColumn" to let FlexCel calculate how many characters to apply for every field\.|
|const|**exportHiddenRowsOrColumns**|Boolean|If true, hidden rows and columns will be exported\. If false, they will be ignored\.|
|const|**fileEncoding**|TEncoding|Encoding for the generated file\. If you are unsure, you can use TUTF8EncodingNoBom\.Instance here\. Note that to create a file with BOM \(byte order marker\) you need to specify an encoding here, the same as you do with a StreamWriter\.|
|const|**exportTextOutsideCells**|Boolean|If true and the cell text spans over more than one empty cell to the right, that text will be exported\. When false \(the default\) only text that fits in the cell will be exported\.<br />When this value is true the printout will look better, but it will not be possible to reimport the data as the columns are lost\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.Export\(TStream, TXlsCellRange, Integer, Int32Array, Boolean, TEncoding, Boolean\)
Exports a range of cells from the active sheet into a text file \(fixed length columns\)\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.Export(const aStream: TStream; const range: <a href="../TXlsCellRange/index.md">TXlsCellRange</a>; const charactersForFirstColumn: Integer; const columnWidths: TArray&lt;Int32>; const exportHiddenRowsOrColumns: Boolean; const fileEncoding: TEncoding; const exportTextOutsideCells: Boolean); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aStream**|TStream|Stream where we want to save the file\.|
|const|**range**|[TXlsCellRange](../TXlsCellRange/index.md)|Range of cells to export\. If you want to export the full sheet, set it to null\.|
|const|**charactersForFirstColumn**|Integer|This value only has effect if columnWidths is null\. It will specify how many characters to use for the first column, and all other columns will be determined according to their ratio with the first\.<br />For example, if the first column is 150 pixels wide and you specify "8" for this parameter, the first column will be padded to 8 characters when exporting\.<br />If the second column is 300 pixels wide, then it will be padded to 16 characters and so on\. As this might not be 100%% exact and depend in pixel measurements, you might want to specify columnWidths parameter instead of using this one\.<br /><br />Note: Setting this parameter to a negative value will assume the text in the columns is already padded, and won't attempt to do any padding\.<br />Use this value if your data is padded in the spreadsheet itself\.<br />|
|const|**columnWidths**|TArray\<Int32>|Array with the number of characters that will be assigned to every column when exporting\. Supplying this array allows you to specify exactly how many characters you want for every field, and that might be really necessary to interop with other applications\.<br />But you can also leave this parameter null and specify "charactersForFirstColumn" to let FlexCel calculate how many characters to apply for every field\.|
|const|**exportHiddenRowsOrColumns**|Boolean|If true, hidden rows and columns will be exported\. If false, they will be ignored\.|
|const|**fileEncoding**|TEncoding|Encoding for the generated file\. If you are unsure, you can use TUTF8EncodingNoBom\.Instance here\. Note that to create a file with BOM \(byte order marker\) you need to specify an encoding here, the same as you do with a StreamWriter\.|
|const|**exportTextOutsideCells**|Boolean|If true and the cell text spans over more than one empty cell to the right, that text will be exported\. When false \(the default\) only text that fits in the cell will be exported\.<br />When this value is true the printout will look better, but it will not be possible to reimport the data as the columns are lost\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.Export\(TTextWriter, TXlsCellRange, Integer, Int32Array, Boolean, Boolean, string\)
Exports a range of cells from the active sheet into a text file \(fixed length columns\)\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.Export(const aTextWriter: TTextWriter; const range: <a href="../TXlsCellRange/index.md">TXlsCellRange</a>; const charactersForFirstColumn: Integer; const columnWidths: TArray&lt;Int32>; const exportHiddenRowsOrColumns: Boolean; const exportTextOutsideCells: Boolean; const newLine: string); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aTextWriter**|TTextWriter|TextWriter where we want to save the file\.|
|const|**range**|[TXlsCellRange](../TXlsCellRange/index.md)|Range of cells to export\. If you want to export the full sheet, set it to null\.|
|const|**charactersForFirstColumn**|Integer|This value only has effect if columnWidths is null\. It will specify how many characters to use for the first column, and all other columns will be determined according to their ratio with the first\.<br />For example, if the first column is 150 pixels wide and you specify "8" for this parameter, the first column will be padded to 8 characters when exporting\.<br />If the second column is 300 pixels wide, then it will be padded to 16 characters and so on\. As this might not be 100%% exact and depend in pixel measurements, you might want to specify columnWidths parameter instead of using this one\.<br /><br />Note: Setting this parameter to a negative value will assume the text in the columns is already padded, and won't attempt to do any padding\.<br />Use this value if your data is padded in the spreadsheet itself\.<br />|
|const|**columnWidths**|TArray\<Int32>|Array with the number of characters that will be assigned to every column when exporting\. Supplying this array allows you to specify exactly how many characters you want for every field, and that might be really necessary to interop with other applications\.<br />But you can also leave this parameter null and specify "charactersForFirstColumn" to let FlexCel calculate how many characters to apply for every field\.|
|const|**exportHiddenRowsOrColumns**|Boolean|If true, hidden rows and columns will be exported\. If false, they will be ignored\.|
|const|**exportTextOutsideCells**|Boolean|If true and the cell text spans over more than one empty cell to the right, that text will be exported\. When false \(the default\) only text that fits in the cell will be exported\.<br />When this value is true the printout will look better, but it will not be possible to reimport the data as the columns are lost\.|
|const|**newLine**|string|String used to separate lines in the output\. If omitted, we will use the OS new line separator\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

