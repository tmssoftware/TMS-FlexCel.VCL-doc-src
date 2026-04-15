---
uid: TFlexCelReport.SetExpression
description: TFlexCelReport.SetExpression
---

# TFlexCelReport\.SetExpression Method

Sets a user\-defined expression to be used in the report\. Different from [SetValue](SetValue.md) this method will evaluate the \<\#tags> in "value"\. This allows you to provide formula functionality to end users, and to reuse the same report for  different formulas\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelReport/index.md">TFlexCelReport</a>.SetExpression(const name: string; const value: <a href="../TReportValue/index.md">TReportValue</a>);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**name**|string|Name of the expression to set\. Case insensitive\.|
|const|**value**|[TReportValue](../TReportValue/index.md)|Value of the expression\.|


## Examples

You could ask the user for an expression in an edit box, and then before running the report do:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  flexCelReport.SetExpression(</span><span style="color:#A31515;--shiki-dark:#CE9178">'MyExpression'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, EditBox.Text);</span></span>
<span class="line"></span></code></pre>

Then, if you write \<\#MyExpresion> on a cell, the expression will be evaluated and entered into the cell\.
If the user enters "\<\#evaluate\(\<\#Order\.Amount> \* \<\#Order\.Vat>\)>" in the edit box, this formula will be evaluated into the cell\. The user can write any \<\#tag> that could be used in an expression defined directly in the template\.


## See also

* [TFlexCelReport](../TFlexCelReport/index.md)

