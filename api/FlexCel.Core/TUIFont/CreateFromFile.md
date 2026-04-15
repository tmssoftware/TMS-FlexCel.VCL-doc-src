---
uid: TUIFont.CreateFromFile
description: TUIFont.CreateFromFile
---

# TUIFont\.CreateFromFile Method

Creates a font from a font file\. **IMPORTANT NOTE: When using GDI\+ \(default in Windows\), this method will create a FontCollection that can never be disposed until the application exits\.**
When using GDI\+, try not to use this method, or make sure that it is called only a couple of times since the memory for the loaded font won't be released\. On the other hand, calling this method multiple times with the same font is ok, FlexCel will cache the font and not create multiple instances\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TUIFont/index.md">TUIFont</a>.CreateFromFile(const aFontFilename: string; const aSize: Double; const aFontStyle: <a href="../TUIFontStyle.md">Set of TUIFontStyle</a>; const aFontIndex: Integer): <a href="../TUIFont/index.md">TUIFont</a>; static;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aFontFilename**|string|Filename of the file containing the ttf font data\.|
|const|**aSize**|Double|Size in points of the font\.|
|const|**aFontStyle**|[Set of TUIFontStyle](../TUIFontStyle.md)|Style of the font \(italic, bold, etc\)|
|const|**aFontIndex**|Integer|Index of the font|


## See also

* [TUIFont](../TUIFont/index.md)

