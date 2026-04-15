---
uid: TAddress
description: TAddress
---

# TAddress Record

Used to summarize a range of cells\. This class is for internal use\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TAddress = record;</code></pre>

## Fields

|Name|Description|
|---|---|
|[Xls](Xls.md)|ExcelFile where this Address applies\.<br />|
|[BookName](BookName.md)|Name of the external workbook\. Null if no external book\.<br />|
|[Sheet](Sheet.md)|Sheet index \(1 based\) where the address is\.<br />|
|[Row](Row.md)|Row index \(1 based\) of the address\.<br />|
|[Col](Col.md)|Column index \(1 based\) of the address\.<br />|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


