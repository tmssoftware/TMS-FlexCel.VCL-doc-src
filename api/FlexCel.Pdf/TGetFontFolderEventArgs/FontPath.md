---
uid: TGetFontFolderEventArgs.FontPath
description: TGetFontFolderEventArgs.FontPath
---

# TGetFontFolderEventArgs.FontPath Property

Return here the font path to the "Fonts" folder where ttf files are located\.

FlexCel will search in the folder you return here, and in \*\*all subfolders\*\* of that folder for ttf files\.


In Android, we use a "@folder" syntax to refer to assets\. So for example to specify that the fonts are in the "fonts" folder asset, return "@fonts" here\. If the fonts are in a normal folder, just return the folder\.



You can return more than one folder here, separating them with semicolons \(;\)\. So you could for example return the string 'c:\\font1folder;c:\\font2folder' and FlexCel will search inside font1folder and font2folder\.



Note: In FlexCel 6 we've changed this name from "FontFolder" to "FontPath" to force a compiler error in FlexCel \.NET\. For Delphi you just need to change the name in your event handlers from "FontFolder" to "FontPath"\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TGetFontFolderEventArgs/index.md">TGetFontFolderEventArgs</a>.FontPath: string</code></pre>

## See also

* [TGetFontFolderEventArgs](../TGetFontFolderEventArgs/index.md)

