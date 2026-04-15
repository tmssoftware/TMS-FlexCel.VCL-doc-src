---
uid: TXlsFile.GetStringFromCell
description: TXlsFile.GetStringFromCell
---

# TXlsFile\.GetStringFromCell Method

This method will return a rich string that is formatted similar to the way Excel shows it\.
For example, if you have "1\.0" on a cell, and the cell is formatted as exponential, this method will return "1\.0e\+1" It might also change the color depending on the value and format\. \(for example, red for negative numbers\) Conditional formats are not applied, you need to call [TExcelFile.ConditionallyModifyFormat\(TFlxFormat, Integer, Integer, Boolean, IDrawingConditionalFormat\)](../../FlexCel.Core/TExcelFile/ConditionallyModifyFormat.md#texcelfileconditionallymodifyformattflxformat-integer-integer-boolean-idrawingconditionalformat) to the cell style for that\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetStringFromCell(const sheet: Integer; const row: Integer; const col: Integer; var XF: Integer; var aColor: <a href="../../FlexCel.Core/TUIColor/index.md">TUIColor</a>; const ignorePrintErrors: Boolean): <a href="../../FlexCel.Core/TRichString/index.md">TRichString</a>; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer|Sheet where the cell is \(1 based\)\.|
|const|**row**|Integer|Cell Row \(1 based\)\.|
|const|**col**|Integer|Cell Column \(1 based\)|
|var|**XF**|Integer|The resulting XF for the cell\.|
|var|**aColor**|[TUIColor](../../FlexCel.Core/TUIColor/index.md)|Resulting color of the string\. If for example you define red for negative numbers, and the result is red, this will be returned on aColor\. If there is not color info on the format, it will remain unchanged\.|
|const|**ignorePrintErrors**|Boolean|If true, the string for an error like \#DIV/0 will always by \#DIV/0 instead of using the value of [TExcelFile.PrintErrors](../../FlexCel.Core/TExcelFile/PrintErrors.md)\. Set it to true when the value is not for printing it\.|


## Returns

A rich string with the cell value\.

## See also

* [TXlsFile](../TXlsFile/index.md)

