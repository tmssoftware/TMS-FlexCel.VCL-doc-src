---
uid: TFormulaValue.TryToDouble
description: TFormulaValue.TryToDouble
---

# TFormulaValue\.TryToDouble Method

Tries to convert this value to a number, and returns true is possible\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TFormulaValue/index.md">TFormulaValue</a>.TryToDouble(out d: Double; const AllowArrays: Boolean = True): Boolean;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|out|**d**|Double|Will contain the value as a number, if the result of this method is true\.<br />|
|const|**AllowArrays**|Boolean|**Optional**: Default value is True<br /><br />|


## Returns

When false, it is not possible to convert the value to a double, and the parameter d is undefined\.


## See also

* [TFormulaValue](../TFormulaValue/index.md)

