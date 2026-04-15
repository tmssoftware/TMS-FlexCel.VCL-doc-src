---
uid: TCultureCreatingEventArgs.Create
description: TCultureCreatingEventArgs.Create
---

# TCultureCreatingEventArgs\.Create Constructor

Creates a new instance of the event arguments with the specified parameters\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TCultureCreatingEventArgs/index.md">TCultureCreatingEventArgs</a>.Create(const aLanguageCode: Integer; const aLanguageName: string; const aCulture: TFormatSettings);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aLanguageCode**|Integer|Language code for the culture we want to create\.|
|const|**aLanguageName**|string|Language name for the culture we want to create\. Note that the value we read from the file is LanguageCode, this parameter is only for convenience, but might be empty if we don't know how to map the LanguageCode\.|
|const|**aCulture**|TFormatSettings|This is the culture that will be used for the language code\. This property is initialized with the culture FlexCel would set if no event was assigned\. You can change the properties of this Culture or completely replace it by a cached one\.|


## See also

* [TCultureCreatingEventArgs](../TCultureCreatingEventArgs/index.md)

