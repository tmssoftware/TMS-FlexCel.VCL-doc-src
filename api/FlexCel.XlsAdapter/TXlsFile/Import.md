---
uid: TXlsFile.Import
description: TXlsFile.Import
---

# TXlsFile\.Import Method

## Overloads

* [TXlsFile\.Import\(TTextReader, Integer, Integer, Int32Array, TColumnImportTypeArray, TArray\<string>\)](#txlsfileimportttextreader-integer-integer-int32array-tcolumnimporttypearray-tarraystring)
* [TXlsFile\.Import\(TTextReader, Integer, Integer, Char, Char, TColumnImportTypeArray, TArray\<string>\)](#txlsfileimportttextreader-integer-integer-char-char-tcolumnimporttypearray-tarraystring)

# TXlsFile\.Import\(TTextReader, Integer, Integer, Int32Array, TColumnImportTypeArray, TArray\<string>\)
Imports a text file \(fixed length columns\) into the current sheet\. Note that this method won't clear any existing data\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.Import(const aTextReader: TTextReader; const firstRow: Integer; const firstCol: Integer; const columnWidths: TArray&lt;Int32>; const columnFormats: <a href="../../FlexCel.Core/TColumnImportType.md">TArray&lt;TColumnImportType></a>; const dateFormats: TArray&lt;string&gt;); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aTextReader**|TTextReader|StreamReader with the text to import\.|
|const|**firstRow**|Integer|Row in the Active sheet where we will start importing the text file\.|
|const|**firstCol**|Integer|Column in the Active sheet where we will start importing the text file\.|
|const|**columnWidths**|TArray\<Int32>|An array with the column widths for every column you want to import\.|
|const|**columnFormats**|[TArray\<&#8203;TColumn&#8203;Import&#8203;Type>](../../FlexCel.Core/TColumnImportType.md)|An array of [TColumnImportType](../../FlexCel.Core/TColumnImportType.md) elements, telling how each column should be imported\.<br />See the example in [TExcelFile.Open\(TStream, TFileFormats, Char, Integer, Integer, TColumnImportTypeArray\)](../../FlexCel.Core/TExcelFile/Open.md#texcelfileopentstream-tfileformats-char-integer-integer-tcolumnimporttypearray) for more information on how to use it\.<br />|
|const|**dateFormats**|TArray\<string>|**Note:**This format must be expressed with \.NET notation, as specified here: [http://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx](http://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx) \.A list of formats allowed for dates and times, when opening text files\. Windows is a little liberal in what it thinks can be a date, and it can convert things like "1\.2" into dates\. By setting this property, you can ensure the dates are only in the formats you expect\. If you leave it null, we will trust "DateTime\.TryParse" to guess the correct values\. This value has no meaning in normal xls files, only text files\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.Import\(TTextReader, Integer, Integer, Char, Char, TColumnImportTypeArray, TArray\<string>\)
Imports a text file \(character\-delimited columns\) into the current sheet\. Note that this method won't clear any existing data\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.Import(const aTextReader: TTextReader; const firstRow: Integer; const firstCol: Integer; const delimiter: Char; const textQualifier: Char; const columnFormats: <a href="../../FlexCel.Core/TColumnImportType.md">TArray&lt;TColumnImportType></a>; const dateFormats: TArray&lt;string&gt;); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aTextReader**|TTextReader|TextReader with the text to import\.|
|const|**firstRow**|Integer|Row in the Active sheet where we will start importing the text file\.|
|const|**firstCol**|Integer|Column in the Active sheet where we will start importing the text file\.|
|const|**delimiter**|Char|Character used to separate columns\.|
|const|**textQualifier**|Char|Character used to quote strings when they contain the delimiter\. This is normally the double quote \("\) but you might change it by a single quote or any other character\. Use a char 0 if the original file isn't quoted\.|
|const|**columnFormats**|[TArray\<&#8203;TColumn&#8203;Import&#8203;Type>](../../FlexCel.Core/TColumnImportType.md)|An array of [TColumnImportType](../../FlexCel.Core/TColumnImportType.md) elements, telling how each column should be imported\.<br />See the example in [TExcelFile.Open\(TStream, TFileFormats, Char, Integer, Integer, TColumnImportTypeArray\)](../../FlexCel.Core/TExcelFile/Open.md#texcelfileopentstream-tfileformats-char-integer-integer-tcolumnimporttypearray) for more information on how to use it\.<br />|
|const|**dateFormats**|TArray\<string>|**Note:**This format must be expressed with \.NET notation, as specified here: [http://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx](http://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx) \.A list of formats allowed for dates and times, when opening text files\. Windows is a little liberal in what it thinks can be a date, and it can convert things like "1\.2" into dates\. By setting this property, you can ensure the dates are only in the formats you expect\. If you leave it null, we will trust "DateTime\.TryParse" to guess the correct values\. This value has no meaning in normal xls files, only text files\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

