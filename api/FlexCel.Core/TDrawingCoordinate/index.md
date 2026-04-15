---
uid: TDrawingCoordinate
description: TDrawingCoordinate
---

# TDrawingCoordinate Record

A coordinate in a drawing\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TDrawingCoordinate = record;</code></pre>

## Constants

|Name|Description|
|---|---|
|[CmToEmu](CmToEmu.md)|Returns how many EMUs in 1 cm\.<br />|
|[InchesToEmu](InchesToEmu.md)|Returns how many EMUs in 1 inch\.<br />|
|[PointsToEmu](PointsToEmu.md)|Returns how many EMUs in 1 point\.<br />|
|[PcToEmu](PcToEmu.md)|Returns how many EMUs in 1 pc\.<br />|
|[PiToEmu](PiToEmu.md)|Returns how many EMUs in 1 pi\.<br />|


## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a coordinate in Emus\. To use other units, use the "From\.\.\." methods of this struct\.<br />|
|[FromCm](FromCm.md)|Creates a drawing coordinate from a measunement in centimeters\.<br />|
|[FromMm](FromMm.md)|Creates a drawing coordinate from a measunement in milimeters\.<br />|
|[FromInches](FromInches.md)|Creates a drawing coordinate from a measurement in inches\.<br />|
|[FromPoints](FromPoints.md)|Creates a drawing coordinate from a measunement in points\. \(1/72 of an inch\)|
|[FromPi](FromPi.md)|Creates a drawing coordinate from a measunement in Pi Excel units\.<br />|
|[Equals](Equals.md)|Returns true if this instance has the same data as the object obj\.<br />|
|[GetHashCode](GetHashCode.md)|Returns the hashcode for this object|
|[ToString](ToString.md)|Returns a string representing the measurement in cm\.<br />|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


## Properties

|Name|Description|
|---|---|
|[Emu](Emu.md)|Value of the coordinate in EMUs \(English Metric Units\)|
|[Cm](Cm.md)|Value of the coordinate in cm|
|[Inches](Inches.md)|Value of the coordinate in inches|
|[Points](Points.md)|Value of the coordinate in points|
|[Pixels](Pixels.md)|Value of the coordinate in pixels|


