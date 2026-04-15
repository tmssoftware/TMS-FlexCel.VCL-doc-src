---
uid: TFontCreatedEventArgs
description: TFontCreatedEventArgs
---

# TFontCreatedEventArgs Class

Arguments passed in FontCreated events\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TFontCreatedEventArgs = class(<a href="../TFontCreationEventArgs/index.md">TFontCreationEventArgs</a>);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new instance of the event arguments with the specified parameters\.<br />|


## Properties

|Name|Description|
|---|---|
|[SubstitutedFontName](SubstitutedFontName.md)|Name of the final font as decided by the operating system\. Note that some operating systems might return the same name as the original font even if they used a substitute font under the hood\.<br />In those platforms we can't know a font has been substituted\.<br />|
|[OriginalFontName](OriginalFontName.md)|Name of the font we were trying to create\. This property is readonly, to change it change [TFontCreation&#8203;Event&#8203;Args.&#8203;Font&#8203;Name](../TFontCreationEventArgs/FontName.md) instead\.<br />|
|[IsModified](IsModified.md)|Returns true if any properties of the class were modified since the class was created\.<br />|


