---
uid: TExcelFileErrorActions
description: TExcelFileErrorActions
---

# TExcelFileErrorActions Enumeration

Enumerates what to do on different FlexCel error situations\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|ErrorOnTooManyPageBreaks|0|When true and the number of manual pagebreaks is bigger than the maximum Excel allows, an Exception will be raised\. When false, the page break will be silently omitted\.<br />Note that This exception is raised when saving the file as xls, when you are exporting your report to PDF or images, all page breaks will be used\.<br />|
|ErrorOnFormulaConstantTooLong|1|When true, FlexCel will complain when you try to set a formula that has a string constant bigger than 255 characters\.<br /><br />For example, the formula: '="very long string that has more than 255 characters\.\.\.\." &amp; "other string" '  would raise an Exception, since Excel won't allow it\. Note that you can still use ' =a1 &amp; "other string" ' where the cell A1 has the value: "very long string that has more than 255 characters\.\.\.\."\. this restriction applies only to inline strings\.<br /><br />Note that when this property is false you will still get the error, but only when saving to xls, xlsx or other file formats that don't support longer strings\. \(this error is too important to be ignored\)|
|ErrorOnRowHeightTooBig|2|When true and the row height is bigger than the maximum allowed by Excel, you will get an Exception\.<br />|
|ErrorOnXlsxInvalidName|3|If this is true and the xlsx file contains an invalid name, an exception will be thrown\.<br />|
|ErrorOnXlsxMissingPart|4|If this is true and the xlsx file contains a missing part \(like an image\), an exception will be thrown\.<br />|
|ErrorOnXlsxInvalidFormula|5|If this is true and the file contains an invalid formula, an exception will be thrown\.<br />|
|ErrorOnXlsxInvalidHyperlink|6|If this is true and the file contains invalid hyperlinks, an exception will be thrown\.<br />|


