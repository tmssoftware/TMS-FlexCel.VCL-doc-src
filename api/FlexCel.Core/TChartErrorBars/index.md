---
uid: TChartErrorBars
description: TChartErrorBars
---

# TChartErrorBars Class

Information about an Error Bar\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TChartErrorBars = class(TFlexCelObject);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new TChartErrorBars instance\.<br />|


## Methods

|Name|Description|
|---|---|
|[CalcErrorValues](CalcErrorValues.md)|This method will calculate the Values array based on the error types and series values\.<br />|
|[Clone](Clone.md)|Returns a deep copy of this object\.<br />|
|[ReleaseLineOptions](ReleaseLineOptions.md)|This function will return the lineoptions and pass ownership of them\. After calling it, LineOptions will be nil\.<br />|


## Properties

|Name|Description|
|---|---|
|[Direction](Direction.md)|Direction of the error bars\.<br />|
|[BarType](BarType.md)|Positive or negative error bars\.<br />|
|[ErrorType](ErrorType.md)|Type of error bar\.<br />|
|[IsTShaped](IsTShaped.md)|If true, the error bar has a top line like a T\.<br />|
|[NumValue](NumValue.md)|Numeric value of the error\. The meaning of this depends in the ErrorType\.<br />|
|[LineOptions](LineOptions.md)|Line options for the error bars, color, line width, etc\. If null, standard options will be used\.<br />|
|[ValuesPlus](ValuesPlus.md)|Values of the positive error bars\. This will be null unless you explicitly calculate them by calling CalcErrorValues\.<br />|
|[ValuesMinus](ValuesMinus.md)|Values of the negative error bars\. This will be null unless you explicitly calculate them by calling CalcErrorValues\.<br />|
|[StdAvg](StdAvg.md)|Returns the average of the series\. This value is calculated by CalcErrorValues, and only is the error type is StdErr or StdDev\.<br />It is used when the error type is StdDev as error bars must be drawn from the average\.<br />|
|[CustomDefPlus](CustomDefPlus.md)|Returns the formula text used for a custom error bar for the \+ values\.<br />|
|[CustomDefMinus](CustomDefMinus.md)|Returns the formula text used for a custom error bar for the \- values\.<br />|
|[CustomValuesPlus](CustomValuesPlus.md)|Returns the formula values used for a custom error bar for the \+ values\.<br />|
|[CustomValuesMinus](CustomValuesMinus.md)|Returns the formula values used for a custom error bar for the \- values\.<br />|


