---
uid: TChartErrorBars.Create
description: TChartErrorBars.Create
---

# TChartErrorBars\.Create Constructor

Creates a new TChartErrorBars instance\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TChartErrorBars/index.md">TChartErrorBars</a>.Create(const aDirection: <a href="../TChartErrorBarDirection.md">TChartErrorBarDirection</a>; const aBarType: <a href="../TChartErrorBarBarType.md">TChartErrorBarBarType</a>; const aErrorType: <a href="../TChartErrorBarErrorType.md">TChartErrorBarErrorType</a>; const aIsTShaped: Boolean; const aNumValue: Double; aLineOptions: <a href="../IChartLineOptions/index.md">IChartLineOptions</a>; const aCustomDefPlus: string; const aCustomValuesPlus: <a href="../TCellValue/index.md">TArray&lt;TCellValue></a>; const aCustomDefMinus: string; const aCustomValuesMinus: <a href="../TCellValue/index.md">TArray&lt;TCellValue></a>);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aDirection**|[TChartErrorBar&#8203;Direction](../TChartErrorBarDirection.md)|Direction of the error bars\.|
|const|**aBarType**|[TChartErrorBar&#8203;BarType](../TChartErrorBarBarType.md)|Positive or negative error bars\.|
|const|**aErrorType**|[TChartErrorBar&#8203;Error&#8203;Type](../TChartErrorBarErrorType.md)|Type of error bar\.|
|const|**aIsTShaped**|Boolean|If true, the error bar has a top line like a T\.|
|const|**aNumValue**|Double|Numeric value of the error\. The meaning of this depends in the ErrorType\.|
||**aLineOptions**|[IChartLineOptions](../IChartLineOptions/index.md)|Line options for the error bars, color, line width, etc\. If null, standard options will be used\.|
|const|**aCustomDefPlus**|string|Definition for the custom error bars in the plus direction\. If the error is not custom this will be null\.|
|const|**aCustomValuesPlus**|[TArray\<TCellValue>](../TCellValue/index.md)|Values for the custom error bars in the plus direction\. If the error is not custom this will be null\.|
|const|**aCustomDefMinus**|string|Definition for the custom error bars in the minus direction\. If the error is not custom this will be null\.|
|const|**aCustomValuesMinus**|[TArray\<TCellValue>](../TCellValue/index.md)|Values for the custom error bars in the minus direction\. If the error is not custom this will be null\.|


## See also

* [TChartErrorBars](../TChartErrorBars/index.md)

