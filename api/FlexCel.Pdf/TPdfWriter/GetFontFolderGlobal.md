---
uid: TPdfWriter.GetFontFolderGlobal
description: TPdfWriter.GetFontFolderGlobal
---

# TPdfWriter.GetFontFolderGlobal Event

Use this event if you want to provide your own font folder for the full application\.
Note that if you assign [GetFontFolder](GetFontFolder.md) for a particular object instance it will be used instead\.
**Important:** This event isn't thread safe or guarded by any lock\. You should set it once when your application starts and never modify it\. For changing a particular instance, use [GetFontFolder](GetFontFolder.md) instead\. If you aren't sure, use [GetFontFolder](GetFontFolder.md)
Note that you can return more than one path by separating them with semicolons\. For example if you return "c:\\fonts1;c:\\fonts2" FlexCel will search both in fonts1 and fonts2\. Every folder you specify here must have at least one font\.


FlexCel will search in the folders you return here, and in \*\*all subfolders\*\* of that folders for ttf files\.



In Android, we use a "@folder" syntax to refer to assets\. So for example to specify that the fonts are in the "fonts" folder asset, return "@fonts" here\. If the fonts are in a normal folder, just return the folder\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TPdfWriter/index.md">TPdfWriter</a>.GetFontFolderGlobal: TGetFontFolderEventHandler</code></pre>

## See also

* [TPdfWriter](../TPdfWriter/index.md)

