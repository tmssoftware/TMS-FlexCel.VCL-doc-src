---
uid: TExcelFile.GetStringFromCell
description: TExcelFile.GetStringFromCell
---

# TExcelFile\.GetStringFromCell Method

## Overloads

* [TExcelFile\.GetStringFromCell\(string\)](#texcelfilegetstringfromcellstring)
* [TExcelFile\.GetStringFromCell\(Integer, Integer\)](#texcelfilegetstringfromcellinteger-integer)
* [TExcelFile\.GetStringFromCell\(Integer, Integer, Boolean\)](#texcelfilegetstringfromcellinteger-integer-boolean)
* [TExcelFile\.GetStringFromCell\(Integer, Integer, Integer, TUIColor\)](#texcelfilegetstringfromcellinteger-integer-integer-tuicolor)
* [TExcelFile\.GetStringFromCell\(Integer, Integer, Integer, Integer, TUIColor\)](#texcelfilegetstringfromcellinteger-integer-integer-integer-tuicolor)
* [TExcelFile\.GetStringFromCell\(Integer, Integer, Integer, Integer, TUIColor, Boolean\)](#texcelfilegetstringfromcellinteger-integer-integer-integer-tuicolor-boolean)

# TExcelFile\.GetStringFromCell\(string\)
This method will return a rich string that is formatted similar to the way Excel shows it\.
For example, if you have "1\.0" on a cell, and the cell is formatted as exponential, this method will return "1\.0e\+1" It might also change the color depending on the value and format\. \(for example, red for negative numbers\)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetStringFromCell(const cellRef: string): <a href="../TRichString/index.md">TRichString</a>; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**cellRef**|string|Cell reference in A1 notation\. Something like A3, or Sheet1\!$B$5 can be used here\.|


## Returns

A rich string with the cell value\.

## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.GetStringFromCell\(Integer, Integer\)
This method will return a rich string that is formatted similar to the way Excel shows it\.
For example, if you have "1\.0" on a cell, and the cell is formatted as exponential, this method will return "1\.0e\+1" It might also change the color depending on the value and format\. \(for example, red for negative numbers\) Conditional formats are not applied, you need to call [ConditionallyModifyFormat\(TFlxFormat, Integer, Integer, Boolean, IDrawingConditionalFormat\)](ConditionallyModifyFormat.md#texcelfileconditionallymodifyformattflxformat-integer-integer-boolean-idrawingconditionalformat) to the cell style for that\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetStringFromCell(const row: Integer; const col: Integer): <a href="../TRichString/index.md">TRichString</a>; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Cell Row \(1 based\)\.|
|const|**col**|Integer|Cell Column \(1 based\)|


## Returns

A rich string with the cell value\.

## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.GetStringFromCell\(Integer, Integer, Boolean\)
This method will return a rich string that is formatted similar to the way Excel shows it\.
For example, if you have "1\.0" on a cell, and the cell is formatted as exponential, this method will return "1\.0e\+1" It might also change the color depending on the value and format\. \(for example, red for negative numbers\) Conditional formats are not applied, you need to call [ConditionallyModifyFormat\(TFlxFormat, Integer, Integer, Boolean, IDrawingConditionalFormat\)](ConditionallyModifyFormat.md#texcelfileconditionallymodifyformattflxformat-integer-integer-boolean-idrawingconditionalformat) to the cell style for that\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetStringFromCell(const row: Integer; const col: Integer; const ignorePrintErrors: Boolean): <a href="../TRichString/index.md">TRichString</a>; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Cell Row \(1 based\)\.|
|const|**col**|Integer|Cell Column \(1 based\)|
|const|**ignorePrintErrors**|Boolean|If true, the string for an error like \#DIV/0 will always by \#DIV/0 instead of using the value of [PrintErrors](PrintErrors.md)\. Set it to true when the value is not for printing it\.|


## Returns

A rich string with the cell value\.

## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.GetStringFromCell\(Integer, Integer, Integer, TUIColor\)
This method will return a rich string that is formatted similar to the way Excel shows it\.
For example, if you have "1\.0" on a cell, and the cell is formatted as exponential, this method will return "1\.0e\+1" It might also change the color depending on the value and format\. \(for example, red for negative numbers\) Conditional formats are not applied, you need to call [ConditionallyModifyFormat\(TFlxFormat, Integer, Integer, Boolean, IDrawingConditionalFormat\)](ConditionallyModifyFormat.md#texcelfileconditionallymodifyformattflxformat-integer-integer-boolean-idrawingconditionalformat) to the cell style for that\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetStringFromCell(const row: Integer; const col: Integer; var XF: Integer; var aColor: <a href="../TUIColor/index.md">TUIColor</a>): <a href="../TRichString/index.md">TRichString</a>; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Cell Row \(1 based\)\.|
|const|**col**|Integer|Cell Column \(1 based\)|
|var|**XF**|Integer|The resulting XF for the cell\.|
|var|**aColor**|[TUIColor](../TUIColor/index.md)|Resulting color of the string\. If for example you define red for negative numbers, and the result is red, this will be returned on aColor\. If there is not color info on the format, it will remain unchanged\.|


## Returns

A rich string with the cell value\.

## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.GetStringFromCell\(Integer, Integer, Integer, Integer, TUIColor\)
This method will return a rich string that is formatted similar to the way Excel shows it\.
For example, if you have "1\.0" on a cell, and the cell is formatted as exponential, this method will return "1\.0e\+1" It might also change the color depending on the value and format\. \(for example, red for negative numbers\) Conditional formats are not applied, you need to call [ConditionallyModifyFormat\(TFlxFormat, Integer, Integer, Boolean, IDrawingConditionalFormat\)](ConditionallyModifyFormat.md#texcelfileconditionallymodifyformattflxformat-integer-integer-boolean-idrawingconditionalformat) to the cell style for that\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetStringFromCell(const sheet: Integer; const row: Integer; const col: Integer; var XF: Integer; var aColor: <a href="../TUIColor/index.md">TUIColor</a>): <a href="../TRichString/index.md">TRichString</a>; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer|Sheet where the cell is \(1 based\)\.|
|const|**row**|Integer|Cell Row \(1 based\)\.|
|const|**col**|Integer|Cell Column \(1 based\)|
|var|**XF**|Integer|The resulting XF for the cell\.|
|var|**aColor**|[TUIColor](../TUIColor/index.md)|Resulting color of the string\. If for example you define red for negative numbers, and the result is red, this will be returned on aColor\. If there is not color info on the format, it will remain unchanged\.|


## Returns

A rich string with the cell value\.

## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.GetStringFromCell\(Integer, Integer, Integer, Integer, TUIColor, Boolean\)
This method will return a rich string that is formatted similar to the way Excel shows it\.
For example, if you have "1\.0" on a cell, and the cell is formatted as exponential, this method will return "1\.0e\+1" It might also change the color depending on the value and format\. \(for example, red for negative numbers\) Conditional formats are not applied, you need to call [ConditionallyModifyFormat\(TFlxFormat, Integer, Integer, Boolean, IDrawingConditionalFormat\)](ConditionallyModifyFormat.md#texcelfileconditionallymodifyformattflxformat-integer-integer-boolean-idrawingconditionalformat) to the cell style for that\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetStringFromCell(const sheet: Integer; const row: Integer; const col: Integer; var XF: Integer; var aColor: <a href="../TUIColor/index.md">TUIColor</a>; const ignorePrintErrors: Boolean): <a href="../TRichString/index.md">TRichString</a>; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer|Sheet where the cell is \(1 based\)\.|
|const|**row**|Integer|Cell Row \(1 based\)\.|
|const|**col**|Integer|Cell Column \(1 based\)|
|var|**XF**|Integer|The resulting XF for the cell\.|
|var|**aColor**|[TUIColor](../TUIColor/index.md)|Resulting color of the string\. If for example you define red for negative numbers, and the result is red, this will be returned on aColor\. If there is not color info on the format, it will remain unchanged\.|
|const|**ignorePrintErrors**|Boolean|If true, the string for an error like \#DIV/0 will always by \#DIV/0 instead of using the value of [PrintErrors](PrintErrors.md)\. Set it to true when the value is not for printing it\.|


## Returns

A rich string with the cell value\.

## See also

* [TExcelFile](../TExcelFile/index.md)

