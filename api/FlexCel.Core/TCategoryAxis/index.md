---
uid: TCategoryAxis
description: TCategoryAxis
---

# TCategoryAxis Class

Information about an Axis of categories\. \(normally the x axis\)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TCategoryAxis = class(<a href="../TBaseAxis/index.md">TBaseAxis</a>);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create](Create.md#tcategoryaxiscreate)<br />  [Create\(Integer, Integer, Integer, TDateUnits, Integer, TDateUnits, TDateUnits, Integer, TCategoryAxisOptionSet, TFlxChartFont, string, Boolean, TAxisLineOptions, TAxisTickOptions, TAxisRangeOptions, IDataLabel, TChartAxisPos, Double\)](Create.md#tcategoryaxiscreateinteger-integer-integer-tdateunits-integer-tdateunits-tdateunits-integer-tcategoryaxisoptionset-tflxchartfont-string-boolean-taxislineoptions-taxistickoptions-taxisrangeoptions-idatalabel-tchartaxispos-double)<br />  [Create\(Integer, Integer, Integer, TDateUnits, Integer, TDateUnits, TDateUnits, Integer, TCategoryAxisOptionSet, TFlxChartFont, string, Boolean, TAxisLineOptions, TAxisTickOptions, TAxisRangeOptions, IDataLabel, TChartAxisPos, Double, Double\)](Create.md#tcategoryaxiscreateinteger-integer-integer-tdateunits-integer-tdateunits-tdateunits-integer-tcategoryaxisoptionset-tflxchartfont-string-boolean-taxislineoptions-taxistickoptions-taxisrangeoptions-idatalabel-tchartaxispos-double-double)<br />|


## Properties

|Name|Description|
|---|---|
|[Min](Min.md)|Minimum value for the axis, when not set to automatic in [AxisOptions](AxisOptions.md)\.<br />|
|[Max](Max.md)|Maximum value for the axis, when not set to automatic in [AxisOptions](AxisOptions.md)\.<br />|
|[MajorValue](MajorValue.md)|Value for the major unit, when not set to automatic in [AxisOptions](AxisOptions.md)\.<br />|
|[MajorUnit](MajorUnit.md)|Units for the major unit, when not set to automatic in [AxisOptions](AxisOptions.md)\.<br />|
|[MinorValue](MinorValue.md)|Value for the minor unit, when not set to automatic in [AxisOptions](AxisOptions.md)\.<br />|
|[MinorUnit](MinorUnit.md)|Units for the minor unit, when not set to automatic in [AxisOptions](AxisOptions.md)\.<br />|
|[BaseUnit](BaseUnit.md)|Base units for the axis, when not set to automatic in [AxisOptions](AxisOptions.md)\.<br />|
|[CrossValue](CrossValue.md)|Value where the other Axis will cross this one, when not set to automatic in [AxisOptions](AxisOptions.md)\.<br />|
|[LabelOffset](LabelOffset.md)|Distance from the labels to the axis\. Defaults to 100\.<br />|
|[AxisOptions](AxisOptions.md)|Enumerates which of the other options contain valid values or are automatic\.<br />|
|[RangeOptions](RangeOptions.md)|Options for the range of this axis\.<br />|


