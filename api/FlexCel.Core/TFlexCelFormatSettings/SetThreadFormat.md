---
uid: TFlexCelFormatSettings.SetThreadFormat
description: TFlexCelFormatSettings.SetThreadFormat
---

# TFlexCelFormatSettings\.SetThreadFormat Method

Sets the format for the current thread\. This has the maximum priority, if you set a thread format, it will always be used in the thread\. If you don't set it, then the Global formats will be used\. If you don't set either a Global format, then Format Settings will be used\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class procedure <a href="../TFlexCelFormatSettings/index.md">TFlexCelFormatSettings</a>.SetThreadFormat(const aLocaleName: string; const aFmt: TFormatSettings);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aLocaleName**|string|The name of the locale\. This is used for sorting\.<br />|
|const|**aFmt**|TFormatSettings|The new format settings to be applied to the thread\.<br />|


## See also

* [TFlexCelFormatSettings](../TFlexCelFormatSettings/index.md)

