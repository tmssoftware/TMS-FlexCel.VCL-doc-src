---
uid: TCultureCreatingEventArgs
description: TCultureCreatingEventArgs
---

# TCultureCreatingEventArgs Class

Event when creating a culture\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TCultureCreatingEventArgs = class(TFlexCelObject);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new instance of the event arguments with the specified parameters\.<br />|


## Properties

|Name|Description|
|---|---|
|[LanguageCode](LanguageCode.md)|Language code for the culture we want to create\.<br />|
|[LanguageName](LanguageName.md)|Language name for the culture we want to create\. Note that the value we read from the file is [LanguageCode](LanguageCode.md), this property is only for convenience, but might be empty if we don't know how to map the LanguageCode\.<br />If in doubt, LanguageCode has the actual value in the file\.<br />|
|[Culture](Culture.md)|This is the culture that will be used for the language code\.<br />This property is initialized with the culture FlexCel would set if no event was assigned\.<br />You can change the properties of this Culture or completely replace it by a cached one\.<br />|


