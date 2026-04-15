---
uid: TFlexCelReport.SetUserFunction
description: TFlexCelReport.SetUserFunction
---

# TFlexCelReport\.SetUserFunction Method

Adds a new user defined function to be used with the report\.
The User function object is managed by the report, so you don't have to free it once you used this method to add it to the report\.
For information on how to create the user function, see [TFlexCelUserFunction](../TFlexCelUserFunction/index.md)

## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelReport/index.md">TFlexCelReport</a>.SetUserFunction(const name: string; const functionImplementation: <a href="../TFlexCelUserFunction/index.md">TFlexCelUserFunction</a>);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**name**|string|Name that the function will have on the report\. Case insensitive\.|
|const|**functionImplementation**|[TFlexCelUserFunction](../TFlexCelUserFunction/index.md)|An implementation of the user function\.|


## Examples

You can define a function "MF" on the following way:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  myFuncImpl := TMyUserFunction.Create;  </span><span style="color:#008000;--shiki-dark:#6A9955">//The MyUserFunction class implements an user defined function.</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //Note that we don't have to free myFuncImpl, it will be freed by the report once it is over.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  flexCelReport.SetUserFunction(</span><span style="color:#A31515;--shiki-dark:#CE9178">'MF'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, myFuncImpl);  </span><span style="color:#008000;--shiki-dark:#6A9955">//The name used in Excel will be =MF().</span></span>
<span class="line"></span></code></pre>

Then, if you write \<\#MF\(param1, param2\.\.\. paramn\)> on a cell, the function will be called and the result shown\.
Note that the name is case insensitive, so both "MF" and "mf" refer to the same function\.


## See also

* [TFlexCelReport](../TFlexCelReport/index.md)

