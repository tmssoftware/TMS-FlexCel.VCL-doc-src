---
uid: TXlsFile.ConvertString
description: TXlsFile.ConvertString
---

# TXlsFile\.ConvertString Method

Converts a string into the best datatype \(a boolean, a number, etc\)

## Remarks

See [TExcelFile.SetCellFromString\(Integer, Integer, TRichString, Integer\)](../../FlexCel.Core/TExcelFile/SetCellFromString.md#texcelfilesetcellfromstringinteger-integer-trichstring-integer) for more information\.

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.ConvertString(const value: <a href="../../FlexCel.Core/TRichString/index.md">TRichString</a>; var XF: Integer; const dateFormats: TArray&lt;string&gt;): <a href="../../FlexCel.Core/TCellValue/index.md">TCellValue</a>; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**value**|[TRichString](../../FlexCel.Core/TRichString/index.md)|RichString to convert\.|
|var|**XF**|Integer|XF of the cell\. It might be modified, for example, if you are entering a date\.|
|const|**dateFormats**|TArray\<string>|**Note:**This format must be expressed with \.NET notation, as specified here: [http://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx](http://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx) \.A list of formats allowed for dates and times\. Windows is a little liberal in what it thinks can be a date, and it can convert things like "1\.2" into dates\. By setting this property, you can ensure the dates are only in the formats you expect\. If you leave it null, we will trust "DateTime\.TryParse" to guess the correct values\.|


## Returns

value converted to the best datatype\.

## See also

* [TXlsFile](../TXlsFile/index.md)

