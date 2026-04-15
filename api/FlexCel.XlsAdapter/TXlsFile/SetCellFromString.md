---
uid: TXlsFile.SetCellFromString
description: TXlsFile.SetCellFromString
---

# TXlsFile\.SetCellFromString Method

Converts a string to the best datatype, and the enters it into a cell\.


## Remarks

When using [TExcelFile.SetCellValue\(Integer, Integer, TCellValue, Integer\)](../../FlexCel.Core/TExcelFile/SetCellValue.md#texcelfilesetcellvalueinteger-integer-tcellvalue-integer) to set a cell value, you have to know the datatype you want to enter\.
That is, if you have a string s="1/1/2002" and call SetCellValue\(1,1,s\); the cell A1 will end up with a string "1/1/2002" and not with a date\. The same if you have a string holding a number\.





SetCellFromString tries to solve this problem\. When you call SetCellFromString\(1, 1, s\) it will look:


1. If s contains a valid number: If it does, it will enter the number into the cell, and not the string s
2. If s contains a boolean:      If s equals the words "TRUE" or "FALSE" \(or whatever you define on the constants TxtTrue and TxtFalse\) it will enter the boolean into the cell
3. If s contains a date:         If s is a valid date \(according to your windows settings, or with a list of allowed date/time formats\) it will enter a number into the cell and format the cell as a date\. \(see ['Date cells' in the Api Developer Guide](xref:ApiDeveloperGuide#date-cells)\)
4. In any other case, it will enter the string s into the cell\.



## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetCellFromString(const sheet: Integer; const row: Integer; const col: Integer; const value: <a href="../../FlexCel.Core/TRichString/index.md">TRichString</a>; const XF: Integer; const dateFormats: TArray&lt;string&gt;); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer|Sheet where the cell is \(1 based\)|
|const|**row**|Integer|Cell Row \(1 based\)|
|const|**col**|Integer|Cell Column \(1 based\)|
|const|**value**|[TRichString](../../FlexCel.Core/TRichString/index.md)|Value to enter into the cell\.|
|const|**XF**|Integer|New XF of the cell\. It can be modified, i\.e\. if you enter a date, the XF will be converted to a Date XF\.|
|const|**dateFormats**|TArray\<string>|**Note:**This format must be expressed with \.NET notation, as specified here: [http://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx](http://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx) \.A list of formats allowed for dates and times\. Windows is a little liberal in what it thinks can be a date, and it can convert things like "1\.2" into dates\. By setting this property, you can ensure the dates are only in the formats you expect\. If you leave it null, we will trust "DateTime\.TryParse" to guess the correct values\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

