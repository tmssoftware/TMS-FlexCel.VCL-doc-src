---
uid: TFlexCelReport.SetValue
description: TFlexCelReport.SetValue
---

# TFlexCelReport\.SetValue Method

Sets a variable for the report\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelReport/index.md">TFlexCelReport</a>.SetValue(const name: string; const value: <a href="../TReportValue/index.md">TReportValue</a>);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**name**|string|Name of the variable to set\. Case insensitive\.|
|const|**value**|[TReportValue](../TReportValue/index.md)|Value of the variable\.|


## Examples

You can define a variable "CurrentDate" on the following way:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  flexCelReport.SetValue(</span><span style="color:#A31515;--shiki-dark:#CE9178">'CurrentDate'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, Now);</span></span>
<span class="line"></span></code></pre>

Then, if you write \<\#CurrentDate> on a cell, the date will be shown\.
Note that the name is case insensitive, so both "CURRENTDATE" and "currentdate" refer to the same variable\.


## See also

* [TFlexCelReport](../TFlexCelReport/index.md)

