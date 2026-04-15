---
uid: TFlexCelReport.SetUserFormat
description: TFlexCelReport.SetUserFormat
---

# TFlexCelReport\.SetUserFormat Method

Adds a new user defined format to be used with the report\.
For information on how to create the user format function, see [TFlexCelUserFormat](../TFlexCelUserFormat/index.md)

## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelReport/index.md">TFlexCelReport</a>.SetUserFormat(const name: string; const formatImplementation: <a href="../TFlexCelUserFormat/index.md">TFlexCelUserFormat</a>);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**name**|string|Name that the format will have on the report\. Case insensitive\.|
|const|**formatImplementation**|[TFlexCelUserFormat](../TFlexCelUserFormat/index.md)|An implementation of the user format\.|


## Examples

You can define a format "MFMT" on the following way:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  myFormatImpl := TMyUserFormat.Create;  </span><span style="color:#008000;--shiki-dark:#6A9955">//The MyUserFormat class implements an user defined format.</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //Note that we don't have to free myFormatImpl, it will be freed by the report once it is over.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  flexCelReport.SetUserFormat(</span><span style="color:#A31515;--shiki-dark:#CE9178">'MFMT'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, myFormatImpl);  </span><span style="color:#008000;--shiki-dark:#6A9955">//The name used in Excel will be =MFMT().</span></span>
<span class="line"></span></code></pre>

Then, if you define the format in the config sheet, you can use it inside \<\#format cell> tags\.
Note that the name is case insensitive, so both "MFMT" and "mfmt" refer to the same format\.


## See also

* [TFlexCelReport](../TFlexCelReport/index.md)

