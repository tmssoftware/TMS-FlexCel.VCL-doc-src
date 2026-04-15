---
uid: TReportValue
description: TReportValue
---

# TReportValue Record

Contains the values you can enter inside a report\. This might be a TCellValue, an array of CellValues or an image as a ByteArray\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">TReportValue = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Empty](Empty.md)|Returns an empty TReportValue|
|[Create](Create.md)|Creates a new TReportValue from a TCellValue\. Note: You normally won't need to call this method, since conversion is automatic\.<br />|
|[HasValue](HasValue.md)|Returns true if the record isn't empty\.<br />|
|[HasCellValue](HasCellValue.md)|Returns true if the record contains a TCellValue, meaning that the Value property is valid\.<br />|


## Operators

|Name|Description|
|---|---|
|[Implicit Conversion](op_Implicit.md)|**Overloaded<br />**  [Implicit conversion from TCellValue to TReportValue](op_Implicit.md#implicit-conversion-from-tcellvalue-to-treportvalue)<br />  [Implicit conversion from string to TReportValue](op_Implicit.md#implicit-conversion-from-string-to-treportvalue)<br />  [Implicit conversion from TRichString to TReportValue](op_Implicit.md#implicit-conversion-from-trichstring-to-treportvalue)<br />  [Implicit conversion from Double to TReportValue](op_Implicit.md#implicit-conversion-from-double-to-treportvalue)<br />  [Implicit conversion from Extended to TReportValue](op_Implicit.md#implicit-conversion-from-extended-to-treportvalue)<br />  [Implicit conversion from TDateTime to TReportValue](op_Implicit.md#implicit-conversion-from-tdatetime-to-treportvalue)<br />  [Implicit conversion from Integer to TReportValue](op_Implicit.md#implicit-conversion-from-integer-to-treportvalue)<br />  [Implicit conversion from Int64 to TReportValue](op_Implicit.md#implicit-conversion-from-int64-to-treportvalue)<br />  [Implicit conversion from Currency to TReportValue](op_Implicit.md#implicit-conversion-from-currency-to-treportvalue)<br />  [Implicit conversion from Boolean to TReportValue](op_Implicit.md#implicit-conversion-from-boolean-to-treportvalue)<br />  [Implicit conversion from TCellValueArray to TReportValue](op_Implicit.md#implicit-conversion-from-tcellvaluearray-to-treportvalue)<br />  [Implicit conversion from TFlxFormulaErrorValue to TReportValue](op_Implicit.md#implicit-conversion-from-tflxformulaerrorvalue-to-treportvalue)<br />  [Implicit conversion from TBytes to TReportValue](op_Implicit.md#implicit-conversion-from-tbytes-to-treportvalue)<br />|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


## Properties

|Name|Description|
|---|---|
|[Value](Value.md)|Value for the report, when it contains a TCellValue\. If the record doesn't contain a TCellValue, this property will be TCellValue\.Empty|
|[ValueArray](ValueArray.md)|Array of TCellValue inside this record\. If this record doesn't contain an array of TCellValue, this property will be nil|
|[ValueBytes](ValueBytes.md)|Value of this record as a byte array, used to represent images\. If this record doesn't contain a byte array, this property will be null\.<br />|


