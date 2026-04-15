---
uid: TExcelFile.Import
description: TExcelFile.Import
---

# TExcelFile\.Import Method

## Overloads

* [TExcelFile\.Import\(TTextReader, Integer, Integer, Int32Array, TColumnImportTypeArray\)](#texcelfileimportttextreader-integer-integer-int32array-tcolumnimporttypearray)
* [TExcelFile\.Import\(TTextReader, Integer, Integer, Int32Array, TColumnImportTypeArray, TArray\<string>\)](#texcelfileimportttextreader-integer-integer-int32array-tcolumnimporttypearray-tarraystring)
* [TExcelFile\.Import\(string, Integer, Integer, Char, TColumnImportTypeArray, TEncoding, Boolean\)](#texcelfileimportstring-integer-integer-char-tcolumnimporttypearray-tencoding-boolean)
* [TExcelFile\.Import\(TStream, Integer, Integer, Char, TColumnImportTypeArray, TEncoding, Boolean\)](#texcelfileimporttstream-integer-integer-char-tcolumnimporttypearray-tencoding-boolean)
* [TExcelFile\.Import\(TTextReader, Integer, Integer, Char, Char, TColumnImportTypeArray, TArray\<string>\)](#texcelfileimportttextreader-integer-integer-char-char-tcolumnimporttypearray-tarraystring)
* [TExcelFile\.Import\(string, Integer, Integer, Int32Array, TColumnImportTypeArray, TEncoding, Boolean\)](#texcelfileimportstring-integer-integer-int32array-tcolumnimporttypearray-tencoding-boolean)
* [TExcelFile\.Import\(TStream, Integer, Integer, Int32Array, TColumnImportTypeArray, TEncoding, Boolean\)](#texcelfileimporttstream-integer-integer-int32array-tcolumnimporttypearray-tencoding-boolean)
* [TExcelFile\.Import\(string, Integer, Integer, Char, TColumnImportTypeArray, TArray\<string>, TEncoding, Boolean\)](#texcelfileimportstring-integer-integer-char-tcolumnimporttypearray-tarraystring-tencoding-boolean)
* [TExcelFile\.Import\(TStream, Integer, Integer, Char, TColumnImportTypeArray, TArray\<string>, TEncoding, Boolean\)](#texcelfileimporttstream-integer-integer-char-tcolumnimporttypearray-tarraystring-tencoding-boolean)
* [TExcelFile\.Import\(string, Integer, Integer, Int32Array, TColumnImportTypeArray, TArray\<string>, TEncoding, Boolean\)](#texcelfileimportstring-integer-integer-int32array-tcolumnimporttypearray-tarraystring-tencoding-boolean)
* [TExcelFile\.Import\(TStream, Integer, Integer, Int32Array, TColumnImportTypeArray, TArray\<string>, TEncoding, Boolean\)](#texcelfileimporttstream-integer-integer-int32array-tcolumnimporttypearray-tarraystring-tencoding-boolean)
* [TExcelFile\.Import\(string, Integer, Integer, Char, Char, TColumnImportTypeArray, TArray\<string>, TEncoding, Boolean\)](#texcelfileimportstring-integer-integer-char-char-tcolumnimporttypearray-tarraystring-tencoding-boolean)
* [TExcelFile\.Import\(TStream, Integer, Integer, Char, Char, TColumnImportTypeArray, TArray\<string>, TEncoding, Boolean\)](#texcelfileimporttstream-integer-integer-char-char-tcolumnimporttypearray-tarraystring-tencoding-boolean)

# TExcelFile\.Import\(TTextReader, Integer, Integer, Int32Array, TColumnImportTypeArray\)
Imports a text file \(fixed length columns\) into the current sheet\. Note that this method won't clear any existing data\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.Import(const aTextReader: TTextReader; const firstRow: Integer; const firstCol: Integer; const columnWidths: TArray&lt;Int32>; const columnFormats: <a href="../TColumnImportType.md">TArray&lt;TColumnImportType></a>); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aTextReader**|TTextReader|StreamReader with the text to import\.|
|const|**firstRow**|Integer|Row in the Active sheet where we will start importing the text file\.|
|const|**firstCol**|Integer|Column in the Active sheet where we will start importing the text file\.|
|const|**columnWidths**|TArray\<Int32>|An array with the column widths for every column you want to import\.|
|const|**columnFormats**|[TArray\<&#8203;TColumn&#8203;Import&#8203;Type>](../TColumnImportType.md)|An array of [TColumnImportType](../TColumnImportType.md) elements, telling how each column should be imported\.<br />See the example in [Open\(TStream, TFileFormats, Char, Integer, Integer, TColumnImportTypeArray\)](Open.md#texcelfileopentstream-tfileformats-char-integer-integer-tcolumnimporttypearray) for more information on how to use it\.<br />|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.Import\(TTextReader, Integer, Integer, Int32Array, TColumnImportTypeArray, TArray\<string>\)
Imports a text file \(fixed length columns\) into the current sheet\. Note that this method won't clear any existing data\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.Import(const aTextReader: TTextReader; const firstRow: Integer; const firstCol: Integer; const columnWidths: TArray&lt;Int32>; const columnFormats: <a href="../TColumnImportType.md">TArray&lt;TColumnImportType></a>; const dateFormats: TArray&lt;string&gt;); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aTextReader**|TTextReader|StreamReader with the text to import\.|
|const|**firstRow**|Integer|Row in the Active sheet where we will start importing the text file\.|
|const|**firstCol**|Integer|Column in the Active sheet where we will start importing the text file\.|
|const|**columnWidths**|TArray\<Int32>|An array with the column widths for every column you want to import\.|
|const|**columnFormats**|[TArray\<&#8203;TColumn&#8203;Import&#8203;Type>](../TColumnImportType.md)|An array of [TColumnImportType](../TColumnImportType.md) elements, telling how each column should be imported\.<br />See the example in [Open\(TStream, TFileFormats, Char, Integer, Integer, TColumnImportTypeArray\)](Open.md#texcelfileopentstream-tfileformats-char-integer-integer-tcolumnimporttypearray) for more information on how to use it\.<br />|
|const|**dateFormats**|TArray\<string>|**Note:**This format must be expressed with \.NET notation, as specified here: [http://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx](http://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx) \.A list of formats allowed for dates and times, when opening text files\. Windows is a little liberal in what it thinks can be a date, and it can convert things like "1\.2" into dates\. By setting this property, you can ensure the dates are only in the formats you expect\. If you leave it null, we will trust "DateTime\.TryParse" to guess the correct values\. This value has no meaning in normal xls files, only text files\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.Import\(string, Integer, Integer, Char, TColumnImportTypeArray, TEncoding, Boolean\)
Imports a text file \(character\-delimited columns\) into the current sheet\. Note that this method won't clear any existing data\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.Import(const fileName: string; const firstRow: Integer; const firstCol: Integer; const delimiter: Char; const columnFormats: <a href="../TColumnImportType.md">TArray&lt;TColumnImportType></a>; const fileEncoding: TEncoding; const detectEncodingFromByteOrderMarks: Boolean); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**fileName**|string|File with the text to import\.|
|const|**firstRow**|Integer|Row in the Active sheet where we will start importing the text file\.|
|const|**firstCol**|Integer|Column in the Active sheet where we will start importing the text file\.|
|const|**delimiter**|Char|Character used to separate columns\.|
|const|**columnFormats**|[TArray\<&#8203;TColumn&#8203;Import&#8203;Type>](../TColumnImportType.md)|An array of [TColumnImportType](../TColumnImportType.md) elements, telling how each column should be imported\.<br />See the example in [Open\(TStream, TFileFormats, Char, Integer, Integer, TColumnImportTypeArray\)](Open.md#texcelfileopentstream-tfileformats-char-integer-integer-tcolumnimporttypearray) for more information on how to use it\.<br />|
|const|**fileEncoding**|TEncoding|Encoding used by the file we are reading\. If omitted or null, it is assumed to be Encoding\.UTF8\.|
|const|**detectEncodingFromByteOrderMarks**|Boolean|It is the same on the constructor of a StreamReader, and it says if BOM must be used at the beginning of the file\. It defaults to true\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.Import\(TStream, Integer, Integer, Char, TColumnImportTypeArray, TEncoding, Boolean\)
Imports a text file \(character\-delimited columns\) into the current sheet\. Note that this method won't clear any existing data\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.Import(const aStream: TStream; const firstRow: Integer; const firstCol: Integer; const delimiter: Char; const columnFormats: <a href="../TColumnImportType.md">TArray&lt;TColumnImportType></a>; const fileEncoding: TEncoding; const detectEncodingFromByteOrderMarks: Boolean); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aStream**|TStream|Stream with the text to import\.|
|const|**firstRow**|Integer|Row in the Active sheet where we will start importing the text file\.|
|const|**firstCol**|Integer|Column in the Active sheet where we will start importing the text file\.|
|const|**delimiter**|Char|Character used to separate columns\.|
|const|**columnFormats**|[TArray\<&#8203;TColumn&#8203;Import&#8203;Type>](../TColumnImportType.md)|An array of [TColumnImportType](../TColumnImportType.md) elements, telling how each column should be imported\.<br />See the example in [Open\(TStream, TFileFormats, Char, Integer, Integer, TColumnImportTypeArray\)](Open.md#texcelfileopentstream-tfileformats-char-integer-integer-tcolumnimporttypearray) for more information on how to use it\.<br />|
|const|**fileEncoding**|TEncoding|Encoding used by the file we are reading\. If omitted or null, it is assumed to be Encoding\.UTF8\.|
|const|**detectEncodingFromByteOrderMarks**|Boolean|It is the same on the constructor of a StreamReader, and it says if BOM must be used at the beginning of the file\. It defaults to true\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.Import\(TTextReader, Integer, Integer, Char, Char, TColumnImportTypeArray, TArray\<string>\)
Imports a text file \(character\-delimited columns\) into the current sheet\. Note that this method won't clear any existing data\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.Import(const aTextReader: TTextReader; const firstRow: Integer; const firstCol: Integer; const delimiter: Char; const textQualifier: Char; const columnFormats: <a href="../TColumnImportType.md">TArray&lt;TColumnImportType></a>; const dateFormats: TArray&lt;string&gt;); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aTextReader**|TTextReader|TextReader with the text to import\.|
|const|**firstRow**|Integer|Row in the Active sheet where we will start importing the text file\.|
|const|**firstCol**|Integer|Column in the Active sheet where we will start importing the text file\.|
|const|**delimiter**|Char|Character used to separate columns\.|
|const|**textQualifier**|Char|Character used to quote strings when they contain the delimiter\. This is normally the double quote \("\) but you might change it by a single quote or any other character\. Use a char 0 if the original file isn't quoted\.|
|const|**columnFormats**|[TArray\<&#8203;TColumn&#8203;Import&#8203;Type>](../TColumnImportType.md)|An array of [TColumnImportType](../TColumnImportType.md) elements, telling how each column should be imported\.<br />See the example in [Open\(TStream, TFileFormats, Char, Integer, Integer, TColumnImportTypeArray\)](Open.md#texcelfileopentstream-tfileformats-char-integer-integer-tcolumnimporttypearray) for more information on how to use it\.<br />|
|const|**dateFormats**|TArray\<string>|**Note:**This format must be expressed with \.NET notation, as specified here: [http://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx](http://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx) \.A list of formats allowed for dates and times, when opening text files\. Windows is a little liberal in what it thinks can be a date, and it can convert things like "1\.2" into dates\. By setting this property, you can ensure the dates are only in the formats you expect\. If you leave it null, we will trust "DateTime\.TryParse" to guess the correct values\. This value has no meaning in normal xls files, only text files\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.Import\(string, Integer, Integer, Int32Array, TColumnImportTypeArray, TEncoding, Boolean\)
Imports a text file \(fixed length columns\) into the current sheet\. Note that this method won't clear any existing data\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.Import(const fileName: string; const firstRow: Integer; const firstCol: Integer; const columnWidths: TArray&lt;Int32>; const columnFormats: <a href="../TColumnImportType.md">TArray&lt;TColumnImportType></a>; const fileEncoding: TEncoding; const detectEncodingFromByteOrderMarks: Boolean); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**fileName**|string|File with the text to import\.|
|const|**firstRow**|Integer|Row in the Active sheet where we will start importing the text file\.|
|const|**firstCol**|Integer|Column in the Active sheet where we will start importing the text file\.|
|const|**columnWidths**|TArray\<Int32>|An array with the column widths for every column you want to import\.|
|const|**columnFormats**|[TArray\<&#8203;TColumn&#8203;Import&#8203;Type>](../TColumnImportType.md)|An array of [TColumnImportType](../TColumnImportType.md) elements, telling how each column should be imported\.<br />See the example in [Open\(TStream, TFileFormats, Char, Integer, Integer, TColumnImportTypeArray\)](Open.md#texcelfileopentstream-tfileformats-char-integer-integer-tcolumnimporttypearray) for more information on how to use it\.<br />|
|const|**fileEncoding**|TEncoding|Encoding used by the file we are reading\. If omitted or null, it is assumed to be Encoding\.UTF8\.|
|const|**detectEncodingFromByteOrderMarks**|Boolean|It is the same on the constructor of a StreamReader, and it says if BOM must be used at the beginning of the file\. It defaults to true\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.Import\(TStream, Integer, Integer, Int32Array, TColumnImportTypeArray, TEncoding, Boolean\)
Imports a text file \(fixed length columns\) into the current sheet\. Note that this method won't clear any existing data\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.Import(const aStream: TStream; const firstRow: Integer; const firstCol: Integer; const columnWidths: TArray&lt;Int32>; const columnFormats: <a href="../TColumnImportType.md">TArray&lt;TColumnImportType></a>; const fileEncoding: TEncoding; const detectEncodingFromByteOrderMarks: Boolean); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aStream**|TStream|Stream with the text to import\.|
|const|**firstRow**|Integer|Row in the Active sheet where we will start importing the text file\.|
|const|**firstCol**|Integer|Column in the Active sheet where we will start importing the text file\.|
|const|**columnWidths**|TArray\<Int32>|An array with the column widths for every column you want to import\.|
|const|**columnFormats**|[TArray\<&#8203;TColumn&#8203;Import&#8203;Type>](../TColumnImportType.md)|An array of [TColumnImportType](../TColumnImportType.md) elements, telling how each column should be imported\.<br />See the example in [Open\(TStream, TFileFormats, Char, Integer, Integer, TColumnImportTypeArray\)](Open.md#texcelfileopentstream-tfileformats-char-integer-integer-tcolumnimporttypearray) for more information on how to use it\.<br />|
|const|**fileEncoding**|TEncoding|Encoding used by the file we are reading\. If omitted or null, it is assumed to be Encoding\.UTF8\.|
|const|**detectEncodingFromByteOrderMarks**|Boolean|It is the same on the constructor of a StreamReader, and it says if BOM must be used at the beginning of the file\. It defaults to true\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.Import\(string, Integer, Integer, Char, TColumnImportTypeArray, TArray\<string>, TEncoding, Boolean\)
Imports a text file \(character\-delimited columns\) into the current sheet\. Note that this method won't clear any existing data\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.Import(const fileName: string; const firstRow: Integer; const firstCol: Integer; const delimiter: Char; const columnFormats: <a href="../TColumnImportType.md">TArray&lt;TColumnImportType></a>; const dateFormats: TArray&lt;string&gt;; const fileEncoding: TEncoding; const detectEncodingFromByteOrderMarks: Boolean); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**fileName**|string|File with the text to import\.|
|const|**firstRow**|Integer|Row in the Active sheet where we will start importing the text file\.|
|const|**firstCol**|Integer|Column in the Active sheet where we will start importing the text file\.|
|const|**delimiter**|Char|Character used to separate columns\.|
|const|**columnFormats**|[TArray\<&#8203;TColumn&#8203;Import&#8203;Type>](../TColumnImportType.md)|An array of [TColumnImportType](../TColumnImportType.md) elements, telling how each column should be imported\.<br />See the example in [Open\(TStream, TFileFormats, Char, Integer, Integer, TColumnImportTypeArray\)](Open.md#texcelfileopentstream-tfileformats-char-integer-integer-tcolumnimporttypearray) for more information on how to use it\.<br />|
|const|**dateFormats**|TArray\<string>|**Note:**This format must be expressed with \.NET notation, as specified here: [http://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx](http://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx) \.A list of formats allowed for dates and times, when opening text files\. Windows is a little liberal in what it thinks can be a date, and it can convert things like "1\.2" into dates\. By setting this property, you can ensure the dates are only in the formats you expect\. If you leave it null, we will trust "DateTime\.TryParse" to guess the correct values\. This value has no meaning in normal xls files, only text files\.|
|const|**fileEncoding**|TEncoding|Encoding used by the file we are reading\. If omitted or null, it is assumed to be Encoding\.UTF8\.|
|const|**detectEncodingFromByteOrderMarks**|Boolean|It is the same on the constructor of a StreamReader, and it says if BOM must be used at the beginning of the file\. It defaults to true\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.Import\(TStream, Integer, Integer, Char, TColumnImportTypeArray, TArray\<string>, TEncoding, Boolean\)
Imports a text file \(character\-delimited columns\) into the current sheet\. Note that this method won't clear any existing data\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.Import(const aStream: TStream; const firstRow: Integer; const firstCol: Integer; const delimiter: Char; const columnFormats: <a href="../TColumnImportType.md">TArray&lt;TColumnImportType></a>; const dateFormats: TArray&lt;string&gt;; const fileEncoding: TEncoding; const detectEncodingFromByteOrderMarks: Boolean); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aStream**|TStream|Stream with the text to import\.|
|const|**firstRow**|Integer|Row in the Active sheet where we will start importing the text file\.|
|const|**firstCol**|Integer|Column in the Active sheet where we will start importing the text file\.|
|const|**delimiter**|Char|Character used to separate columns\.|
|const|**columnFormats**|[TArray\<&#8203;TColumn&#8203;Import&#8203;Type>](../TColumnImportType.md)|An array of [TColumnImportType](../TColumnImportType.md) elements, telling how each column should be imported\.<br />See the example in [Open\(TStream, TFileFormats, Char, Integer, Integer, TColumnImportTypeArray\)](Open.md#texcelfileopentstream-tfileformats-char-integer-integer-tcolumnimporttypearray) for more information on how to use it\.<br />|
|const|**dateFormats**|TArray\<string>|**Note:**This format must be expressed with \.NET notation, as specified here: [http://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx](http://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx) \.A list of formats allowed for dates and times, when opening text files\. Windows is a little liberal in what it thinks can be a date, and it can convert things like "1\.2" into dates\. By setting this property, you can ensure the dates are only in the formats you expect\. If you leave it null, we will trust "DateTime\.TryParse" to guess the correct values\. This value has no meaning in normal xls files, only text files\.|
|const|**fileEncoding**|TEncoding|Encoding used by the file we are reading\. If omitted or null, it is assumed to be Encoding\.UTF8\.|
|const|**detectEncodingFromByteOrderMarks**|Boolean|It is the same on the constructor of a StreamReader, and it says if BOM must be used at the beginning of the file\. It defaults to true\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.Import\(string, Integer, Integer, Int32Array, TColumnImportTypeArray, TArray\<string>, TEncoding, Boolean\)
Imports a text file \(fixed length columns\) into the current sheet\. Note that this method won't clear any existing data\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.Import(const fileName: string; const firstRow: Integer; const firstCol: Integer; const columnWidths: TArray&lt;Int32>; const columnFormats: <a href="../TColumnImportType.md">TArray&lt;TColumnImportType></a>; const dateFormats: TArray&lt;string&gt;; const fileEncoding: TEncoding; const detectEncodingFromByteOrderMarks: Boolean); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**fileName**|string|File with the text to import\.|
|const|**firstRow**|Integer|Row in the Active sheet where we will start importing the text file\.|
|const|**firstCol**|Integer|Column in the Active sheet where we will start importing the text file\.|
|const|**columnWidths**|TArray\<Int32>|An array with the column widths for every column you want to import\.|
|const|**columnFormats**|[TArray\<&#8203;TColumn&#8203;Import&#8203;Type>](../TColumnImportType.md)|An array of [TColumnImportType](../TColumnImportType.md) elements, telling how each column should be imported\.<br />See the example in [Open\(TStream, TFileFormats, Char, Integer, Integer, TColumnImportTypeArray\)](Open.md#texcelfileopentstream-tfileformats-char-integer-integer-tcolumnimporttypearray) for more information on how to use it\.<br />|
|const|**dateFormats**|TArray\<string>|**Note:**This format must be expressed with \.NET notation, as specified here: [http://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx](http://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx) \.A list of formats allowed for dates and times, when opening text files\. Windows is a little liberal in what it thinks can be a date, and it can convert things like "1\.2" into dates\. By setting this property, you can ensure the dates are only in the formats you expect\. If you leave it null, we will trust "DateTime\.TryParse" to guess the correct values\. This value has no meaning in normal xls files, only text files\.|
|const|**fileEncoding**|TEncoding|Encoding used by the file we are reading\. If omitted or null, it is assumed to be Encoding\.UTF8\.|
|const|**detectEncodingFromByteOrderMarks**|Boolean|It is the same on the constructor of a StreamReader, and it says if BOM must be used at the beginning of the file\. It defaults to true\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.Import\(TStream, Integer, Integer, Int32Array, TColumnImportTypeArray, TArray\<string>, TEncoding, Boolean\)
Imports a text file \(fixed length columns\) into the current sheet\. Note that this method won't clear any existing data\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.Import(const aStream: TStream; const firstRow: Integer; const firstCol: Integer; const columnWidths: TArray&lt;Int32>; const columnFormats: <a href="../TColumnImportType.md">TArray&lt;TColumnImportType></a>; const dateFormats: TArray&lt;string&gt;; const fileEncoding: TEncoding; const detectEncodingFromByteOrderMarks: Boolean); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aStream**|TStream|Stream with the text to import\.|
|const|**firstRow**|Integer|Row in the Active sheet where we will start importing the text file\.|
|const|**firstCol**|Integer|Column in the Active sheet where we will start importing the text file\.|
|const|**columnWidths**|TArray\<Int32>|An array with the column widths for every column you want to import\.|
|const|**columnFormats**|[TArray\<&#8203;TColumn&#8203;Import&#8203;Type>](../TColumnImportType.md)|An array of [TColumnImportType](../TColumnImportType.md) elements, telling how each column should be imported\.<br />See the example in [Open\(TStream, TFileFormats, Char, Integer, Integer, TColumnImportTypeArray\)](Open.md#texcelfileopentstream-tfileformats-char-integer-integer-tcolumnimporttypearray) for more information on how to use it\.<br />|
|const|**dateFormats**|TArray\<string>|**Note:**This format must be expressed with \.NET notation, as specified here: [http://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx](http://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx) \.A list of formats allowed for dates and times, when opening text files\. Windows is a little liberal in what it thinks can be a date, and it can convert things like "1\.2" into dates\. By setting this property, you can ensure the dates are only in the formats you expect\. If you leave it null, we will trust "DateTime\.TryParse" to guess the correct values\. This value has no meaning in normal xls files, only text files\.|
|const|**fileEncoding**|TEncoding|Encoding used by the file we are reading\. If omitted or null, it is assumed to be Encoding\.UTF8\.|
|const|**detectEncodingFromByteOrderMarks**|Boolean|It is the same on the constructor of a StreamReader, and it says if BOM must be used at the beginning of the file\. It defaults to true\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.Import\(string, Integer, Integer, Char, Char, TColumnImportTypeArray, TArray\<string>, TEncoding, Boolean\)
Imports a text file \(character\-delimited columns\) into the current sheet\. Note that this method won't clear any existing data\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.Import(const fileName: string; const firstRow: Integer; const firstCol: Integer; const delimiter: Char; const textQualifier: Char; const columnFormats: <a href="../TColumnImportType.md">TArray&lt;TColumnImportType></a>; const dateFormats: TArray&lt;string&gt;; const fileEncoding: TEncoding; const detectEncodingFromByteOrderMarks: Boolean); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**fileName**|string|File with the text to import\.|
|const|**firstRow**|Integer|Row in the Active sheet where we will start importing the text file\.|
|const|**firstCol**|Integer|Column in the Active sheet where we will start importing the text file\.|
|const|**delimiter**|Char|Character used to separate columns\.|
|const|**textQualifier**|Char|Character used to quote strings when they contain the delimiter\. This is normally the double quote \("\) but you might change it by a single quote or any other character\. Use a char 0 if the original file isn't quoted\.|
|const|**columnFormats**|[TArray\<&#8203;TColumn&#8203;Import&#8203;Type>](../TColumnImportType.md)|An array of [TColumnImportType](../TColumnImportType.md) elements, telling how each column should be imported\.<br />See the example in [Open\(TStream, TFileFormats, Char, Integer, Integer, TColumnImportTypeArray\)](Open.md#texcelfileopentstream-tfileformats-char-integer-integer-tcolumnimporttypearray) for more information on how to use it\.<br />|
|const|**dateFormats**|TArray\<string>|**Note:**This format must be expressed with \.NET notation, as specified here: [http://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx](http://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx) \.A list of formats allowed for dates and times, when opening text files\. Windows is a little liberal in what it thinks can be a date, and it can convert things like "1\.2" into dates\. By setting this property, you can ensure the dates are only in the formats you expect\. If you leave it null, we will trust "DateTime\.TryParse" to guess the correct values\. This value has no meaning in normal xls files, only text files\.|
|const|**fileEncoding**|TEncoding|Encoding used by the file we are reading\. If omitted or null, it is assumed to be Encoding\.UTF8\.|
|const|**detectEncodingFromByteOrderMarks**|Boolean|It is the same on the constructor of a StreamReader, and it says if BOM must be used at the beginning of the file\. It defaults to true\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.Import\(TStream, Integer, Integer, Char, Char, TColumnImportTypeArray, TArray\<string>, TEncoding, Boolean\)
Imports a text file \(character\-delimited columns\) into the current sheet\. Note that this method won't clear any existing data\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.Import(const aStream: TStream; const firstRow: Integer; const firstCol: Integer; const delimiter: Char; const textQualifier: Char; const columnFormats: <a href="../TColumnImportType.md">TArray&lt;TColumnImportType></a>; const dateFormats: TArray&lt;string&gt;; const fileEncoding: TEncoding; const detectEncodingFromByteOrderMarks: Boolean); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aStream**|TStream|Stream with the text to import\.|
|const|**firstRow**|Integer|Row in the Active sheet where we will start importing the text file\.|
|const|**firstCol**|Integer|Column in the Active sheet where we will start importing the text file\.|
|const|**delimiter**|Char|Character used to separate columns\.|
|const|**textQualifier**|Char|Character used to quote strings when they contain the delimiter\. This is normally the double quote \("\) but you might change it by a single quote or any other character\. Use a char 0 if the original file isn't quoted\.|
|const|**columnFormats**|[TArray\<&#8203;TColumn&#8203;Import&#8203;Type>](../TColumnImportType.md)|An array of [TColumnImportType](../TColumnImportType.md) elements, telling how each column should be imported\.<br />See the example in [Open\(TStream, TFileFormats, Char, Integer, Integer, TColumnImportTypeArray\)](Open.md#texcelfileopentstream-tfileformats-char-integer-integer-tcolumnimporttypearray) for more information on how to use it\.<br />|
|const|**dateFormats**|TArray\<string>|**Note:**This format must be expressed with \.NET notation, as specified here: [http://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx](http://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx) \.A list of formats allowed for dates and times, when opening text files\. Windows is a little liberal in what it thinks can be a date, and it can convert things like "1\.2" into dates\. By setting this property, you can ensure the dates are only in the formats you expect\. If you leave it null, we will trust "DateTime\.TryParse" to guess the correct values\. This value has no meaning in normal xls files, only text files\.|
|const|**fileEncoding**|TEncoding|Encoding used by the file we are reading\. If omitted or null, it is assumed to be Encoding\.UTF8\.|
|const|**detectEncodingFromByteOrderMarks**|Boolean|It is the same on the constructor of a StreamReader, and it says if BOM must be used at the beginning of the file\. It defaults to true\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

