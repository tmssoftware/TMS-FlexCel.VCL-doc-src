---
uid: TFlxNumberFormat.FormatValue
description: TFlxNumberFormat.FormatValue
---

# TFlxNumberFormat\.FormatValue Method

## Overloads

* [TFlxNumberFormat\.FormatValue\(TCellValue, string, TCoreExcelFile\)](#tflxnumberformatformatvaluetcellvalue-string-tcoreexcelfile)
* [TFlxNumberFormat\.FormatValue\(TCellValue, string, TUIColor, TCoreExcelFile\)](#tflxnumberformatformatvaluetcellvalue-string-tuicolor-tcoreexcelfile)
* [TFlxNumberFormat\.FormatValue\(TCellValue, string, TUIColor, TCoreExcelFile, Boolean\)](#tflxnumberformatformatvaluetcellvalue-string-tuicolor-tcoreexcelfile-boolean)
* [TFlxNumberFormat\.FormatValue\(TCellValue, string, TUIColor, TCoreExcelFile, Boolean, Boolean\)](#tflxnumberformatformatvaluetcellvalue-string-tuicolor-tcoreexcelfile-boolean-boolean)
* [TFlxNumberFormat\.FormatValue\(TCellValue, string, TUIColor, TCoreExcelFile, Boolean, Boolean, TAdaptativeFormats\)](#tflxnumberformatformatvaluetcellvalue-string-tuicolor-tcoreexcelfile-boolean-boolean-tadaptativeformats)
* [TFlxNumberFormat\.FormatValue\(TCellValue, string, TUIColor, TCoreExcelFile, Boolean, Boolean, Integer, TAdaptativeFormats\)](#tflxnumberformatformatvaluetcellvalue-string-tuicolor-tcoreexcelfile-boolean-boolean-integer-tadaptativeformats)

# TFlxNumberFormat\.FormatValue\(TCellValue, string, TCoreExcelFile\)
Formats a value as it would be shown by Excel\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TFlxNumberFormat/index.md">TFlxNumberFormat</a>.FormatValue(const Value: <a href="../TCellValue/index.md">TCellValue</a>; const Format: string; const Workbook: TCoreExcelFile): string; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**Value**|[TCellValue](../TCellValue/index.md)|Value to format\.|
|const|**Format**|string|Cell Format\. \(For example, "yyyy\-mm\-dd" for a date format, or "\#\.00" for a numeric 2 decimal format\)<br />This format string is the same you use in Excel under "Custom" format when formatting a cell \(for English versions of Excel\), and it is documented in the Excel documentation\. You can use APIMate to find out which string to use from a format you entered in Excel\.<br />|
|const|**Workbook**|TCoreExcelFile|Workbook with the cell\. If null, no color information will be returned and the base date fill be assumed to be 1900 \(windows\) and not 1904 \(macs\)\.|


## See also

* [TFlxNumberFormat](../TFlxNumberFormat/index.md)

# TFlxNumberFormat\.FormatValue\(TCellValue, string, TUIColor, TCoreExcelFile\)
Formats a value as it would be shown by Excel\.
Conditional formats are not applied, you need to call [TExcelFile.ConditionallyModifyFormat\(TFlxFormat, Integer, Integer, Boolean, IDrawingConditionalFormat\)](../TExcelFile/ConditionallyModifyFormat.md#texcelfileconditionallymodifyformattflxformat-integer-integer-boolean-idrawingconditionalformat) to the cell style for that\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TFlxNumberFormat/index.md">TFlxNumberFormat</a>.FormatValue(const Value: <a href="../TCellValue/index.md">TCellValue</a>; const Format: string; var aColor: <a href="../TUIColor/index.md">TUIColor</a>; const Workbook: TCoreExcelFile): <a href="../TRichString/index.md">TRichString</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**Value**|[TCellValue](../TCellValue/index.md)|Value to format\.|
|const|**Format**|string|Cell Format\. \(For example, "yyyy\-mm\-dd" for a date format, or "\#\.00" for a numeric 2 decimal format\)<br />This format string is the same you use in Excel under "Custom" format when formatting a cell \(for English versions of Excel\), and it is documented in the Excel documentation\. You can use APIMate to find out which string to use from a format you entered in Excel\.<br />|
|var|**aColor**|[TUIColor](../TUIColor/index.md)|Final color of the text\. \(Depending on the format, color might change\. I\.e\. Red for negatives\)|
|const|**Workbook**|TCoreExcelFile|Workbook with the cell\. If null, no color information will be returned and the base date fill be assumed to be 1900 \(windows\) and not 1904 \(macs\)\.|


## Returns

Formatted string\.

## See also

* [TFlxNumberFormat](../TFlxNumberFormat/index.md)

# TFlxNumberFormat\.FormatValue\(TCellValue, string, TUIColor, TCoreExcelFile, Boolean\)
Formats a value as it would be shown by Excel\.
Conditional formats are not applied, you need to call [TExcelFile.ConditionallyModifyFormat\(TFlxFormat, Integer, Integer, Boolean, IDrawingConditionalFormat\)](../TExcelFile/ConditionallyModifyFormat.md#texcelfileconditionallymodifyformattflxformat-integer-integer-boolean-idrawingconditionalformat) to the cell style for that\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TFlxNumberFormat/index.md">TFlxNumberFormat</a>.FormatValue(const Value: <a href="../TCellValue/index.md">TCellValue</a>; const Format: string; var aColor: <a href="../TUIColor/index.md">TUIColor</a>; const Workbook: TCoreExcelFile; const ignorePrintErrors: Boolean): <a href="../TRichString/index.md">TRichString</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**Value**|[TCellValue](../TCellValue/index.md)|Value to format\.|
|const|**Format**|string|Cell Format\. \(For example, "yyyy\-mm\-dd" for a date format, or "\#\.00" for a numeric 2 decimal format\)<br />This format string is the same you use in Excel under "Custom" format when formatting a cell \(for English versions of Excel\), and it is documented in the Excel documentation\. You can use APIMate to find out which string to use from a format you entered in Excel\.<br />|
|var|**aColor**|[TUIColor](../TUIColor/index.md)|Final color of the text\. \(Depending on the format, color might change\. I\.e\. Red for negatives\)|
|const|**Workbook**|TCoreExcelFile|Workbook with the cell\. If null, no color information will be returned and the base date fill be assumed to be 1900 \(windows\) and not 1904 \(macs\)\.|
|const|**ignorePrintErrors**|Boolean|If true, the string for an error like \#DIV/0 will always by \#DIV/0 instead of using the value of ExcelFile\.PrintErrors\. Set it to true when the value is not for printing it\.|


## Returns

Formatted string\.

## See also

* [TFlxNumberFormat](../TFlxNumberFormat/index.md)

# TFlxNumberFormat\.FormatValue\(TCellValue, string, TUIColor, TCoreExcelFile, Boolean, Boolean\)
Formats a value as it would be shown by Excel\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TFlxNumberFormat/index.md">TFlxNumberFormat</a>.FormatValue(const Value: <a href="../TCellValue/index.md">TCellValue</a>; const Format: string; var aColor: <a href="../TUIColor/index.md">TUIColor</a>; const Workbook: TCoreExcelFile; out HasDate: Boolean; out HasTime: Boolean): <a href="../TRichString/index.md">TRichString</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**Value**|[TCellValue](../TCellValue/index.md)|Value to format\.|
|const|**Format**|string|Cell Format\. \(For example, "yyyy\-mm\-dd" for a date format, or "\#\.00" for a numeric 2 decimal format\)<br />This format string is the same you use in Excel under "Custom" format when formatting a cell \(for English versions of Excel\), and it is documented in the Excel documentation\. You can use APIMate to find out which string to use from a format you entered in Excel\.<br />|
|var|**aColor**|[TUIColor](../TUIColor/index.md)|Final color of the text\. \(Depending on the format, color might change\. I\.e\. Red for negatives\)|
|const|**Workbook**|TCoreExcelFile|Workbook with the cell\. If null, no color information will be returned and the base date fill be assumed to be 1900 \(windows\) and not 1904 \(macs\)\.|
|out|**HasDate**|Boolean|Returns if the format contains a date\.|
|out|**HasTime**|Boolean|Returns if the format contains a time\.|


## Returns

Formatted string\.

## See also

* [TFlxNumberFormat](../TFlxNumberFormat/index.md)

# TFlxNumberFormat\.FormatValue\(TCellValue, string, TUIColor, TCoreExcelFile, Boolean, Boolean, TAdaptativeFormats\)
Formats a value as it would be shown by Excel\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TFlxNumberFormat/index.md">TFlxNumberFormat</a>.FormatValue(const Value: <a href="../TCellValue/index.md">TCellValue</a>; const Format: string; var aColor: <a href="../TUIColor/index.md">TUIColor</a>; const Workbook: TCoreExcelFile; out HasDate: Boolean; out HasTime: Boolean; out AdaptativeFormats: <a href="../TAdaptativeFormats/index.md">TAdaptativeFormats</a>): <a href="../TRichString/index.md">TRichString</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**Value**|[TCellValue](../TCellValue/index.md)|Value to format\.|
|const|**Format**|string|Cell Format\. \(For example, "yyyy\-mm\-dd" for a date format, or "\#\.00" for a numeric 2 decimal format\)<br />This format string is the same you use in Excel under "Custom" format when formatting a cell \(for English versions of Excel\), and it is documented in the Excel documentation\. You can use APIMate to find out which string to use from a format you entered in Excel\.<br />|
|var|**aColor**|[TUIColor](../TUIColor/index.md)|Final color of the text\. \(Depending on the format, color might change\. I\.e\. Red for negatives\)|
|const|**Workbook**|TCoreExcelFile|Workbook with the cell\. If null, no color information will be returned and the base date fill be assumed to be 1900 \(windows\) and not 1904 \(macs\)\.|
|out|**HasDate**|Boolean|Returns if the format contains a date\.|
|out|**HasTime**|Boolean|Returns if the format contains a time\.|
|out|**AdaptativeFormats**|[TAdaptativeFormats](../TAdaptativeFormats/index.md)|Returns micro\-justification information needed to adapt the text better to a cell\. Null if there are no adaptative formats\.|


## Returns

Formatted string\.

## See also

* [TFlxNumberFormat](../TFlxNumberFormat/index.md)

# TFlxNumberFormat\.FormatValue\(TCellValue, string, TUIColor, TCoreExcelFile, Boolean, Boolean, Integer, TAdaptativeFormats\)
Formats a value as it would be shown by Excel\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TFlxNumberFormat/index.md">TFlxNumberFormat</a>.FormatValue(const Value: <a href="../TCellValue/index.md">TCellValue</a>; const Format: string; var aColor: <a href="../TUIColor/index.md">TUIColor</a>; const Workbook: TCoreExcelFile; out HasDate: Boolean; out HasTime: Boolean; out PercentCount: Integer; out AdaptativeFormats: <a href="../TAdaptativeFormats/index.md">TAdaptativeFormats</a>): <a href="../TRichString/index.md">TRichString</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**Value**|[TCellValue](../TCellValue/index.md)|Value to format\.|
|const|**Format**|string|Cell Format\. \(For example, "yyyy\-mm\-dd" for a date format, or "\#\.00" for a numeric 2 decimal format\)<br />This format string is the same you use in Excel under "Custom" format when formatting a cell \(for English versions of Excel\), and it is documented in the Excel documentation\. You can use APIMate to find out which string to use from a format you entered in Excel\.<br />|
|var|**aColor**|[TUIColor](../TUIColor/index.md)|Final color of the text\. \(Depending on the format, color might change\. I\.e\. Red for negatives\)|
|const|**Workbook**|TCoreExcelFile|Workbook with the cell\. If null, no color information will be returned and the base date fill be assumed to be 1900 \(windows\) and not 1904 \(macs\)\.|
|out|**HasDate**|Boolean|Returns if the format contains a date\.|
|out|**HasTime**|Boolean|Returns if the format contains a time\.|
|out|**PercentCount**|Integer|Returns the number of %% signs applied to the format\. Each %% in the format string multiplies the number by 100, so 0\.1 displays as "10%%" or "1000%%%%"|
|out|**AdaptativeFormats**|[TAdaptativeFormats](../TAdaptativeFormats/index.md)|Returns micro\-justification information needed to adapt the text better to a cell\. Null if there are no adaptative formats\.|


## Returns

Formatted string\.

## See also

* [TFlxNumberFormat](../TFlxNumberFormat/index.md)

