---
uid: TFlexCelFormatSettings.PushThreadFormat
description: TFlexCelFormatSettings.PushThreadFormat
---

# TFlexCelFormatSettings\.PushThreadFormat Method

This method is similar to [SetThreadFormat](SetThreadFormat.md), but it returns the current thread format so you can restore it later with [PopThreadFormat](PopThreadFormat.md)\.


## Remarks

This method is supposed to be used as follows:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span>SaveFormat := TFlexCelFormatSettings.PushThreadFormat(NewLocale, NewFormatSettings); try //Run reports, convert to pdf, etc using the NewFormatSettings finally TFlexCelFormatSettings.PopThreadFormat(SaveFormat); end;</span></span>
<span class="line"><span></span></span></code></pre>



## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TFlexCelFormatSettings/index.md">TFlexCelFormatSettings</a>.PushThreadFormat(const aLocaleName: string; const aFmt: TFormatSettings): <a href="../TFlexCelFormatSettings/index.md">TFlexCelFormatSettings</a>;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aLocaleName**|string|The name of the locale\. This is used for sorting\.<br />|
|const|**aFmt**|TFormatSettings|The new format settings to be applied to the thread\.<br />|


## Returns

The format settings that were set to the thread before calling this method\.


## See also

* [TFlexCelFormatSettings](../TFlexCelFormatSettings/index.md)

