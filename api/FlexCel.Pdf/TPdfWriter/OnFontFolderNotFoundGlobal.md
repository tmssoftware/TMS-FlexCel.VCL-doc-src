---
uid: TPdfWriter.OnFontFolderNotFoundGlobal
description: TPdfWriter.OnFontFolderNotFoundGlobal
---

# TPdfWriter.OnFontFolderNotFoundGlobal Property

This property determines how FlexCel behaves when one of the folders you specify in [GetFontFolder](GetFontFolder.md) doesn't exist\.
**Important:** This event isn't thread safe or guarded by any lock\. You should set it once when your application starts and never modify it\. For changing a particular instance, use [OnFontFolderNotFound](OnFontFolderNotFound.md) instead\. If you aren't sure, use [OnFontFolderNotFound](OnFontFolderNotFound.md)

## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TPdfWriter/index.md">TPdfWriter</a>.OnFontFolderNotFoundGlobal: <a href="../TPdfFontFolderNotFoundAction.md">TPdfFontFolderNotFoundAction</a></code></pre>

## See also

* [TPdfWriter](../TPdfWriter/index.md)

