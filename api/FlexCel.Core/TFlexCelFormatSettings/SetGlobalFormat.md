---
uid: TFlexCelFormatSettings.SetGlobalFormat
description: TFlexCelFormatSettings.SetGlobalFormat
---

# TFlexCelFormatSettings\.SetGlobalFormat Method

Sets the format that FlexCel will use on all the threads\. If you set the format for a particular thread with [SetThreadFormat](SetThreadFormat.md) then it will take priority\. If the thread format is not assigned, it will fall back to this\. If you don't assign a global format either, then FormatSettings will be used\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class procedure <a href="../TFlexCelFormatSettings/index.md">TFlexCelFormatSettings</a>.SetGlobalFormat(const aLocaleName: string; const aFmt: TFormatSettings);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aLocaleName**|string|The name of the locale\. This is used for sorting\.<br />|
|const|**aFmt**|TFormatSettings|The new format settings to be applied to all threads\.<br />|


## See also

* [TFlexCelFormatSettings](../TFlexCelFormatSettings/index.md)

