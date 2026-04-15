---
uid: TValueAxis.Create
description: TValueAxis.Create
---

# TValueAxis\.Create Constructor

## Overloads

* [TValueAxis\.Create](#tvalueaxiscreate)
* [TValueAxis\.Create\(Double, Double, Double, Double, Double, TValueAxisOptionSet, TFlxChartFont, string, Boolean, TAxisLineOptions, TAxisTickOptions, IDataLabel, TChartAxisPos\)](#tvalueaxiscreatedouble-double-double-double-double-tvalueaxisoptionset-tflxchartfont-string-boolean-taxislineoptions-taxistickoptions-idatalabel-tchartaxispos)
* [TValueAxis\.Create\(Double, Double, Double, Double, Double, TValueAxisOptionSet, TFlxChartFont, string, Boolean, TAxisLineOptions, TAxisTickOptions, IDataLabel, TChartAxisPos, Double\)](#tvalueaxiscreatedouble-double-double-double-double-tvalueaxisoptionset-tflxchartfont-string-boolean-taxislineoptions-taxistickoptions-idatalabel-tchartaxispos-double)

# TValueAxis\.Create
Constructs a new TValueAxisOptions instance with all values set to automatic\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TValueAxis/index.md">TValueAxis</a>.Create;</code></pre>

## See also

* [TValueAxis](../TValueAxis/index.md)

# TValueAxis\.Create\(Double, Double, Double, Double, Double, TValueAxisOptionSet, TFlxChartFont, string, Boolean, TAxisLineOptions, TAxisTickOptions, IDataLabel, TChartAxisPos\)
Constructs a new TValueAxisOptions instance\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TValueAxis/index.md">TValueAxis</a>.Create(const aMin: Double; const aMax: Double; const aMajor: Double; const aMinor: Double; const aCrossValue: Double; const aAxisOptions: <a href="../TValueAxisOptions.md">Set of TValueAxisOptions</a>; const aFont: <a href="../TFlxChartFont/index.md">TFlxChartFont</a>; const aNumberFormat: string; const aNumberFormatLinkedToSource: Boolean; const aAxisLineOptions: <a href="../TAxisLineOptions/index.md">TAxisLineOptions</a>; const aTickOptions: <a href="../TAxisTickOptions/index.md">TAxisTickOptions</a>; aCaption: <a href="../IDataLabel/index.md">IDataLabel</a>; const aAxisPos: <a href="../TChartAxisPos.md">TChartAxisPos</a>);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aMin**|Double|See [Min](Min.md)|
|const|**aMax**|Double|See [Max](Max.md)|
|const|**aMajor**|Double|See [Major](Major.md)|
|const|**aMinor**|Double|See [Minor](Minor.md)|
|const|**aCrossValue**|Double|See [CrossValue](CrossValue.md)|
|const|**aAxisOptions**|[Set of TValueAxisOptions](../TValueAxisOptions.md)|See [AxisOptions](AxisOptions.md)|
|const|**aFont**|[TFlxChartFont](../TFlxChartFont/index.md)|See [TBaseAxis.Font](../TBaseAxis/Font.md)\. This parameter will be cloned\.|
|const|**aNumberFormat**|string|See [TBaseAxis.NumberFormat](../TBaseAxis/NumberFormat.md)|
|const|**aNumberFormatLinkedToSource**|Boolean|See [TBaseAxis.NumberFormatLinkedToSource](../TBaseAxis/NumberFormatLinkedToSource.md)|
|const|**aAxisLineOptions**|[TAxisLineOptions](../TAxisLineOptions/index.md)|See [TBaseAxis.AxisLineOptions](../TBaseAxis/AxisLineOptions.md)\. This parameter will be cloned\.|
|const|**aTickOptions**|[TAxisTickOptions](../TAxisTickOptions/index.md)|See [TBaseAxis.TickOptions](../TBaseAxis/TickOptions.md)\. This parameter will be cloned\.|
||**aCaption**|[IDataLabel](../IDataLabel/index.md)|See [TBaseAxis.Caption](../TBaseAxis/Caption.md) This parameter will be cloned\.|
|const|**aAxisPos**|[TChartAxisPos](../TChartAxisPos.md)|See [TBaseAxis.AxisPos](../TBaseAxis/AxisPos.md)|


## See also

* [TValueAxis](../TValueAxis/index.md)

# TValueAxis\.Create\(Double, Double, Double, Double, Double, TValueAxisOptionSet, TFlxChartFont, string, Boolean, TAxisLineOptions, TAxisTickOptions, IDataLabel, TChartAxisPos, Double\)
Constructs a new TValueAxisOptions instance\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TValueAxis/index.md">TValueAxis</a>.Create(const aMin: Double; const aMax: Double; const aMajor: Double; const aMinor: Double; const aCrossValue: Double; const aAxisOptions: <a href="../TValueAxisOptions.md">Set of TValueAxisOptions</a>; const aFont: <a href="../TFlxChartFont/index.md">TFlxChartFont</a>; const aNumberFormat: string; const aNumberFormatLinkedToSource: Boolean; const aAxisLineOptions: <a href="../TAxisLineOptions/index.md">TAxisLineOptions</a>; const aTickOptions: <a href="../TAxisTickOptions/index.md">TAxisTickOptions</a>; aCaption: <a href="../IDataLabel/index.md">IDataLabel</a>; const aAxisPos: <a href="../TChartAxisPos.md">TChartAxisPos</a>; const aLogBase: Double);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aMin**|Double|See [Min](Min.md)|
|const|**aMax**|Double|See [Max](Max.md)|
|const|**aMajor**|Double|See [Major](Major.md)|
|const|**aMinor**|Double|See [Minor](Minor.md)|
|const|**aCrossValue**|Double|See [CrossValue](CrossValue.md)|
|const|**aAxisOptions**|[Set of TValueAxisOptions](../TValueAxisOptions.md)|See [AxisOptions](AxisOptions.md)|
|const|**aFont**|[TFlxChartFont](../TFlxChartFont/index.md)|See [TBaseAxis.Font](../TBaseAxis/Font.md)\. This parameter will be cloned\.|
|const|**aNumberFormat**|string|See [TBaseAxis.NumberFormat](../TBaseAxis/NumberFormat.md)|
|const|**aNumberFormatLinkedToSource**|Boolean|See [TBaseAxis.NumberFormatLinkedToSource](../TBaseAxis/NumberFormatLinkedToSource.md)|
|const|**aAxisLineOptions**|[TAxisLineOptions](../TAxisLineOptions/index.md)|See [TBaseAxis.AxisLineOptions](../TBaseAxis/AxisLineOptions.md)\. This parameter will be cloned\.|
|const|**aTickOptions**|[TAxisTickOptions](../TAxisTickOptions/index.md)|See [TBaseAxis.TickOptions](../TBaseAxis/TickOptions.md)\. This parameter will be cloned\.|
||**aCaption**|[IDataLabel](../IDataLabel/index.md)|See [TBaseAxis.Caption](../TBaseAxis/Caption.md) This parameter will be cloned\.|
|const|**aAxisPos**|[TChartAxisPos](../TChartAxisPos.md)|See [TBaseAxis.AxisPos](../TBaseAxis/AxisPos.md)|
|const|**aLogBase**|Double|See [TBaseAxis.LogBase](../TBaseAxis/LogBase.md)|


## See also

* [TValueAxis](../TValueAxis/index.md)

