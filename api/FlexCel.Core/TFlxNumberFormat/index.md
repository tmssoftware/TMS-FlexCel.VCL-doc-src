---
uid: TFlxNumberFormat
description: TFlxNumberFormat
---

# TFlxNumberFormat Record

Static class to convert cells to formatted strings\. It uses format strings from Excel, that are different to those on \.net, so we have to try to reconcile the diffs\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TFlxNumberFormat = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[FormatValue](FormatValue.md)|**Overloaded<br />**  [FormatValue\(TCellValue, string, TCoreExcelFile\)](FormatValue.md#tflxnumberformatformatvaluetcellvalue-string-tcoreexcelfile)<br />  [FormatValue\(TCellValue, string, TUIColor, TCoreExcelFile\)](FormatValue.md#tflxnumberformatformatvaluetcellvalue-string-tuicolor-tcoreexcelfile)<br />  [FormatValue\(TCellValue, string, TUIColor, TCoreExcelFile, Boolean\)](FormatValue.md#tflxnumberformatformatvaluetcellvalue-string-tuicolor-tcoreexcelfile-boolean)<br />  [FormatValue\(TCellValue, string, TUIColor, TCoreExcelFile, Boolean, Boolean\)](FormatValue.md#tflxnumberformatformatvaluetcellvalue-string-tuicolor-tcoreexcelfile-boolean-boolean)<br />  [FormatValue\(TCellValue, string, TUIColor, TCoreExcelFile, Boolean, Boolean, TAdaptativeFormats\)](FormatValue.md#tflxnumberformatformatvaluetcellvalue-string-tuicolor-tcoreexcelfile-boolean-boolean-tadaptativeformats)<br />  [FormatValue\(TCellValue, string, TUIColor, TCoreExcelFile, Boolean, Boolean, Integer, TAdaptativeFormats\)](FormatValue.md#tflxnumberformatformatvaluetcellvalue-string-tuicolor-tcoreexcelfile-boolean-boolean-integer-tadaptativeformats)<br />|
|[HasDateOrTime](HasDateOrTime.md)|Returns true if the format string has a date or a time\.<br />|
|[HasDate](HasDate.md)|Returns true if the format string has a date\.<br />|
|[HasTime](HasTime.md)|Returns true if the format string has a time\.<br />|
|[PercentCount](PercentCount.md)|Returns the number of %% sign in a cell\. Each %% in the format string multiplies the value by 100, so 0\.1 formatted as "0%%" will display as 10%% and formatted as 0%%%% will display as 1000%%%%\.<br />|


## Properties

|Name|Description|
|---|---|
|[RegionalDateString](RegionalDateString.md)|Returns the string used on a standard date on the current locale|
|[RegionalDate&#8203;Time&#8203;String](RegionalDateTimeString.md)|Returns the string used on a standard date and time on the current locale|


## Events

|Name|Description|
|---|---|
|[CultureCreating](CultureCreating.md)|Fires before a culture is created\. Read [Localized Month Names](xref:LocalizedMonthNames) for more information on how to use it\.<br />Note that this event is static and it applies to the whole app\.<br />|


