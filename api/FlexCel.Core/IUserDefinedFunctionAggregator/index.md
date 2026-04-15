---
uid: IUserDefinedFunctionAggregator
description: IUserDefinedFunctionAggregator
---

# IUserDefinedFunctionAggregator Interface

This interface is passed to methods that will process the workbook\. Implement your own custom decendant to create new functions\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">IUserDefinedFunctionAggregator = interface(IInterface);</code></pre>

## Methods

|Name|Description|
|---|---|
|[Process](Process.md)|Implement this method to do something for every value in the range\.<br />Note: You can abort the processing \(for example if there is an error\) by returning false in this function, and the error value in the "error" parameter\.<br />But, Excel normally doesn't behave this way\. Excel will normally first check all values to see if there is an error, and only then if no cell was a \#Err\! value, do other checks \(for example negative parameters\)\. So, for this to be 100%% like Excel, you always need to return true in  this function, and check for other errors only after all values have been processed\. If you don't care about returning the exact error message Excel returns, you can return  the error directly here while you are processing the values and speed up things \(since other values won't be processed after you know the first error\)\.<br />|


