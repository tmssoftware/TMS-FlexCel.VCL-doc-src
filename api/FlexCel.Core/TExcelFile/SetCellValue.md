---
uid: TExcelFile.SetCellValue
description: TExcelFile.SetCellValue
---

# TExcelFile\.SetCellValue Method

## Overloads

* [TExcelFile\.SetCellValue\(string, TCellValue\)](#texcelfilesetcellvaluestring-tcellvalue)
* [TExcelFile\.SetCellValue\(Integer, Integer, TCellValue, Integer\)](#texcelfilesetcellvalueinteger-integer-tcellvalue-integer)
* [TExcelFile\.SetCellValue\(Integer, Integer, string, Integer\)](#texcelfilesetcellvalueinteger-integer-string-integer)
* [TExcelFile\.SetCellValue\(Integer, Integer, TRichString, Integer\)](#texcelfilesetcellvalueinteger-integer-trichstring-integer)
* [TExcelFile\.SetCellValue\(Integer, Integer, Double, Integer\)](#texcelfilesetcellvalueinteger-integer-double-integer)
* [TExcelFile\.SetCellValue\(Integer, Integer, TDateTime, Integer\)](#texcelfilesetcellvalueinteger-integer-tdatetime-integer)
* [TExcelFile\.SetCellValue\(Integer, Integer, Integer, Integer\)](#texcelfilesetcellvalueinteger-integer-integer-integer)
* [TExcelFile\.SetCellValue\(Integer, Integer, Int64, Integer\)](#texcelfilesetcellvalueinteger-integer-int64-integer)
* [TExcelFile\.SetCellValue\(Integer, Integer, Single, Integer\)](#texcelfilesetcellvalueinteger-integer-single-integer)
* [TExcelFile\.SetCellValue\(Integer, Integer, Integer, TCellValue, Integer\)](#texcelfilesetcellvalueinteger-integer-integer-tcellvalue-integer)
* [TExcelFile\.SetCellValue\(Integer, Integer, Integer, string, Integer\)](#texcelfilesetcellvalueinteger-integer-integer-string-integer)
* [TExcelFile\.SetCellValue\(Integer, Integer, Integer, Double, Integer\)](#texcelfilesetcellvalueinteger-integer-integer-double-integer)
* [TExcelFile\.SetCellValue\(Integer, Integer, Integer, Integer, Integer\)](#texcelfilesetcellvalueinteger-integer-integer-integer-integer)

# TExcelFile\.SetCellValue\(string, TCellValue\)
Sets a cell value given a cell reference\. While this is normally not needed because you can use [TCellAddress](../TCellAddress/index.md) to convert  the cell reference to row and column and then use a standard SetCellValue call, it can be handy if you know the cell reference \(like AX42\) and want a fast way to set the value of the cell\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetCellValue(const cellRef: string; const value: <a href="../TCellValue/index.md">TCellValue</a>); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**cellRef**|string|Cell reference in A1 notation\. Something like A3, or Sheet1\!$B$5 can be used here\.|
|const|**value**|[TCellValue](../TCellValue/index.md)|Value to set\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.SetCellValue\(Integer, Integer, TCellValue, Integer\)
Sets the value and format on a cell\.


## Remarks

This method will enter the datatype of the object you pass to it\. For example, if you set value="1" the string "1" will be entered on the cell\. To convert a string to the best representation \(on this case a number\), use [SetCellFromString\(Integer, Integer, TRichString, Integer\)](SetCellFromString.md#texcelfilesetcellfromstringinteger-integer-trichstring-integer) To enter a HTML formatted string, use [SetCellFromHtml\(Integer, Integer, string, Integer\)](SetCellFromHtml.md#texcelfilesetcellfromhtmlinteger-integer-string-integer)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetCellValue(const row: Integer; const col: Integer; const value: <a href="../TCellValue/index.md">TCellValue</a>; const XF: Integer = -1); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row, 1 based\.|
|const|**col**|Integer|Column, 1 based\.|
|const|**value**|[TCellValue](../TCellValue/index.md)|Value to set\.|
|const|**XF**|Integer|**Optional**: Default value is -1<br /><br />Format to Set\. You normally get this number with [AddFormat](AddFormat.md) function\. Use \-1 \(the default\) to keep format unchanged\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.SetCellValue\(Integer, Integer, string, Integer\)
Sets the value on a cell to a string\.


## Remarks

This method will enter the datatype of the object you pass to it\. For example, if you set value="1" the string "1" will be entered on the cell\. To convert a string to the best representation \(on this case a number\), use [SetCellFromString\(Integer, Integer, TRichString, Integer\)](SetCellFromString.md#texcelfilesetcellfromstringinteger-integer-trichstring-integer)\.
To enter a HTML formatted string, use [SetCellFromHtml\(Integer, Integer, string, Integer\)](SetCellFromHtml.md#texcelfilesetcellfromhtmlinteger-integer-string-integer)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetCellValue(const row: Integer; const col: Integer; const value: string; const XF: Integer = -1); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row, 1 based\.|
|const|**col**|Integer|Column, 1 based\.|
|const|**value**|string|Value to set\.|
|const|**XF**|Integer|**Optional**: Default value is -1<br /><br />Format to Set\. You normally get this number with [AddFormat](AddFormat.md) function\. Use \-1 \(the default\) to keep format unchanged\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.SetCellValue\(Integer, Integer, TRichString, Integer\)
Sets the value on a cell to a string\.


## Remarks

This method will enter the datatype of the object you pass to it\. For example, if you set value="1" the string "1" will be entered on the cell\. To convert a string to the best representation \(on this case a number\), use [SetCellFromString\(Integer, Integer, TRichString, Integer\)](SetCellFromString.md#texcelfilesetcellfromstringinteger-integer-trichstring-integer)\.
To enter a HTML formatted string, use [SetCellFromHtml\(Integer, Integer, string, Integer\)](SetCellFromHtml.md#texcelfilesetcellfromhtmlinteger-integer-string-integer)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetCellValue(const row: Integer; const col: Integer; const value: <a href="../TRichString/index.md">TRichString</a>; const XF: Integer = -1); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row, 1 based\.|
|const|**col**|Integer|Column, 1 based\.|
|const|**value**|[TRichString](../TRichString/index.md)|Value to set\.|
|const|**XF**|Integer|**Optional**: Default value is -1<br /><br />Format to Set\. You normally get this number with [AddFormat](AddFormat.md) function\. Use \-1 \(the default\) to keep format unchanged\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.SetCellValue\(Integer, Integer, Double, Integer\)
Sets the value on a cell to a number\.


## Remarks

This method will enter the datatype of the object you pass to it\. For example, if you set value="1" the string "1" will be entered on the cell\. To convert a string to the best representation \(on this case a number\), use [SetCellFromString\(Integer, Integer, TRichString, Integer\)](SetCellFromString.md#texcelfilesetcellfromstringinteger-integer-trichstring-integer)\.
To enter a HTML formatted string, use [SetCellFromHtml\(Integer, Integer, string, Integer\)](SetCellFromHtml.md#texcelfilesetcellfromhtmlinteger-integer-string-integer)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetCellValue(const row: Integer; const col: Integer; const value: Double; const XF: Integer = -1); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row, 1 based\.|
|const|**col**|Integer|Column, 1 based\.|
|const|**value**|Double|Value to set\.|
|const|**XF**|Integer|**Optional**: Default value is -1<br /><br />Format to Set\. You normally get this number with [AddFormat](AddFormat.md) function\. Use \-1 \(the default\) to keep format unchanged\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.SetCellValue\(Integer, Integer, TDateTime, Integer\)
Sets the value on a cell to a datetime\.


## Remarks

This method will enter the datatype of the object you pass to it\. For example, if you set value="1" the string "1" will be entered on the cell\. To convert a string to the best representation \(on this case a number\), use [SetCellFromString\(Integer, Integer, TRichString, Integer\)](SetCellFromString.md#texcelfilesetcellfromstringinteger-integer-trichstring-integer)\.
To enter a HTML formatted string, use [SetCellFromHtml\(Integer, Integer, string, Integer\)](SetCellFromHtml.md#texcelfilesetcellfromhtmlinteger-integer-string-integer)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetCellValue(const row: Integer; const col: Integer; const value: TDateTime; const XF: Integer = -1); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row, 1 based\.|
|const|**col**|Integer|Column, 1 based\.|
|const|**value**|TDateTime|Value to set\.|
|const|**XF**|Integer|**Optional**: Default value is -1<br /><br />Format to Set\. You normally get this number with [AddFormat](AddFormat.md) function\. Use \-1 \(the default\) to keep format unchanged\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.SetCellValue\(Integer, Integer, Integer, Integer\)
Sets the value on a cell to a number\.


## Remarks

This method will enter the datatype of the object you pass to it\. For example, if you set value="1" the string "1" will be entered on the cell\. To convert a string to the best representation \(on this case a number\), use [SetCellFromString\(Integer, Integer, TRichString, Integer\)](SetCellFromString.md#texcelfilesetcellfromstringinteger-integer-trichstring-integer)\.
To enter a HTML formatted string, use [SetCellFromHtml\(Integer, Integer, string, Integer\)](SetCellFromHtml.md#texcelfilesetcellfromhtmlinteger-integer-string-integer)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetCellValue(const row: Integer; const col: Integer; const value: Integer; const XF: Integer = -1); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row, 1 based\.|
|const|**col**|Integer|Column, 1 based\.|
|const|**value**|Integer|Value to set\.|
|const|**XF**|Integer|**Optional**: Default value is -1<br /><br />Format to Set\. You normally get this number with [AddFormat](AddFormat.md) function\. Use \-1 \(the default\) to keep format unchanged\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.SetCellValue\(Integer, Integer, Int64, Integer\)
Sets the value on a cell to a number\.


## Remarks

This method will enter the datatype of the object you pass to it\. For example, if you set value="1" the string "1" will be entered on the cell\. To convert a string to the best representation \(on this case a number\), use [SetCellFromString\(Integer, Integer, TRichString, Integer\)](SetCellFromString.md#texcelfilesetcellfromstringinteger-integer-trichstring-integer)\.
To enter a HTML formatted string, use [SetCellFromHtml\(Integer, Integer, string, Integer\)](SetCellFromHtml.md#texcelfilesetcellfromhtmlinteger-integer-string-integer)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetCellValue(const row: Integer; const col: Integer; const value: Int64; const XF: Integer = -1); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row, 1 based\.|
|const|**col**|Integer|Column, 1 based\.|
|const|**value**|Int64|Value to set\.|
|const|**XF**|Integer|**Optional**: Default value is -1<br /><br />Format to Set\. You normally get this number with [AddFormat](AddFormat.md) function\. Use \-1 \(the default\) to keep format unchanged\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.SetCellValue\(Integer, Integer, Single, Integer\)
Sets the value on a cell to a number\.


## Remarks

This method will enter the datatype of the object you pass to it\. For example, if you set value="1" the string "1" will be entered on the cell\. To convert a string to the best representation \(on this case a number\), use [SetCellFromString\(Integer, Integer, TRichString, Integer\)](SetCellFromString.md#texcelfilesetcellfromstringinteger-integer-trichstring-integer)\.
To enter a HTML formatted string, use [SetCellFromHtml\(Integer, Integer, string, Integer\)](SetCellFromHtml.md#texcelfilesetcellfromhtmlinteger-integer-string-integer)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetCellValue(const row: Integer; const col: Integer; const value: Single; const XF: Integer = -1); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row, 1 based\.|
|const|**col**|Integer|Column, 1 based\.|
|const|**value**|Single|Value to set\.|
|const|**XF**|Integer|**Optional**: Default value is -1<br /><br />Format to Set\. You normally get this number with [AddFormat](AddFormat.md) function\. Use \-1 \(the default\) to keep format unchanged\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.SetCellValue\(Integer, Integer, Integer, TCellValue, Integer\)
Sets the value on a cell\.


## Remarks

This method will enter the datatype of the object you pass to it\. For example, if you set value="1" the string "1" will be entered on the cell\. To convert a string to the best representation \(on this case a number\), use [SetCellFromString\(Integer, Integer, TRichString, Integer\)](SetCellFromString.md#texcelfilesetcellfromstringinteger-integer-trichstring-integer)\.
To enter a HTML formatted string, use [SetCellFromHtml\(Integer, Integer, string, Integer\)](SetCellFromHtml.md#texcelfilesetcellfromhtmlinteger-integer-string-integer)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetCellValue(const sheet: Integer; const row: Integer; const col: Integer; const value: <a href="../TCellValue/index.md">TCellValue</a>; const XF: Integer); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer|Sheet number, 1 based|
|const|**row**|Integer|Row, 1 based\.|
|const|**col**|Integer|Column, 1 based\.|
|const|**value**|[TCellValue](../TCellValue/index.md)|Value to set\.|
|const|**XF**|Integer|Format to Set\. You normally get this number with [AddFormat](AddFormat.md) function\. Use \-1 to keep format unchanged\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.SetCellValue\(Integer, Integer, Integer, string, Integer\)
Sets the value on a cell\.


## Remarks

This method will enter the datatype of the object you pass to it\. For example, if you set value="1" the string "1" will be entered on the cell\. To convert a string to the best representation \(on this case a number\), use [SetCellFromString\(Integer, Integer, TRichString, Integer\)](SetCellFromString.md#texcelfilesetcellfromstringinteger-integer-trichstring-integer)\.
To enter a HTML formatted string, use [SetCellFromHtml\(Integer, Integer, string, Integer\)](SetCellFromHtml.md#texcelfilesetcellfromhtmlinteger-integer-string-integer)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetCellValue(const sheet: Integer; const row: Integer; const col: Integer; const value: string; const XF: Integer); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer|Sheet number, 1 based|
|const|**row**|Integer|Row, 1 based\.|
|const|**col**|Integer|Column, 1 based\.|
|const|**value**|string|Value to set\.|
|const|**XF**|Integer|Format to Set\. You normally get this number with [AddFormat](AddFormat.md) function\. Use \-1 to keep format unchanged\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.SetCellValue\(Integer, Integer, Integer, Double, Integer\)
Sets the value on a cell\.


## Remarks

This method will enter the datatype of the object you pass to it\. For example, if you set value="1" the string "1" will be entered on the cell\. To convert a string to the best representation \(on this case a number\), use [SetCellFromString\(Integer, Integer, TRichString, Integer\)](SetCellFromString.md#texcelfilesetcellfromstringinteger-integer-trichstring-integer)\.
To enter a HTML formatted string, use [SetCellFromHtml\(Integer, Integer, string, Integer\)](SetCellFromHtml.md#texcelfilesetcellfromhtmlinteger-integer-string-integer)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetCellValue(const sheet: Integer; const row: Integer; const col: Integer; const value: Double; const XF: Integer); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer|Sheet number, 1 based|
|const|**row**|Integer|Row, 1 based\.|
|const|**col**|Integer|Column, 1 based\.|
|const|**value**|Double|Value to set\.|
|const|**XF**|Integer|Format to Set\. You normally get this number with [AddFormat](AddFormat.md) function\. Use \-1 to keep format unchanged\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.SetCellValue\(Integer, Integer, Integer, Integer, Integer\)
Sets the value on a cell\.


## Remarks

This method will enter the datatype of the object you pass to it\. For example, if you set value="1" the string "1" will be entered on the cell\. To convert a string to the best representation \(on this case a number\), use [SetCellFromString\(Integer, Integer, TRichString, Integer\)](SetCellFromString.md#texcelfilesetcellfromstringinteger-integer-trichstring-integer)\.
To enter a HTML formatted string, use [SetCellFromHtml\(Integer, Integer, string, Integer\)](SetCellFromHtml.md#texcelfilesetcellfromhtmlinteger-integer-string-integer)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetCellValue(const sheet: Integer; const row: Integer; const col: Integer; const value: Integer; const XF: Integer); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer|Sheet number, 1 based|
|const|**row**|Integer|Row, 1 based\.|
|const|**col**|Integer|Column, 1 based\.|
|const|**value**|Integer|Value to set\.|
|const|**XF**|Integer|Format to Set\. You normally get this number with [AddFormat](AddFormat.md) function\. Use \-1 to keep format unchanged\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

