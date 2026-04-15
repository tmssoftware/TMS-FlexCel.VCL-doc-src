---
uid: TPaperDimensions
description: TPaperDimensions
---

# TPaperDimensions Record

Dimensions of an Excel paper

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TPaperDimensions = record;</code></pre>

## Fields

|Name|Description|
|---|---|
|[PaperName](PaperName.md)|Paper Name\.<br />|
|[Width](Width.md)|Paper width in inches/100|
|[Height](Height.md)|Paper height in inches/100|


## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create\(TPaperSize\)](Create.md#tpaperdimensionscreatetpapersize)<br />  [Create\(string, Double, Double\)](Create.md#tpaperdimensionscreatestring-double-double)<br />|
|[mm](mm.md)|Converts millimeters to inches/100|
|[in100](in100.md)|Converts inches/100 to millimeters|
|[IsNull](IsNull.md)|Returns true if the record doesn't have a defined value\.<br />|
|[HasValue](HasValue.md)|Returns true if the record has a defined value\. This is the inverse of [IsNull](IsNull.md)|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


## Properties

|Name|Description|
|---|---|
|[SizeInPoints](SizeInPoints.md)|The size in points \(inches/72\)|


