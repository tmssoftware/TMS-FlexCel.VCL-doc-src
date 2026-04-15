---
uid: TPdfDestination
description: TPdfDestination
---

# TPdfDestination Record

Represents a destination inside a PDF document\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">TPdfDestination = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create\(Integer\)](Create.md#tpdfdestinationcreateinteger)<br />  [Create\(Integer, TZoomOptions\)](Create.md#tpdfdestinationcreateinteger-tzoomoptions)<br />  [Create\(Integer, Double, Double, Double\)](Create.md#tpdfdestinationcreateinteger-double-double-double)<br />|
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
|[PageNumber](PageNumber.md)|Page where the destination will point to\. \(1 based\)|
|[ZoomOptions](ZoomOptions.md)|Zoom options for this destination\.<br />|
|[X](X.md)|X offset of the page in points from the left\. A negative number means keep the default\.<br />This value is only used if ZoomOptions is Zoom\.<br />|
|[Y](Y.md)|Y offset of the page in points from the top\. A negative number means keep the default\.<br />This value is only used if ZoomOptions is Zoom\.<br />|
|[Zoom](Zoom.md)|Zoom to show at the destination\. A negative or 0 number means keep the default\.<br />This value is only used if ZoomOptions is Zoom\.<br />|


