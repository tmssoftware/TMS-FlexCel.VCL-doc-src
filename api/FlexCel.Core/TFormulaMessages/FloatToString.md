---
uid: TFormulaMessages.FloatToString
description: TFormulaMessages.FloatToString
---

# TFormulaMessages\.FloatToString Method

This is a non\-localized version of FloatToStr It will always use "\." as decimal separator\.
If you are localizing this unit to your language, change this function to be: public string FloatToString\(double Value\) \{ return Value\.ToString\(\); \} And it will use your current locale to get the decimal separator\.
Just remember that if you for example use "," as decimal sep, you should also change fmArrayColSep, fmFunctionSep and all vars with value=","

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TFormulaMessages/index.md">TFormulaMessages</a>.FloatToString(const Value: Double): string; static;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**Value**|Double|Value to convert|


## Returns

String using ALWAYS "\." as decimal separator, regardless of the regional settings

## See also

* [TFormulaMessages](../TFormulaMessages/index.md)

