---
uid: TDrawingValue
description: TDrawingValue
---

# TDrawingValue Record

Represents a value inside a cell\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TDrawingValue = record;</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create\(TCellValue\)](Create.md#tdrawingvaluecreatetcellvalue)<br />  [Create\(TDrawingRichString\)](Create.md#tdrawingvaluecreatetdrawingrichstring)<br />  [Create\(string\)](Create.md#tdrawingvaluecreatestring)<br />  [Create\(TRichString\)](Create.md#tdrawingvaluecreatetrichstring)<br />|


## Operators

|Name|Description|
|---|---|
|[Implicit Conversion](op_Implicit.md)|**Overloaded<br />**  [Implicit conversion from TCellValue to TDrawingValue](op_Implicit.md#implicit-conversion-from-tcellvalue-to-tdrawingvalue)<br />  [Implicit conversion from TDrawingRichString to TDrawingValue](op_Implicit.md#implicit-conversion-from-tdrawingrichstring-to-tdrawingvalue)<br />|


## Properties

|Name|Description|
|---|---|
|[DrawingValueType](DrawingValueType.md)|Type of value in this object\.<br />|
|[IsDrawingRichString](IsDrawingRichString.md)|Returns true if the object contains a TDrawingRich&#8203;String\.&#8203;<br />|
|[IsCellValue](IsCellValue.md)|Returns true if the object contains a TCellValue\.<br />|
|[AsCellValue](AsCellValue.md)|Cell value if the object contains a TCellValue\. Will raise an exception if it doesn't\.<br />|
|[AsDrawingRichString](AsDrawingRichString.md)|Drawing RichString if the object contains a TDrawingRichString\. Will raise an exception if it doesn't\.<br />|


