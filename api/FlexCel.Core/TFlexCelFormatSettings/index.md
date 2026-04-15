---
uid: TFlexCelFormatSettings
description: TFlexCelFormatSettings
---

# TFlexCelFormatSettings Class

This class allows customization of the numeric formats FlexCel uses to display, either globally for all instances or by thread\.


## Remarks

If you don't change anything, by default this class will use Delphi's FormatSettings global variable\. If you use [SetGlobalFormat](SetGlobalFormat.md) then that format will be used instead\. If you use [SetThreadFormat](SetThreadFormat.md) then it will be used instead of the GlobalFormat\. The priority is: ThreadFormat is used if assigned\. If ThreadFormat is not assigned, the GlobalFormat is used\. If GlobalFormat is not assigned, then FormatSettings is used\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TFlexCelFormatSettings = class(TObject);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new TFlexCelFormat&#8203;Settings instance and assigns a TFormatSettings variable to it\.<br />|


## Methods

|Name|Description|
|---|---|
|[Invariant](Invariant.md)|Returns the invariant culture\. This culture always uses "\." as decimal separator\.<br />|
|[Current](Current.md)|Returns the current culture\. If you assigned a Thread Format with [SetThreadFormat](SetThreadFormat.md) then it will be returned\. If you didn't assign a Thread Format, but assigned a Global Format with [SetGlobalFormat](SetGlobalFormat.md) then the Global Format will be returned\. If you didn't assign a thread or global format, then FormatSettings will be returned\.<br />|
|[SetThreadFormat](SetThreadFormat.md)|Sets the format for the current thread\. This has the maximum priority, if you set a thread format, it will always be used in the thread\. If you don't set it, then the Global formats will be used\. If you don't set either a Global format, then Format Settings will be used\.<br />|
|[PushThreadFormat](PushThreadFormat.md)|This method is similar to [SetThreadFormat](SetThreadFormat.md), but it returns the current thread format so you can restore it later with [PopThreadFormat](PopThreadFormat.md)\.<br />|
|[PopThreadFormat](PopThreadFormat.md)|Restores the thread format settings that were set by [PushThreadFormat](PushThreadFormat.md)**Note:** This method only works with formats that were obtained with [PushThreadFormat](PushThreadFormat.md) \. Don't try to use it with different formats\.<br />|
|[SetGlobalFormat](SetGlobalFormat.md)|Sets the format that FlexCel will use on all the threads\. If you set the format for a particular thread with [SetThreadFormat](SetThreadFormat.md) then it will take priority\. If the thread format is not assigned, it will fall back to this\. If you don't assign a global format either, then FormatSettings will be used\.<br />|


