---
uid: TExcelFile.Open
description: TExcelFile.Open
---

# TExcelFile\.Open Method

## Overloads

* [TExcelFile\.Open\(string\)](#texcelfileopenstring)
* [TExcelFile\.Open\(TStream\)](#texcelfileopentstream)
* [TExcelFile\.Open\(string, TFileFormats, Char, Integer, Integer, TColumnImportTypeArray\)](#texcelfileopenstring-tfileformats-char-integer-integer-tcolumnimporttypearray)
* [TExcelFile\.Open\(TStream, TFileFormats, Char, Integer, Integer, TColumnImportTypeArray\)](#texcelfileopentstream-tfileformats-char-integer-integer-tcolumnimporttypearray)
* [TExcelFile\.Open\(TStream, TFileFormats, Char, Integer, Integer, TColumnImportTypeArray, Boolean\)](#texcelfileopentstream-tfileformats-char-integer-integer-tcolumnimporttypearray-boolean)
* [TExcelFile\.Open\(string, TFileFormats, Char, Integer, Integer, TColumnImportTypeArray, TEncoding, Boolean\)](#texcelfileopenstring-tfileformats-char-integer-integer-tcolumnimporttypearray-tencoding-boolean)
* [TExcelFile\.Open\(TStream, TFileFormats, Char, Integer, Integer, TColumnImportTypeArray, TEncoding, Boolean\)](#texcelfileopentstream-tfileformats-char-integer-integer-tcolumnimporttypearray-tencoding-boolean)
* [TExcelFile\.Open\(string, TFileFormats, Char, Integer, Integer, TColumnImportTypeArray, TArray\<string>, TEncoding, Boolean\)](#texcelfileopenstring-tfileformats-char-integer-integer-tcolumnimporttypearray-tarraystring-tencoding-boolean)
* [TExcelFile\.Open\(TStream, TFileFormats, Char, Integer, Integer, TColumnImportTypeArray, TArray\<string>, TEncoding, Boolean\)](#texcelfileopentstream-tfileformats-char-integer-integer-tcolumnimporttypearray-tarraystring-tencoding-boolean)

# TExcelFile\.Open\(string\)
Loads a new Spreadsheet from disk\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.Open(const fileName: string); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**fileName**|string|File to open\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.Open\(TStream\)
Loads a new Spreadsheet from a stream\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.Open(const aStream: TStream); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aStream**|TStream|Stream to Load, must be a seekable stream\. Verify it is on the correct position\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.Open\(string, TFileFormats, Char, Integer, Integer, TColumnImportTypeArray\)
Loads a new Spreadsheet from disk, on one of the specified formats\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.Open(const fileName: string; const fileFormat: <a href="../TFileFormats.md">TFileFormats</a>; const delimiter: Char; const firstRow: Integer; const firstCol: Integer; const columnFormats: <a href="../TColumnImportType.md">TArray&lt;TColumnImportType></a>); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**fileName**|string|File to open|
|const|**fileFormat**|[TFileFormats](../TFileFormats.md)|List with possible file formats to try|
|const|**delimiter**|Char|Delimiter used to separate columns, if the format is [TFileFormats.Text](../TFileFormats.md)|
|const|**firstRow**|Integer|First row where we will copy the cells on the new sheet, for [TFileFormats.Text](../TFileFormats.md)|
|const|**firstCol**|Integer|First column where we will copy the cells on the new sheet, for [TFileFormats.Text](../TFileFormats.md)|
|const|**columnFormats**|[TArray\<&#8203;TColumn&#8203;Import&#8203;Type>](../TColumnImportType.md)|An array of [TColumnImportType](../TColumnImportType.md) elements, telling how each column should be imported\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.Open\(TStream, TFileFormats, Char, Integer, Integer, TColumnImportTypeArray\)
Loads a new Spreadsheet from a stream, on one of the specified formats\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.Open(const aStream: TStream; const fileFormat: <a href="../TFileFormats.md">TFileFormats</a>; const delimiter: Char; const firstRow: Integer; const firstCol: Integer; const columnFormats: <a href="../TColumnImportType.md">TArray&lt;TColumnImportType></a>); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aStream**|TStream|Stream to open, must be a seekable stream\. Verify it is on the correct position\.|
|const|**fileFormat**|[TFileFormats](../TFileFormats.md)|List with possible file formats to try\.|
|const|**delimiter**|Char|Delimiter used to separate columns, if the format is [TFileFormats.Text](../TFileFormats.md)|
|const|**firstRow**|Integer|First row where we will copy the cells on the new sheet, for [TFileFormats.Text](../TFileFormats.md)|
|const|**firstCol**|Integer|First column where we will copy the cells on the new sheet, for [TFileFormats.Text](../TFileFormats.md)|
|const|**columnFormats**|[TArray\<&#8203;TColumn&#8203;Import&#8203;Type>](../TColumnImportType.md)|An array of [TColumnImportType](../TColumnImportType.md) elements, telling how each column should be imported\.<br />See the example for more information on how to use it\.<br />|


## Examples

Imagine you have a file with 20 columns, and column 2 has numbers you want to be imported as text \(like phone numbers\), and you don't want to import column 10\.

You can use the following code to do it:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ColTypes: TArray&#x3C;TColumnImportType>;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls: TExcelFile;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  SetLength(ColTypes, </span><span style="color:#098658;--shiki-dark:#B5CEA8">10</span><span style="color:#000000;--shiki-dark:#D4D4D4">);  </span><span style="color:#008000;--shiki-dark:#6A9955">//You just need to define 10 items, all other columns after 10 will be imported with default formatting.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ColTypes[</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">] := TColumnImportType.Text;  </span><span style="color:#008000;--shiki-dark:#6A9955">//Import whatever is in column 2 as text.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ColTypes[</span><span style="color:#098658;--shiki-dark:#B5CEA8">9</span><span style="color:#000000;--shiki-dark:#D4D4D4">] := TColumnImportType.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Skip</span><span style="color:#000000;--shiki-dark:#D4D4D4">;  </span><span style="color:#008000;--shiki-dark:#6A9955">//don't import column 10.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls := TXlsFile.Create(</span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);  </span><span style="color:#008000;--shiki-dark:#6A9955">//Create a new file.</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.Open(</span><span style="color:#A31515;--shiki-dark:#CE9178">'csv.csv'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TFileFormats.Text, </span><span style="color:#A31515;--shiki-dark:#CE9178">','</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, ColTypes);  </span><span style="color:#008000;--shiki-dark:#6A9955">//Import the csv text.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Process(xls);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>



## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.Open\(TStream, TFileFormats, Char, Integer, Integer, TColumnImportTypeArray, Boolean\)
Loads a new Spreadsheet from a stream, on one of the specified formats\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.Open(const aStream: TStream; const fileFormat: <a href="../TFileFormats.md">TFileFormats</a>; const delimiter: Char; const firstRow: Integer; const firstCol: Integer; const columnFormats: <a href="../TColumnImportType.md">TArray&lt;TColumnImportType></a>; const detectEncodingFromByteOrderMarks: Boolean); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aStream**|TStream|Stream to open, must be a seekable stream\. Verify it is on the correct position\.|
|const|**fileFormat**|[TFileFormats](../TFileFormats.md)|List with possible file formats to try\.|
|const|**delimiter**|Char|Delimiter used to separate columns, if the format is [TFileFormats.Text](../TFileFormats.md)|
|const|**firstRow**|Integer|First row where we will copy the cells on the new sheet, for [TFileFormats.Text](../TFileFormats.md)|
|const|**firstCol**|Integer|First column where we will copy the cells on the new sheet, for [TFileFormats.Text](../TFileFormats.md)|
|const|**columnFormats**|[TArray\<&#8203;TColumn&#8203;Import&#8203;Type>](../TColumnImportType.md)|An array of [TColumnImportType](../TColumnImportType.md) elements, telling how each column should be imported\.<br />See the example for more information on how to use it\.<br />|
|const|**detectEncodingFromByteOrderMarks**|Boolean|This parameter only applies when reading Text files\. It is the same on the constructor of a StreamReader, and it says if BOM must be used at the beginning of the file\. It defaults to true\.|


## Examples

Imagine you have a file with 20 columns, and column 2 has numbers you want to be imported as text \(like phone numbers\), and you don't want to import column 10\.

You can use the following code to do it:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ColTypes: TArray&#x3C;TColumnImportType>;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls: TExcelFile;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  SetLength(ColTypes, </span><span style="color:#098658;--shiki-dark:#B5CEA8">10</span><span style="color:#000000;--shiki-dark:#D4D4D4">);  </span><span style="color:#008000;--shiki-dark:#6A9955">//You just need to define 10 items, all other columns after 10 will be imported with default formatting.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ColTypes[</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">] := TColumnImportType.Text;  </span><span style="color:#008000;--shiki-dark:#6A9955">//Import whatever is in column 2 as text.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ColTypes[</span><span style="color:#098658;--shiki-dark:#B5CEA8">9</span><span style="color:#000000;--shiki-dark:#D4D4D4">] := TColumnImportType.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Skip</span><span style="color:#000000;--shiki-dark:#D4D4D4">;  </span><span style="color:#008000;--shiki-dark:#6A9955">//don't import column 10.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls := TXlsFile.Create(</span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);  </span><span style="color:#008000;--shiki-dark:#6A9955">//Create a new file.</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.Open(</span><span style="color:#A31515;--shiki-dark:#CE9178">'csv.csv'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TFileFormats.Text, </span><span style="color:#A31515;--shiki-dark:#CE9178">','</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, ColTypes);  </span><span style="color:#008000;--shiki-dark:#6A9955">//Import the csv text.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Process(xls);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>



## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.Open\(string, TFileFormats, Char, Integer, Integer, TColumnImportTypeArray, TEncoding, Boolean\)
Loads a new Spreadsheet from disk, on one of the specified formats\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.Open(const fileName: string; const fileFormat: <a href="../TFileFormats.md">TFileFormats</a>; const delimiter: Char; const firstRow: Integer; const firstCol: Integer; const columnFormats: <a href="../TColumnImportType.md">TArray&lt;TColumnImportType></a>; const fileEncoding: TEncoding; const detectEncodingFromByteOrderMarks: Boolean); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**fileName**|string|File to open|
|const|**fileFormat**|[TFileFormats](../TFileFormats.md)|List with possible file formats to try|
|const|**delimiter**|Char|Delimiter used to separate columns, if the format is [TFileFormats.Text](../TFileFormats.md)|
|const|**firstRow**|Integer|First row where we will copy the cells on the new sheet, for [TFileFormats.Text](../TFileFormats.md)|
|const|**firstCol**|Integer|First column where we will copy the cells on the new sheet, for [TFileFormats.Text](../TFileFormats.md)|
|const|**columnFormats**|[TArray\<&#8203;TColumn&#8203;Import&#8203;Type>](../TColumnImportType.md)|An array of [TColumnImportType](../TColumnImportType.md) elements, telling how each column should be imported\.|
|const|**fileEncoding**|TEncoding|Encoding used by the file we are reading, when opening a Text\-delimited file \(csv or txt\)\.<br />If you specify an encoding for xls95 files, it will overwrite the default encoding specified in the file, and this can be used to read  buggy or corrupted xls95 files\. But in general for xls95 you should keep this parameter null\.<br /><br />This parameter has no effect on xls 97 files or xlsx\. If null when reading text files, it is assumed to be Encoding\.UTF8\.|
|const|**detectEncodingFromByteOrderMarks**|Boolean|This parameter only applies when reading Text files\. It is the same on the constructor of a StreamReader, and it says if BOM must be used at the beginning of the file\. It defaults to true\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.Open\(TStream, TFileFormats, Char, Integer, Integer, TColumnImportTypeArray, TEncoding, Boolean\)
Loads a new Spreadsheet from a stream, on one of the specified formats\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.Open(const aStream: TStream; const fileFormat: <a href="../TFileFormats.md">TFileFormats</a>; const delimiter: Char; const firstRow: Integer; const firstCol: Integer; const columnFormats: <a href="../TColumnImportType.md">TArray&lt;TColumnImportType></a>; const fileEncoding: TEncoding; const detectEncodingFromByteOrderMarks: Boolean); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aStream**|TStream|Stream to open, must be a seekable stream\. Verify it is on the correct position\.|
|const|**fileFormat**|[TFileFormats](../TFileFormats.md)|List with possible file formats to try\.|
|const|**delimiter**|Char|Delimiter used to separate columns, if the format is [TFileFormats.Text](../TFileFormats.md)|
|const|**firstRow**|Integer|First row where we will copy the cells on the new sheet, for [TFileFormats.Text](../TFileFormats.md)|
|const|**firstCol**|Integer|First column where we will copy the cells on the new sheet, for [TFileFormats.Text](../TFileFormats.md)|
|const|**columnFormats**|[TArray\<&#8203;TColumn&#8203;Import&#8203;Type>](../TColumnImportType.md)|An array of [TColumnImportType](../TColumnImportType.md) elements, telling how each column should be imported\.<br />See the example for more information on how to use it\.<br />|
|const|**fileEncoding**|TEncoding|Encoding used by the file we are reading, when opening a Text\-delimited file \(csv or txt\)\.<br />If you specify an encoding for xls95 files, it will overwrite the default encoding specified in the file, and this can be used to read  buggy or corrupted xls95 files\. But in general for xls95 you should keep this parameter null\.<br /><br />This parameter has no effect on xls 97 files or xlsx\. If null when reading text files, it is assumed to be Encoding\.UTF8\.|
|const|**detectEncodingFromByteOrderMarks**|Boolean|This parameter only applies when reading Text files\. It is the same on the constructor of a StreamReader, and it says if BOM must be used at the beginning of the file\. It defaults to true\.|


## Examples

Imagine you have a file with 20 columns, and column 2 has numbers you want to be imported as text \(like phone numbers\), and you don't want to import column 10\.

You can use the following code to do it:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ColTypes: TArray&#x3C;TColumnImportType>;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls: TExcelFile;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  SetLength(ColTypes, </span><span style="color:#098658;--shiki-dark:#B5CEA8">10</span><span style="color:#000000;--shiki-dark:#D4D4D4">);  </span><span style="color:#008000;--shiki-dark:#6A9955">//You just need to define 10 items, all other columns after 10 will be imported with default formatting.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ColTypes[</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">] := TColumnImportType.Text;  </span><span style="color:#008000;--shiki-dark:#6A9955">//Import whatever is in column 2 as text.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ColTypes[</span><span style="color:#098658;--shiki-dark:#B5CEA8">9</span><span style="color:#000000;--shiki-dark:#D4D4D4">] := TColumnImportType.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Skip</span><span style="color:#000000;--shiki-dark:#D4D4D4">;  </span><span style="color:#008000;--shiki-dark:#6A9955">//don't import column 10.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls := TXlsFile.Create(</span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);  </span><span style="color:#008000;--shiki-dark:#6A9955">//Create a new file.</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.Open(</span><span style="color:#A31515;--shiki-dark:#CE9178">'csv.csv'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TFileFormats.Text, </span><span style="color:#A31515;--shiki-dark:#CE9178">','</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, ColTypes);  </span><span style="color:#008000;--shiki-dark:#6A9955">//Import the csv text.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Process(xls);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>



## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.Open\(string, TFileFormats, Char, Integer, Integer, TColumnImportTypeArray, TArray\<string>, TEncoding, Boolean\)
Loads a new Spreadsheet from disk, on one of the specified formats\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.Open(const fileName: string; const fileFormat: <a href="../TFileFormats.md">TFileFormats</a>; const delimiter: Char; const firstRow: Integer; const firstCol: Integer; const columnFormats: <a href="../TColumnImportType.md">TArray&lt;TColumnImportType></a>; const dateFormats: TArray&lt;string&gt;; const fileEncoding: TEncoding; const detectEncodingFromByteOrderMarks: Boolean); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**fileName**|string|File to open|
|const|**fileFormat**|[TFileFormats](../TFileFormats.md)|List with possible file formats to try|
|const|**delimiter**|Char|Delimiter used to separate columns, if the format is [TFileFormats.Text](../TFileFormats.md)|
|const|**firstRow**|Integer|First row where we will copy the cells on the new sheet, for [TFileFormats.Text](../TFileFormats.md)|
|const|**firstCol**|Integer|First column where we will copy the cells on the new sheet, for [TFileFormats.Text](../TFileFormats.md)|
|const|**columnFormats**|[TArray\<&#8203;TColumn&#8203;Import&#8203;Type>](../TColumnImportType.md)|An array of [TColumnImportType](../TColumnImportType.md) elements, telling how each column should be imported\.|
|const|**dateFormats**|TArray\<string>|**Note:**This format must be expressed with \.NET notation, as specified here: [http://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx](http://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx) \.A list of formats allowed for dates and times, when opening text files\. Windows is a little liberal in what it thinks can be a date, and it can convert things like "1\.2" into dates\. By setting this property, you can ensure the dates are only in the formats you expect\. If you leave it null, we will trust "DateTime\.TryParse" to guess the correct values\. This value has no meaning in normal xls files, only text files\.|
|const|**fileEncoding**|TEncoding|Encoding used by the file we are reading, when opening a Text\-delimited file \(csv or txt\)\.<br />If you specify an encoding for xls95 files, it will overwrite the default encoding specified in the file, and this can be used to read  buggy or corrupted xls95 files\. But in general for xls95 you should keep this parameter null\.<br /><br />This parameter has no effect on xls 97 files or xlsx\. If null when reading text files, it is assumed to be Encoding\.UTF8\.|
|const|**detectEncodingFromByteOrderMarks**|Boolean|This parameter only applies when reading Text files\. It is the same on the constructor of a StreamReader, and it says if BOM must be used at the beginning of the file\. It defaults to true\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.Open\(TStream, TFileFormats, Char, Integer, Integer, TColumnImportTypeArray, TArray\<string>, TEncoding, Boolean\)
Loads a new Spreadsheet from a stream, on one of the specified formats\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.Open(const aStream: TStream; const fileFormat: <a href="../TFileFormats.md">TFileFormats</a>; const delimiter: Char; const firstRow: Integer; const firstCol: Integer; const columnFormats: <a href="../TColumnImportType.md">TArray&lt;TColumnImportType></a>; const dateFormats: TArray&lt;string&gt;; const fileEncoding: TEncoding; const detectEncodingFromByteOrderMarks: Boolean); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aStream**|TStream|Stream to open, must be a seekable stream\. Verify it is on the correct position\.|
|const|**fileFormat**|[TFileFormats](../TFileFormats.md)|List with possible file formats to try\.|
|const|**delimiter**|Char|Delimiter used to separate columns, if the format is [TFileFormats.Text](../TFileFormats.md)|
|const|**firstRow**|Integer|First row where we will copy the cells on the new sheet, for [TFileFormats.Text](../TFileFormats.md)|
|const|**firstCol**|Integer|First column where we will copy the cells on the new sheet, for [TFileFormats.Text](../TFileFormats.md)|
|const|**columnFormats**|[TArray\<&#8203;TColumn&#8203;Import&#8203;Type>](../TColumnImportType.md)|An array of [TColumnImportType](../TColumnImportType.md) elements, telling how each column should be imported\.<br />See the example for more information on how to use it\.<br />|
|const|**dateFormats**|TArray\<string>|**Note:**This format must be expressed with \.NET notation, as specified here: [http://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx](http://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx) \.A list of formats allowed for dates and times, when opening text files\. Windows is a little liberal in what it thinks can be a date, and it can convert things like "1\.2" into dates\. By setting this property, you can ensure the dates are only in the formats you expect\. If you leave it null, we will trust "DateTime\.TryParse" to guess the correct values\. This value has no meaning in normal xls files, only text files\.|
|const|**fileEncoding**|TEncoding|Encoding used by the file we are reading, when opening a Text\-delimited file \(csv or txt\)\.<br />If you specify an encoding for xls95 files, it will overwrite the default encoding specified in the file, and this can be used to read  buggy or corrupted xls95 files\. But in general for xls95 you should keep this parameter null\.<br /><br />This parameter has no effect on xls 97 files or xlsx\. If null when reading text files, it is assumed to be Encoding\.UTF8\.|
|const|**detectEncodingFromByteOrderMarks**|Boolean|This parameter only applies when reading Text files\. It is the same on the constructor of a StreamReader, and it says if BOM must be used at the beginning of the file\. It defaults to true\.|


## Examples

Imagine you have a file with 20 columns, and column 2 has numbers you want to be imported as text \(like phone numbers\), and you don't want to import column 10\.

You can use the following code to do it:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ColTypes: TArray&#x3C;TColumnImportType>;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls: TExcelFile;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  SetLength(ColTypes, </span><span style="color:#098658;--shiki-dark:#B5CEA8">10</span><span style="color:#000000;--shiki-dark:#D4D4D4">);  </span><span style="color:#008000;--shiki-dark:#6A9955">//You just need to define 10 items, all other columns after 10 will be imported with default formatting.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ColTypes[</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">] := TColumnImportType.Text;  </span><span style="color:#008000;--shiki-dark:#6A9955">//Import whatever is in column 2 as text.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ColTypes[</span><span style="color:#098658;--shiki-dark:#B5CEA8">9</span><span style="color:#000000;--shiki-dark:#D4D4D4">] := TColumnImportType.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Skip</span><span style="color:#000000;--shiki-dark:#D4D4D4">;  </span><span style="color:#008000;--shiki-dark:#6A9955">//don't import column 10.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls := TXlsFile.Create(</span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);  </span><span style="color:#008000;--shiki-dark:#6A9955">//Create a new file.</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.Open(</span><span style="color:#A31515;--shiki-dark:#CE9178">'csv.csv'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TFileFormats.Text, </span><span style="color:#A31515;--shiki-dark:#CE9178">','</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, ColTypes);  </span><span style="color:#008000;--shiki-dark:#6A9955">//Import the csv text.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Process(xls);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>



## See also

* [TExcelFile](../TExcelFile/index.md)

