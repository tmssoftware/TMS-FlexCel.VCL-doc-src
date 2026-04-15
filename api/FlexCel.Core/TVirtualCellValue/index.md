---
uid: TVirtualCellValue
description: TVirtualCellValue
---

# TVirtualCellValue Record

Represents a cell, including the row, column and sheet where it was read\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TVirtualCellValue = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new CellValue instance\.<br />|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


## Properties

|Name|Description|
|---|---|
|[Sheet](Sheet.md)|Sheet where the cell was read\. \(1 based\)|
|[Row](Row.md)|Row where the cell was read\. \(1 based\)|
|[Col](Col.md)|Column where the cell was read\. \(1 based\)|
|[Value](Value.md)|Value of the cell\. The possible objects here are the same as the returned by [TExcelFile.&#8203;Get&#8203;Cell&#8203;Value\(&#8203;&#8203;Integer, Integer, Integer\)](../TExcelFile/GetCellValue.md#texcelfilegetcellvalueinteger-integer-integer)|
|[XF](XF.md)|Format of the cell\.<br />|


