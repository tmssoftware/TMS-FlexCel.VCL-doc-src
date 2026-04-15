---
uid: TFontCreatedEventArgs.Create
description: TFontCreatedEventArgs.Create
---

# TFontCreatedEventArgs\.Create Constructor

Creates a new instance of the event arguments with the specified parameters\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TFontCreatedEventArgs/index.md">TFontCreatedEventArgs</a>.Create(const aSubstitutedFontName: string; const aOriginalFontName: string; const aFontSize: Double; const aFontStyle: <a href="../TUIFontStyle.md">Set of TUIFontStyle</a>);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aSubstitutedFontName**|string|Name of the final font as decided by the operating system\. Note that some operating systems might return the same name as the original font even if they used a substitute font under the hood\.<br />In those platforms we can't know a font has been substituted\.|
|const|**aOriginalFontName**|string|Name of the font we were trying to create\. It might not be the same as the font the operating system gave to us\.|
|const|**aFontSize**|Double|Size in points of the font\.|
|const|**aFontStyle**|[Set of TUIFontStyle](../TUIFontStyle.md)|Style of the font\.|


## See also

* [TFontCreatedEventArgs](../TFontCreatedEventArgs/index.md)

