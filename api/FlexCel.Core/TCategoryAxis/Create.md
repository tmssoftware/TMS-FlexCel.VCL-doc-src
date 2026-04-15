---
uid: TCategoryAxis.Create
description: TCategoryAxis.Create
---

# TCategoryAxis\.Create Constructor

## Overloads

* [TCategoryAxis\.Create](#tcategoryaxiscreate)
* [TCategoryAxis\.Create\(Integer, Integer, Integer, TDateUnits, Integer, TDateUnits, TDateUnits, Integer, TCategoryAxisOptionSet, TFlxChartFont, string, Boolean, TAxisLineOptions, TAxisTickOptions, TAxisRangeOptions, IDataLabel, TChartAxisPos, Double\)](#tcategoryaxiscreateinteger-integer-integer-tdateunits-integer-tdateunits-tdateunits-integer-tcategoryaxisoptionset-tflxchartfont-string-boolean-taxislineoptions-taxistickoptions-taxisrangeoptions-idatalabel-tchartaxispos-double)
* [TCategoryAxis\.Create\(Integer, Integer, Integer, TDateUnits, Integer, TDateUnits, TDateUnits, Integer, TCategoryAxisOptionSet, TFlxChartFont, string, Boolean, TAxisLineOptions, TAxisTickOptions, TAxisRangeOptions, IDataLabel, TChartAxisPos, Double, Double\)](#tcategoryaxiscreateinteger-integer-integer-tdateunits-integer-tdateunits-tdateunits-integer-tcategoryaxisoptionset-tflxchartfont-string-boolean-taxislineoptions-taxistickoptions-taxisrangeoptions-idatalabel-tchartaxispos-double-double)

# TCategoryAxis\.Create
Constructs a new TCategoryAxisOption instance with all values set to automatic\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TCategoryAxis/index.md">TCategoryAxis</a>.Create;</code></pre>

## See also

* [TCategoryAxis](../TCategoryAxis/index.md)

# TCategoryAxis\.Create\(Integer, Integer, Integer, TDateUnits, Integer, TDateUnits, TDateUnits, Integer, TCategoryAxisOptionSet, TFlxChartFont, string, Boolean, TAxisLineOptions, TAxisTickOptions, TAxisRangeOptions, IDataLabel, TChartAxisPos, Double\)
Constructs a new TCategoryAxisOptions instance\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TCategoryAxis/index.md">TCategoryAxis</a>.Create(const aMin: Integer; const aMax: Integer; const aMajorValue: Integer; const aMajorUnit: <a href="../TDateUnits.md">TDateUnits</a>; const aMinorValue: Integer; const aMinorUnit: <a href="../TDateUnits.md">TDateUnits</a>; const aBaseUnit: <a href="../TDateUnits.md">TDateUnits</a>; const aCrossValue: Integer; const aAxisOptions: <a href="../TCategoryAxisOptions.md">Set of TCategoryAxisOptions</a>; const aFont: <a href="../TFlxChartFont/index.md">TFlxChartFont</a>; const aNumberFormat: string; const aNumberFormatLinkedToSource: Boolean; const aAxisLineOptions: <a href="../TAxisLineOptions/index.md">TAxisLineOptions</a>; const aTickOptions: <a href="../TAxisTickOptions/index.md">TAxisTickOptions</a>; const aRangeOptions: <a href="../TAxisRangeOptions/index.md">TAxisRangeOptions</a>; aCaption: <a href="../IDataLabel/index.md">IDataLabel</a>; const aAxisPos: <a href="../TChartAxisPos.md">TChartAxisPos</a>; const aLabelOffset: Double);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aMin**|Integer|See [Min](Min.md)|
|const|**aMax**|Integer|See [Max](Max.md)|
|const|**aMajorValue**|Integer|See [MajorValue](MajorValue.md)|
|const|**aMajorUnit**|[TDateUnits](../TDateUnits.md)|See [MajorUnit](MajorUnit.md)|
|const|**aMinorValue**|Integer|See [MinorValue](MinorValue.md)|
|const|**aMinorUnit**|[TDateUnits](../TDateUnits.md)|See [MinorUnit](MinorUnit.md)|
|const|**aBaseUnit**|[TDateUnits](../TDateUnits.md)|See [BaseUnit](BaseUnit.md)|
|const|**aCrossValue**|Integer|See [CrossValue](CrossValue.md)|
|const|**aAxisOptions**|[Set of TCategoryAxisOptions](../TCategoryAxisOptions.md)|See [AxisOptions](AxisOptions.md)|
|const|**aFont**|[TFlxChartFont](../TFlxChartFont/index.md)|See [TBaseAxis.Font](../TBaseAxis/Font.md)|
|const|**aNumberFormat**|string|See [TBaseAxis.NumberFormat](../TBaseAxis/NumberFormat.md)|
|const|**aNumberFormatLinkedToSource**|Boolean|See [TBaseAxis.NumberFormatLinkedToSource](../TBaseAxis/NumberFormatLinkedToSource.md)|
|const|**aAxisLineOptions**|[TAxisLineOptions](../TAxisLineOptions/index.md)|See [TBaseAxis.AxisLineOptions](../TBaseAxis/AxisLineOptions.md)\. This parameter will be cloned\.|
|const|**aTickOptions**|[TAxisTickOptions](../TAxisTickOptions/index.md)|See [TBaseAxis.TickOptions](../TBaseAxis/TickOptions.md) This parameter will be cloned\.|
|const|**aRangeOptions**|[TAxisRangeOptions](../TAxisRangeOptions/index.md)|See [RangeOptions](RangeOptions.md) This parameter will be cloned\.|
||**aCaption**|[IDataLabel](../IDataLabel/index.md)|See [TBaseAxis.Caption](../TBaseAxis/Caption.md) This parameter will be cloned\.|
|const|**aAxisPos**|[TChartAxisPos](../TChartAxisPos.md)|See [TBaseAxis.AxisPos](../TBaseAxis/AxisPos.md)|
|const|**aLabelOffset**|Double|See [LabelOffset](LabelOffset.md)|


## See also

* [TCategoryAxis](../TCategoryAxis/index.md)

# TCategoryAxis\.Create\(Integer, Integer, Integer, TDateUnits, Integer, TDateUnits, TDateUnits, Integer, TCategoryAxisOptionSet, TFlxChartFont, string, Boolean, TAxisLineOptions, TAxisTickOptions, TAxisRangeOptions, IDataLabel, TChartAxisPos, Double, Double\)
Constructs a new TCategoryAxisOptions instance\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TCategoryAxis/index.md">TCategoryAxis</a>.Create(const aMin: Integer; const aMax: Integer; const aMajorValue: Integer; const aMajorUnit: <a href="../TDateUnits.md">TDateUnits</a>; const aMinorValue: Integer; const aMinorUnit: <a href="../TDateUnits.md">TDateUnits</a>; const aBaseUnit: <a href="../TDateUnits.md">TDateUnits</a>; const aCrossValue: Integer; const aAxisOptions: <a href="../TCategoryAxisOptions.md">Set of TCategoryAxisOptions</a>; const aFont: <a href="../TFlxChartFont/index.md">TFlxChartFont</a>; const aNumberFormat: string; const aNumberFormatLinkedToSource: Boolean; const aAxisLineOptions: <a href="../TAxisLineOptions/index.md">TAxisLineOptions</a>; const aTickOptions: <a href="../TAxisTickOptions/index.md">TAxisTickOptions</a>; const aRangeOptions: <a href="../TAxisRangeOptions/index.md">TAxisRangeOptions</a>; aCaption: <a href="../IDataLabel/index.md">IDataLabel</a>; const aAxisPos: <a href="../TChartAxisPos.md">TChartAxisPos</a>; const aLabelOffset: Double; const aLogBase: Double);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aMin**|Integer|See [Min](Min.md)|
|const|**aMax**|Integer|See [Max](Max.md)|
|const|**aMajorValue**|Integer|See [MajorValue](MajorValue.md)|
|const|**aMajorUnit**|[TDateUnits](../TDateUnits.md)|See [MajorUnit](MajorUnit.md)|
|const|**aMinorValue**|Integer|See [MinorValue](MinorValue.md)|
|const|**aMinorUnit**|[TDateUnits](../TDateUnits.md)|See [MinorUnit](MinorUnit.md)|
|const|**aBaseUnit**|[TDateUnits](../TDateUnits.md)|See [BaseUnit](BaseUnit.md)|
|const|**aCrossValue**|Integer|See [CrossValue](CrossValue.md)|
|const|**aAxisOptions**|[Set of TCategoryAxisOptions](../TCategoryAxisOptions.md)|See [AxisOptions](AxisOptions.md)|
|const|**aFont**|[TFlxChartFont](../TFlxChartFont/index.md)|See [TBaseAxis.Font](../TBaseAxis/Font.md)|
|const|**aNumberFormat**|string|See [TBaseAxis.NumberFormat](../TBaseAxis/NumberFormat.md)|
|const|**aNumberFormatLinkedToSource**|Boolean|See [TBaseAxis.NumberFormatLinkedToSource](../TBaseAxis/NumberFormatLinkedToSource.md)|
|const|**aAxisLineOptions**|[TAxisLineOptions](../TAxisLineOptions/index.md)|See [TBaseAxis.AxisLineOptions](../TBaseAxis/AxisLineOptions.md)\. This parameter will be cloned\.|
|const|**aTickOptions**|[TAxisTickOptions](../TAxisTickOptions/index.md)|See [TBaseAxis.TickOptions](../TBaseAxis/TickOptions.md) This parameter will be cloned\.|
|const|**aRangeOptions**|[TAxisRangeOptions](../TAxisRangeOptions/index.md)|See [RangeOptions](RangeOptions.md) This parameter will be cloned\.|
||**aCaption**|[IDataLabel](../IDataLabel/index.md)|See [TBaseAxis.Caption](../TBaseAxis/Caption.md) This parameter will be cloned\.|
|const|**aAxisPos**|[TChartAxisPos](../TChartAxisPos.md)|See [TBaseAxis.AxisPos](../TBaseAxis/AxisPos.md)|
|const|**aLabelOffset**|Double|See [LabelOffset](LabelOffset.md)|
|const|**aLogBase**|Double|See [TBaseAxis.LogBase](../TBaseAxis/LogBase.md)|


## See also

* [TCategoryAxis](../TCategoryAxis/index.md)

