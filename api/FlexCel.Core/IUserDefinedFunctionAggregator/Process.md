---
uid: IUserDefinedFunctionAggregator.Process
description: IUserDefinedFunctionAggregator.Process
---

# IUserDefinedFunctionAggregator\.Process Method

Implement this method to do something for every value in the range\.
Note: You can abort the processing \(for example if there is an error\) by returning false in this function, and the error value in the "error" parameter\.
But, Excel normally doesn't behave this way\. Excel will normally first check all values to see if there is an error, and only then if no cell was a \#Err\! value, do other checks \(for example negative parameters\)\. So, for this to be 100%% like Excel, you always need to return true in  this function, and check for other errors only after all values have been processed\. If you don't care about returning the exact error message Excel returns, you can return  the error directly here while you are processing the values and speed up things \(since other values won't be processed after you know the first error\)\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../IUserDefinedFunctionAggregator/index.md">IUserDefinedFunctionAggregator</a>.Process(const value: Double; out error: <a href="../TFlxFormulaErrorValue.md">TFlxFormulaErrorValue</a>): Boolean; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**value**|Double|Value that will be processed\.|
|out|**error**|[TFlxFormulaError&#8203;Value](../TFlxFormulaErrorValue.md)|Return an error here when the method returns false\. If the method returns true, this parameter is undefined\.|


## Returns

False if you want to abort, true to continue\.

## See also

* [IUserDefinedFunctionAggregator](../IUserDefinedFunctionAggregator/index.md)

