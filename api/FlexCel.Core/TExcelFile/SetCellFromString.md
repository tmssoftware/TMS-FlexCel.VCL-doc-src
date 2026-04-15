---
uid: TExcelFile.SetCellFromString
description: TExcelFile.SetCellFromString
---

# TExcelFile\.SetCellFromString Method

## Overloads

* [TExcelFile\.SetCellFromString\(Integer, Integer, string\)](#texcelfilesetcellfromstringinteger-integer-string)
* [TExcelFile\.SetCellFromString\(Integer, Integer, TRichString\)](#texcelfilesetcellfromstringinteger-integer-trichstring)
* [TExcelFile\.SetCellFromString\(string, string, TArray\<string>\)](#texcelfilesetcellfromstringstring-string-tarraystring)
* [TExcelFile\.SetCellFromString\(Integer, Integer, string, TArray\<string>\)](#texcelfilesetcellfromstringinteger-integer-string-tarraystring)
* [TExcelFile\.SetCellFromString\(Integer, Integer, TRichString, TArray\<string>\)](#texcelfilesetcellfromstringinteger-integer-trichstring-tarraystring)
* [TExcelFile\.SetCellFromString\(Integer, Integer, string, Integer\)](#texcelfilesetcellfromstringinteger-integer-string-integer)
* [TExcelFile\.SetCellFromString\(Integer, Integer, TRichString, Integer\)](#texcelfilesetcellfromstringinteger-integer-trichstring-integer)
* [TExcelFile\.SetCellFromString\(Integer, Integer, string, Integer, TArray\<string>\)](#texcelfilesetcellfromstringinteger-integer-string-integer-tarraystring)
* [TExcelFile\.SetCellFromString\(Integer, Integer, TRichString, Integer, TArray\<string>\)](#texcelfilesetcellfromstringinteger-integer-trichstring-integer-tarraystring)
* [TExcelFile\.SetCellFromString\(Integer, Integer, Integer, TRichString, Integer, TArray\<string>\)](#texcelfilesetcellfromstringinteger-integer-integer-trichstring-integer-tarraystring)

# TExcelFile\.SetCellFromString\(Integer, Integer, string\)
Converts a string to the best datatype, and the enters it into a cell\.


## Remarks

When using [SetCellValue\(Integer, Integer, TCellValue, Integer\)](SetCellValue.md#texcelfilesetcellvalueinteger-integer-tcellvalue-integer) to set a cell value, you have to know the datatype you want to enter\.
That is, if you have a string s="1/1/2002" and call SetCellValue\(1,1,s\); the cell A1 will end up with a string "1/1/2002" and not with a date\. The same if you have a string holding a number\.





SetCellFromString tries to solve this problem\. When you call SetCellFromString\(1, 1, s\) it will look:


1. If s contains a valid number: If it does, it will enter the number into the cell, and not the string s
2. If s contains a boolean:      If s equals the words "TRUE" or "FALSE" \(or whatever you define on the constants TxtTrue and TxtFalse\) it will enter the boolean into the cell
3. If s contains a date:         If s is a valid date \(according to your windows settings, or with a list of allowed date/time formats\) it will enter a number into the cell and format the cell as a date\. \(see ['Date cells' in the Api Developer Guide](xref:ApiDeveloperGuide#date-cells)\)
4. In any other case, it will enter the string s into the cell\.



## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetCellFromString(const row: Integer; const col: Integer; const value: string); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Cell Row \(1 based\)|
|const|**col**|Integer|Cell Column \(1 based\)|
|const|**value**|string|Value to enter into the cell\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.SetCellFromString\(Integer, Integer, TRichString\)
Converts a string to the best datatype, and the enters it into a cell\.


## Remarks

When using [SetCellValue\(Integer, Integer, TCellValue, Integer\)](SetCellValue.md#texcelfilesetcellvalueinteger-integer-tcellvalue-integer) to set a cell value, you have to know the datatype you want to enter\.
That is, if you have a string s="1/1/2002" and call SetCellValue\(1,1,s\); the cell A1 will end up with a string "1/1/2002" and not with a date\. The same if you have a string holding a number\.





SetCellFromString tries to solve this problem\. When you call SetCellFromString\(1, 1, s\) it will look:


1. If s contains a valid number: If it does, it will enter the number into the cell, and not the string s
2. If s contains a boolean:      If s equals the words "TRUE" or "FALSE" \(or whatever you define on the constants TxtTrue and TxtFalse\) it will enter the boolean into the cell
3. If s contains a date:         If s is a valid date \(according to your windows settings, or with a list of allowed date/time formats\) it will enter a number into the cell and format the cell as a date\. \(see ['Date cells' in the Api Developer Guide](xref:ApiDeveloperGuide#date-cells)\)
4. In any other case, it will enter the string s into the cell\.



## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetCellFromString(const row: Integer; const col: Integer; const value: <a href="../TRichString/index.md">TRichString</a>); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Cell Row \(1 based\)|
|const|**col**|Integer|Cell Column \(1 based\)|
|const|**value**|[TRichString](../TRichString/index.md)|Value to enter into the cell\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.SetCellFromString\(string, string, TArray\<string>\)
Converts a string into the best datatype \(a boolean, a number, etc\)

## Remarks

See [SetCellFromString\(Integer, Integer, TRichString, Integer\)](SetCellFromString.md#texcelfilesetcellfromstringinteger-integer-trichstring-integer) for more information\.

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetCellFromString(const cellRef: string; const value: string; const dateFormats: TArray&lt;string&gt;); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**cellRef**|string|Cell reference in A1 notation\. Something like A3, or Sheet1\!$B$5 can be used here\.|
|const|**value**|string|RichString to convert\.|
|const|**dateFormats**|TArray\<string>|A list of formats allowed for dates and times\. Windows is a little liberal in what it thinks can be a date, and it can convert things  like "1\.2" into dates\. By setting this property, you can ensure the dates are only in the formats you expect\. If you leave it null, we will trust "DateTime\.TryParse" to guess the correct values\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.SetCellFromString\(Integer, Integer, string, TArray\<string>\)
Converts a string to the best datatype, and the enters it into a cell\.


## Remarks

When using [SetCellValue\(Integer, Integer, TCellValue, Integer\)](SetCellValue.md#texcelfilesetcellvalueinteger-integer-tcellvalue-integer) to set a cell value, you have to know the datatype you want to enter\.
That is, if you have a string s="1/1/2002" and call SetCellValue\(1,1,s\); the cell A1 will end up with a string "1/1/2002" and not with a date\. The same if you have a string holding a number\.





SetCellFromString tries to solve this problem\. When you call SetCellFromString\(1, 1, s\) it will look:


1. If s contains a valid number: If it does, it will enter the number into the cell, and not the string s
2. If s contains a boolean:      If s equals the words "TRUE" or "FALSE" \(or whatever you define on the constants TxtTrue and TxtFalse\) it will enter the boolean into the cell
3. If s contains a date:         If s is a valid date \(according to your windows settings, or with a list of allowed date/time formats\) it will enter a number into the cell and format the cell as a date\. \(see ['Date cells' in the Api Developer Guide](xref:ApiDeveloperGuide#date-cells)\)
4. In any other case, it will enter the string s into the cell\.



## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetCellFromString(const row: Integer; const col: Integer; const value: string; const dateFormats: TArray&lt;string&gt;); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Cell Row \(1 based\)|
|const|**col**|Integer|Cell Column \(1 based\)|
|const|**value**|string|Value to enter into the cell\.|
|const|**dateFormats**|TArray\<string>|**Note:**This format must be expressed with \.NET notation, as specified here: [http://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx](http://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx) \.A list of formats allowed for dates and times\. Windows is a little liberal in what it thinks can be a date, and it can convert things like "1\.2" into dates\. By setting this property, you can ensure the dates are only in the formats you expect\. If you leave it null, we will trust "DateTime\.TryParse" to guess the correct values\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.SetCellFromString\(Integer, Integer, TRichString, TArray\<string>\)
Converts a string to the best datatype, and the enters it into a cell\.


## Remarks

When using [SetCellValue\(Integer, Integer, TCellValue, Integer\)](SetCellValue.md#texcelfilesetcellvalueinteger-integer-tcellvalue-integer) to set a cell value, you have to know the datatype you want to enter\.
That is, if you have a string s="1/1/2002" and call SetCellValue\(1,1,s\); the cell A1 will end up with a string "1/1/2002" and not with a date\. The same if you have a string holding a number\.





SetCellFromString tries to solve this problem\. When you call SetCellFromString\(1, 1, s\) it will look:


1. If s contains a valid number: If it does, it will enter the number into the cell, and not the string s
2. If s contains a boolean:      If s equals the words "TRUE" or "FALSE" \(or whatever you define on the constants TxtTrue and TxtFalse\) it will enter the boolean into the cell
3. If s contains a date:         If s is a valid date \(according to your windows settings, or with a list of allowed date/time formats\) it will enter a number into the cell and format the cell as a date\. \(see ['Date cells' in the Api Developer Guide](xref:ApiDeveloperGuide#date-cells)\)
4. In any other case, it will enter the string s into the cell\.



## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetCellFromString(const row: Integer; const col: Integer; const value: <a href="../TRichString/index.md">TRichString</a>; const dateFormats: TArray&lt;string&gt;); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Cell Row \(1 based\)|
|const|**col**|Integer|Cell Column \(1 based\)|
|const|**value**|[TRichString](../TRichString/index.md)|Value to enter into the cell\.|
|const|**dateFormats**|TArray\<string>|**Note:**This format must be expressed with \.NET notation, as specified here: [http://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx](http://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx) \.A list of formats allowed for dates and times\. Windows is a little liberal in what it thinks can be a date, and it can convert things like "1\.2" into dates\. By setting this property, you can ensure the dates are only in the formats you expect\. If you leave it null, we will trust "DateTime\.TryParse" to guess the correct values\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.SetCellFromString\(Integer, Integer, string, Integer\)
Converts a string to the best datatype, and the enters it into a cell\.


## Remarks

When using [SetCellValue\(Integer, Integer, TCellValue, Integer\)](SetCellValue.md#texcelfilesetcellvalueinteger-integer-tcellvalue-integer) to set a cell value, you have to know the datatype you want to enter\.
That is, if you have a string s="1/1/2002" and call SetCellValue\(1,1,s\); the cell A1 will end up with a string "1/1/2002" and not with a date\. The same if you have a string holding a number\.





SetCellFromString tries to solve this problem\. When you call SetCellFromString\(1, 1, s\) it will look:


1. If s contains a valid number: If it does, it will enter the number into the cell, and not the string s
2. If s contains a boolean:      If s equals the words "TRUE" or "FALSE" \(or whatever you define on the constants TxtTrue and TxtFalse\) it will enter the boolean into the cell
3. If s contains a date:         If s is a valid date \(according to your windows settings, or with a list of allowed date/time formats\) it will enter a number into the cell and format the cell as a date\. \(see ['Date cells' in the Api Developer Guide](xref:ApiDeveloperGuide#date-cells)\)
4. In any other case, it will enter the string s into the cell\.



## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetCellFromString(const row: Integer; const col: Integer; const value: string; const XF: Integer); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Cell Row \(1 based\)|
|const|**col**|Integer|Cell Column \(1 based\)|
|const|**value**|string|Value to enter into the cell\.|
|const|**XF**|Integer|New XF of the cell\. It can be modified, i\.e\. if you enter a date, the XF will be converted to a Date XF\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.SetCellFromString\(Integer, Integer, TRichString, Integer\)
Converts a string to the best datatype, and the enters it into a cell\.


## Remarks

When using [SetCellValue\(Integer, Integer, TCellValue, Integer\)](SetCellValue.md#texcelfilesetcellvalueinteger-integer-tcellvalue-integer) to set a cell value, you have to know the datatype you want to enter\.
That is, if you have a string s="1/1/2002" and call SetCellValue\(1,1,s\); the cell A1 will end up with a string "1/1/2002" and not with a date\. The same if you have a string holding a number\.





SetCellFromString tries to solve this problem\. When you call SetCellFromString\(1, 1, s\) it will look:


1. If s contains a valid number: If it does, it will enter the number into the cell, and not the string s
2. If s contains a boolean:      If s equals the words "TRUE" or "FALSE" \(or whatever you define on the constants TxtTrue and TxtFalse\) it will enter the boolean into the cell
3. If s contains a date:         If s is a valid date \(according to your windows settings, or with a list of allowed date/time formats\) it will enter a number into the cell and format the cell as a date\. \(see ['Date cells' in the Api Developer Guide](xref:ApiDeveloperGuide#date-cells)\)
4. In any other case, it will enter the string s into the cell\.



## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetCellFromString(const row: Integer; const col: Integer; const value: <a href="../TRichString/index.md">TRichString</a>; const XF: Integer); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Cell Row \(1 based\)|
|const|**col**|Integer|Cell Column \(1 based\)|
|const|**value**|[TRichString](../TRichString/index.md)|Value to enter into the cell\.|
|const|**XF**|Integer|New XF of the cell\. It can be modified, i\.e\. if you enter a date, the XF will be converted to a Date XF\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.SetCellFromString\(Integer, Integer, string, Integer, TArray\<string>\)
Converts a string to the best datatype, and the enters it into a cell\.


## Remarks

When using [SetCellValue\(Integer, Integer, TCellValue, Integer\)](SetCellValue.md#texcelfilesetcellvalueinteger-integer-tcellvalue-integer) to set a cell value, you have to know the datatype you want to enter\.
That is, if you have a string s="1/1/2002" and call SetCellValue\(1,1,s\); the cell A1 will end up with a string "1/1/2002" and not with a date\. The same if you have a string holding a number\.





SetCellFromString tries to solve this problem\. When you call SetCellFromString\(1, 1, s\) it will look:


1. If s contains a valid number: If it does, it will enter the number into the cell, and not the string s
2. If s contains a boolean:      If s equals the words "TRUE" or "FALSE" \(or whatever you define on the constants TxtTrue and TxtFalse\) it will enter the boolean into the cell
3. If s contains a date:         If s is a valid date \(according to your windows settings, or with a list of allowed date/time formats\) it will enter a number into the cell and format the cell as a date\. \(see ['Date cells' in the Api Developer Guide](xref:ApiDeveloperGuide#date-cells)\)
4. In any other case, it will enter the string s into the cell\.



## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetCellFromString(const row: Integer; const col: Integer; const value: string; const XF: Integer; const dateFormats: TArray&lt;string&gt;); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Cell Row \(1 based\)|
|const|**col**|Integer|Cell Column \(1 based\)|
|const|**value**|string|Value to enter into the cell\.|
|const|**XF**|Integer|New XF of the cell\. It can be modified, i\.e\. if you enter a date, the XF will be converted to a Date XF\.|
|const|**dateFormats**|TArray\<string>|**Note:**This format must be expressed with \.NET notation, as specified here: [http://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx](http://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx) \.A list of formats allowed for dates and times\. Windows is a little liberal in what it thinks can be a date, and it can convert things like "1\.2" into dates\. By setting this property, you can ensure the dates are only in the formats you expect\. If you leave it null, we will trust "DateTime\.TryParse" to guess the correct values\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.SetCellFromString\(Integer, Integer, TRichString, Integer, TArray\<string>\)
Converts a string to the best datatype, and the enters it into a cell\.


## Remarks

When using [SetCellValue\(Integer, Integer, TCellValue, Integer\)](SetCellValue.md#texcelfilesetcellvalueinteger-integer-tcellvalue-integer) to set a cell value, you have to know the datatype you want to enter\.
That is, if you have a string s="1/1/2002" and call SetCellValue\(1,1,s\); the cell A1 will end up with a string "1/1/2002" and not with a date\. The same if you have a string holding a number\.





SetCellFromString tries to solve this problem\. When you call SetCellFromString\(1, 1, s\) it will look:


1. If s contains a valid number: If it does, it will enter the number into the cell, and not the string s
2. If s contains a boolean:      If s equals the words "TRUE" or "FALSE" \(or whatever you define on the constants TxtTrue and TxtFalse\) it will enter the boolean into the cell
3. If s contains a date:         If s is a valid date \(according to your windows settings, or with a list of allowed date/time formats\) it will enter a number into the cell and format the cell as a date\. \(see ['Date cells' in the Api Developer Guide](xref:ApiDeveloperGuide#date-cells)\)
4. In any other case, it will enter the string s into the cell\.



## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetCellFromString(const row: Integer; const col: Integer; const value: <a href="../TRichString/index.md">TRichString</a>; const XF: Integer; const dateFormats: TArray&lt;string&gt;); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Cell Row \(1 based\)|
|const|**col**|Integer|Cell Column \(1 based\)|
|const|**value**|[TRichString](../TRichString/index.md)|Value to enter into the cell\.|
|const|**XF**|Integer|New XF of the cell\. It can be modified, i\.e\. if you enter a date, the XF will be converted to a Date XF\.|
|const|**dateFormats**|TArray\<string>|**Note:**This format must be expressed with \.NET notation, as specified here: [http://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx](http://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx) \.A list of formats allowed for dates and times\. Windows is a little liberal in what it thinks can be a date, and it can convert things like "1\.2" into dates\. By setting this property, you can ensure the dates are only in the formats you expect\. If you leave it null, we will trust "DateTime\.TryParse" to guess the correct values\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.SetCellFromString\(Integer, Integer, Integer, TRichString, Integer, TArray\<string>\)
Converts a string to the best datatype, and the enters it into a cell\.


## Remarks

When using [SetCellValue\(Integer, Integer, TCellValue, Integer\)](SetCellValue.md#texcelfilesetcellvalueinteger-integer-tcellvalue-integer) to set a cell value, you have to know the datatype you want to enter\.
That is, if you have a string s="1/1/2002" and call SetCellValue\(1,1,s\); the cell A1 will end up with a string "1/1/2002" and not with a date\. The same if you have a string holding a number\.





SetCellFromString tries to solve this problem\. When you call SetCellFromString\(1, 1, s\) it will look:


1. If s contains a valid number: If it does, it will enter the number into the cell, and not the string s
2. If s contains a boolean:      If s equals the words "TRUE" or "FALSE" \(or whatever you define on the constants TxtTrue and TxtFalse\) it will enter the boolean into the cell
3. If s contains a date:         If s is a valid date \(according to your windows settings, or with a list of allowed date/time formats\) it will enter a number into the cell and format the cell as a date\. \(see ['Date cells' in the Api Developer Guide](xref:ApiDeveloperGuide#date-cells)\)
4. In any other case, it will enter the string s into the cell\.



## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetCellFromString(const sheet: Integer; const row: Integer; const col: Integer; const value: <a href="../TRichString/index.md">TRichString</a>; const XF: Integer; const dateFormats: TArray&lt;string&gt;); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer|Sheet where the cell is \(1 based\)|
|const|**row**|Integer|Cell Row \(1 based\)|
|const|**col**|Integer|Cell Column \(1 based\)|
|const|**value**|[TRichString](../TRichString/index.md)|Value to enter into the cell\.|
|const|**XF**|Integer|New XF of the cell\. It can be modified, i\.e\. if you enter a date, the XF will be converted to a Date XF\.|
|const|**dateFormats**|TArray\<string>|**Note:**This format must be expressed with \.NET notation, as specified here: [http://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx](http://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx) \.A list of formats allowed for dates and times\. Windows is a little liberal in what it thinks can be a date, and it can convert things like "1\.2" into dates\. By setting this property, you can ensure the dates are only in the formats you expect\. If you leave it null, we will trust "DateTime\.TryParse" to guess the correct values\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

