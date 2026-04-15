---
uid: TXlsFile.SetCellValue
description: TXlsFile.SetCellValue
---

# TXlsFile\.SetCellValue Method

## Overloads

* [TXlsFile\.SetCellValue\(Integer, Integer, TCellValue, Integer\)](#txlsfilesetcellvalueinteger-integer-tcellvalue-integer)
* [TXlsFile\.SetCellValue\(Integer, Integer, string, Integer\)](#txlsfilesetcellvalueinteger-integer-string-integer)
* [TXlsFile\.SetCellValue\(Integer, Integer, TRichString, Integer\)](#txlsfilesetcellvalueinteger-integer-trichstring-integer)
* [TXlsFile\.SetCellValue\(Integer, Integer, TDateTime, Integer\)](#txlsfilesetcellvalueinteger-integer-tdatetime-integer)
* [TXlsFile\.SetCellValue\(Integer, Integer, Double, Integer\)](#txlsfilesetcellvalueinteger-integer-double-integer)
* [TXlsFile\.SetCellValue\(Integer, Integer, Single, Integer\)](#txlsfilesetcellvalueinteger-integer-single-integer)
* [TXlsFile\.SetCellValue\(Integer, Integer, Integer, Integer\)](#txlsfilesetcellvalueinteger-integer-integer-integer)
* [TXlsFile\.SetCellValue\(Integer, Integer, Int64, Integer\)](#txlsfilesetcellvalueinteger-integer-int64-integer)
* [TXlsFile\.SetCellValue\(Integer, Integer, Integer, TCellValue, Integer\)](#txlsfilesetcellvalueinteger-integer-integer-tcellvalue-integer)
* [TXlsFile\.SetCellValue\(Integer, Integer, Integer, string, Integer\)](#txlsfilesetcellvalueinteger-integer-integer-string-integer)
* [TXlsFile\.SetCellValue\(Integer, Integer, Integer, Double, Integer\)](#txlsfilesetcellvalueinteger-integer-integer-double-integer)
* [TXlsFile\.SetCellValue\(Integer, Integer, Integer, Integer, Integer\)](#txlsfilesetcellvalueinteger-integer-integer-integer-integer)

# TXlsFile\.SetCellValue\(Integer, Integer, TCellValue, Integer\)
Sets the value and format on a cell\.


## Remarks

This method will enter the datatype of the object you pass to it\. For example, if you set value="1" the string "1" will be entered on the cell\. To convert a string to the best representation \(on this case a number\), use [TExcelFile.SetCellFromString\(Integer, Integer, TRichString, Integer\)](../../FlexCel.Core/TExcelFile/SetCellFromString.md#texcelfilesetcellfromstringinteger-integer-trichstring-integer) To enter a HTML formatted string, use [TExcelFile.SetCellFromHtml\(Integer, Integer, string, Integer\)](../../FlexCel.Core/TExcelFile/SetCellFromHtml.md#texcelfilesetcellfromhtmlinteger-integer-string-integer)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetCellValue(const row: Integer; const col: Integer; const value: <a href="../../FlexCel.Core/TCellValue/index.md">TCellValue</a>; const XF: Integer = -1); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row, 1 based\.|
|const|**col**|Integer|Column, 1 based\.|
|const|**value**|[TCellValue](../../FlexCel.Core/TCellValue/index.md)|Value to set\.|
|const|**XF**|Integer|**Optional**: Default value is -1<br /><br />Format to Set\. You normally get this number with [TExcelFile.AddFormat](../../FlexCel.Core/TExcelFile/AddFormat.md) function\. Use \-1 \(the default\) to keep format unchanged\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.SetCellValue\(Integer, Integer, string, Integer\)
Sets the value on a cell to a string\.


## Remarks

This method will enter the datatype of the object you pass to it\. For example, if you set value="1" the string "1" will be entered on the cell\. To convert a string to the best representation \(on this case a number\), use [TExcelFile.SetCellFromString\(Integer, Integer, TRichString, Integer\)](../../FlexCel.Core/TExcelFile/SetCellFromString.md#texcelfilesetcellfromstringinteger-integer-trichstring-integer)\.
To enter a HTML formatted string, use [TExcelFile.SetCellFromHtml\(Integer, Integer, string, Integer\)](../../FlexCel.Core/TExcelFile/SetCellFromHtml.md#texcelfilesetcellfromhtmlinteger-integer-string-integer)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetCellValue(const row: Integer; const col: Integer; const value: string; const XF: Integer = -1); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row, 1 based\.|
|const|**col**|Integer|Column, 1 based\.|
|const|**value**|string|Value to set\.|
|const|**XF**|Integer|**Optional**: Default value is -1<br /><br />Format to Set\. You normally get this number with [TExcelFile.AddFormat](../../FlexCel.Core/TExcelFile/AddFormat.md) function\. Use \-1 \(the default\) to keep format unchanged\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.SetCellValue\(Integer, Integer, TRichString, Integer\)
Sets the value on a cell to a string\.


## Remarks

This method will enter the datatype of the object you pass to it\. For example, if you set value="1" the string "1" will be entered on the cell\. To convert a string to the best representation \(on this case a number\), use [TExcelFile.SetCellFromString\(Integer, Integer, TRichString, Integer\)](../../FlexCel.Core/TExcelFile/SetCellFromString.md#texcelfilesetcellfromstringinteger-integer-trichstring-integer)\.
To enter a HTML formatted string, use [TExcelFile.SetCellFromHtml\(Integer, Integer, string, Integer\)](../../FlexCel.Core/TExcelFile/SetCellFromHtml.md#texcelfilesetcellfromhtmlinteger-integer-string-integer)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetCellValue(const row: Integer; const col: Integer; const value: <a href="../../FlexCel.Core/TRichString/index.md">TRichString</a>; const XF: Integer = -1); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row, 1 based\.|
|const|**col**|Integer|Column, 1 based\.|
|const|**value**|[TRichString](../../FlexCel.Core/TRichString/index.md)|Value to set\.|
|const|**XF**|Integer|**Optional**: Default value is -1<br /><br />Format to Set\. You normally get this number with [TExcelFile.AddFormat](../../FlexCel.Core/TExcelFile/AddFormat.md) function\. Use \-1 \(the default\) to keep format unchanged\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.SetCellValue\(Integer, Integer, TDateTime, Integer\)
Sets the value on a cell to a datetime\.


## Remarks

This method will enter the datatype of the object you pass to it\. For example, if you set value="1" the string "1" will be entered on the cell\. To convert a string to the best representation \(on this case a number\), use [TExcelFile.SetCellFromString\(Integer, Integer, TRichString, Integer\)](../../FlexCel.Core/TExcelFile/SetCellFromString.md#texcelfilesetcellfromstringinteger-integer-trichstring-integer)\.
To enter a HTML formatted string, use [TExcelFile.SetCellFromHtml\(Integer, Integer, string, Integer\)](../../FlexCel.Core/TExcelFile/SetCellFromHtml.md#texcelfilesetcellfromhtmlinteger-integer-string-integer)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetCellValue(const row: Integer; const col: Integer; const value: TDateTime; const XF: Integer = -1); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row, 1 based\.|
|const|**col**|Integer|Column, 1 based\.|
|const|**value**|TDateTime|Value to set\.|
|const|**XF**|Integer|**Optional**: Default value is -1<br /><br />Format to Set\. You normally get this number with [TExcelFile.AddFormat](../../FlexCel.Core/TExcelFile/AddFormat.md) function\. Use \-1 \(the default\) to keep format unchanged\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.SetCellValue\(Integer, Integer, Double, Integer\)
Sets the value on a cell to a number\.


## Remarks

This method will enter the datatype of the object you pass to it\. For example, if you set value="1" the string "1" will be entered on the cell\. To convert a string to the best representation \(on this case a number\), use [TExcelFile.SetCellFromString\(Integer, Integer, TRichString, Integer\)](../../FlexCel.Core/TExcelFile/SetCellFromString.md#texcelfilesetcellfromstringinteger-integer-trichstring-integer)\.
To enter a HTML formatted string, use [TExcelFile.SetCellFromHtml\(Integer, Integer, string, Integer\)](../../FlexCel.Core/TExcelFile/SetCellFromHtml.md#texcelfilesetcellfromhtmlinteger-integer-string-integer)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetCellValue(const row: Integer; const col: Integer; const value: Double; const XF: Integer = -1); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row, 1 based\.|
|const|**col**|Integer|Column, 1 based\.|
|const|**value**|Double|Value to set\.|
|const|**XF**|Integer|**Optional**: Default value is -1<br /><br />Format to Set\. You normally get this number with [TExcelFile.AddFormat](../../FlexCel.Core/TExcelFile/AddFormat.md) function\. Use \-1 \(the default\) to keep format unchanged\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.SetCellValue\(Integer, Integer, Single, Integer\)
Sets the value on a cell to a number\.


## Remarks

This method will enter the datatype of the object you pass to it\. For example, if you set value="1" the string "1" will be entered on the cell\. To convert a string to the best representation \(on this case a number\), use [TExcelFile.SetCellFromString\(Integer, Integer, TRichString, Integer\)](../../FlexCel.Core/TExcelFile/SetCellFromString.md#texcelfilesetcellfromstringinteger-integer-trichstring-integer)\.
To enter a HTML formatted string, use [TExcelFile.SetCellFromHtml\(Integer, Integer, string, Integer\)](../../FlexCel.Core/TExcelFile/SetCellFromHtml.md#texcelfilesetcellfromhtmlinteger-integer-string-integer)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetCellValue(const row: Integer; const col: Integer; const value: Single; const XF: Integer = -1); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row, 1 based\.|
|const|**col**|Integer|Column, 1 based\.|
|const|**value**|Single|Value to set\.|
|const|**XF**|Integer|**Optional**: Default value is -1<br /><br />Format to Set\. You normally get this number with [TExcelFile.AddFormat](../../FlexCel.Core/TExcelFile/AddFormat.md) function\. Use \-1 \(the default\) to keep format unchanged\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.SetCellValue\(Integer, Integer, Integer, Integer\)
Sets the value on a cell to a number\.


## Remarks

This method will enter the datatype of the object you pass to it\. For example, if you set value="1" the string "1" will be entered on the cell\. To convert a string to the best representation \(on this case a number\), use [TExcelFile.SetCellFromString\(Integer, Integer, TRichString, Integer\)](../../FlexCel.Core/TExcelFile/SetCellFromString.md#texcelfilesetcellfromstringinteger-integer-trichstring-integer)\.
To enter a HTML formatted string, use [TExcelFile.SetCellFromHtml\(Integer, Integer, string, Integer\)](../../FlexCel.Core/TExcelFile/SetCellFromHtml.md#texcelfilesetcellfromhtmlinteger-integer-string-integer)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetCellValue(const row: Integer; const col: Integer; const value: Integer; const XF: Integer = -1); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row, 1 based\.|
|const|**col**|Integer|Column, 1 based\.|
|const|**value**|Integer|Value to set\.|
|const|**XF**|Integer|**Optional**: Default value is -1<br /><br />Format to Set\. You normally get this number with [TExcelFile.AddFormat](../../FlexCel.Core/TExcelFile/AddFormat.md) function\. Use \-1 \(the default\) to keep format unchanged\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.SetCellValue\(Integer, Integer, Int64, Integer\)
Sets the value on a cell to a number\.


## Remarks

This method will enter the datatype of the object you pass to it\. For example, if you set value="1" the string "1" will be entered on the cell\. To convert a string to the best representation \(on this case a number\), use [TExcelFile.SetCellFromString\(Integer, Integer, TRichString, Integer\)](../../FlexCel.Core/TExcelFile/SetCellFromString.md#texcelfilesetcellfromstringinteger-integer-trichstring-integer)\.
To enter a HTML formatted string, use [TExcelFile.SetCellFromHtml\(Integer, Integer, string, Integer\)](../../FlexCel.Core/TExcelFile/SetCellFromHtml.md#texcelfilesetcellfromhtmlinteger-integer-string-integer)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetCellValue(const row: Integer; const col: Integer; const value: Int64; const XF: Integer = -1); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row, 1 based\.|
|const|**col**|Integer|Column, 1 based\.|
|const|**value**|Int64|Value to set\.|
|const|**XF**|Integer|**Optional**: Default value is -1<br /><br />Format to Set\. You normally get this number with [TExcelFile.AddFormat](../../FlexCel.Core/TExcelFile/AddFormat.md) function\. Use \-1 \(the default\) to keep format unchanged\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.SetCellValue\(Integer, Integer, Integer, TCellValue, Integer\)
Sets the value on a cell\.


## Remarks

This method will enter the datatype of the object you pass to it\. For example, if you set value="1" the string "1" will be entered on the cell\. To convert a string to the best representation \(on this case a number\), use [TExcelFile.SetCellFromString\(Integer, Integer, TRichString, Integer\)](../../FlexCel.Core/TExcelFile/SetCellFromString.md#texcelfilesetcellfromstringinteger-integer-trichstring-integer)\.
To enter a HTML formatted string, use [TExcelFile.SetCellFromHtml\(Integer, Integer, string, Integer\)](../../FlexCel.Core/TExcelFile/SetCellFromHtml.md#texcelfilesetcellfromhtmlinteger-integer-string-integer)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetCellValue(const sheet: Integer; const row: Integer; const col: Integer; const value: <a href="../../FlexCel.Core/TCellValue/index.md">TCellValue</a>; const XF: Integer); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer|Sheet number, 1 based|
|const|**row**|Integer|Row, 1 based\.|
|const|**col**|Integer|Column, 1 based\.|
|const|**value**|[TCellValue](../../FlexCel.Core/TCellValue/index.md)|Value to set\.|
|const|**XF**|Integer|Format to Set\. You normally get this number with [TExcelFile.AddFormat](../../FlexCel.Core/TExcelFile/AddFormat.md) function\. Use \-1 to keep format unchanged\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.SetCellValue\(Integer, Integer, Integer, string, Integer\)
Sets the value on a cell\.


## Remarks

This method will enter the datatype of the object you pass to it\. For example, if you set value="1" the string "1" will be entered on the cell\. To convert a string to the best representation \(on this case a number\), use [TExcelFile.SetCellFromString\(Integer, Integer, TRichString, Integer\)](../../FlexCel.Core/TExcelFile/SetCellFromString.md#texcelfilesetcellfromstringinteger-integer-trichstring-integer)\.
To enter a HTML formatted string, use [TExcelFile.SetCellFromHtml\(Integer, Integer, string, Integer\)](../../FlexCel.Core/TExcelFile/SetCellFromHtml.md#texcelfilesetcellfromhtmlinteger-integer-string-integer)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetCellValue(const sheet: Integer; const row: Integer; const col: Integer; const value: string; const XF: Integer); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer|Sheet number, 1 based|
|const|**row**|Integer|Row, 1 based\.|
|const|**col**|Integer|Column, 1 based\.|
|const|**value**|string|Value to set\.|
|const|**XF**|Integer|Format to Set\. You normally get this number with [TExcelFile.AddFormat](../../FlexCel.Core/TExcelFile/AddFormat.md) function\. Use \-1 to keep format unchanged\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.SetCellValue\(Integer, Integer, Integer, Double, Integer\)
Sets the value on a cell\.


## Remarks

This method will enter the datatype of the object you pass to it\. For example, if you set value="1" the string "1" will be entered on the cell\. To convert a string to the best representation \(on this case a number\), use [TExcelFile.SetCellFromString\(Integer, Integer, TRichString, Integer\)](../../FlexCel.Core/TExcelFile/SetCellFromString.md#texcelfilesetcellfromstringinteger-integer-trichstring-integer)\.
To enter a HTML formatted string, use [TExcelFile.SetCellFromHtml\(Integer, Integer, string, Integer\)](../../FlexCel.Core/TExcelFile/SetCellFromHtml.md#texcelfilesetcellfromhtmlinteger-integer-string-integer)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetCellValue(const sheet: Integer; const row: Integer; const col: Integer; const value: Double; const XF: Integer); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer|Sheet number, 1 based|
|const|**row**|Integer|Row, 1 based\.|
|const|**col**|Integer|Column, 1 based\.|
|const|**value**|Double|Value to set\.|
|const|**XF**|Integer|Format to Set\. You normally get this number with [TExcelFile.AddFormat](../../FlexCel.Core/TExcelFile/AddFormat.md) function\. Use \-1 to keep format unchanged\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.SetCellValue\(Integer, Integer, Integer, Integer, Integer\)
Sets the value on a cell\.


## Remarks

This method will enter the datatype of the object you pass to it\. For example, if you set value="1" the string "1" will be entered on the cell\. To convert a string to the best representation \(on this case a number\), use [TExcelFile.SetCellFromString\(Integer, Integer, TRichString, Integer\)](../../FlexCel.Core/TExcelFile/SetCellFromString.md#texcelfilesetcellfromstringinteger-integer-trichstring-integer)\.
To enter a HTML formatted string, use [TExcelFile.SetCellFromHtml\(Integer, Integer, string, Integer\)](../../FlexCel.Core/TExcelFile/SetCellFromHtml.md#texcelfilesetcellfromhtmlinteger-integer-string-integer)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetCellValue(const sheet: Integer; const row: Integer; const col: Integer; const value: Integer; const XF: Integer); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer|Sheet number, 1 based|
|const|**row**|Integer|Row, 1 based\.|
|const|**col**|Integer|Column, 1 based\.|
|const|**value**|Integer|Value to set\.|
|const|**XF**|Integer|Format to Set\. You normally get this number with [TExcelFile.AddFormat](../../FlexCel.Core/TExcelFile/AddFormat.md) function\. Use \-1 to keep format unchanged\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

