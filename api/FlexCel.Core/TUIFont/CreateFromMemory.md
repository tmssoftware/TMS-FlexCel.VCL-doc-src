---
uid: TUIFont.CreateFromMemory
description: TUIFont.CreateFromMemory
---

# TUIFont\.CreateFromMemory Method

Creates a font from the font data\. **IMPORTANT NOTE: When using GDI\+ \(default in Windows\), this method will create a FontCollection that can never be disposed until the application exits\.**
When using GDI\+, try not to use this method, or make sure that it is called only a couple of times since the memory for the loaded font won't be released\. On the other hand, calling this method multiple times with the same font is ok, FlexCel will cache the font and not create multiple instances\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TUIFont/index.md">TUIFont</a>.CreateFromMemory(const aFontData: TBytes; const aSize: Double; const aFontStyle: <a href="../TUIFontStyle.md">Set of TUIFontStyle</a>; const aFontIndex: Integer): <a href="../TUIFont/index.md">TUIFont</a>; static;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aFontData**|TBytes|Byte array containing the ttf font data\.|
|const|**aSize**|Double|Size in points of the font\.|
|const|**aFontStyle**|[Set of TUIFontStyle](../TUIFontStyle.md)|Style of the font \(italic, bold, etc\)|
|const|**aFontIndex**|Integer|Index of the font|


## See also

* [TUIFont](../TUIFont/index.md)

