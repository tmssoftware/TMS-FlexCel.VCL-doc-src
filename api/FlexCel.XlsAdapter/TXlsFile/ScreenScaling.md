---
uid: TXlsFile.ScreenScaling
description: TXlsFile.ScreenScaling
---

# TXlsFile.ScreenScaling Property

This property lets you specify the screen scaling that FlexCel will assume for reading xlsx files in  percent\. \(default is 100 which means 100%%\)\. The values can be between 100 and 500\.


Column widths in xlsx files which don't have a fixed column width set will be different in different screen  resolutions\. So we need to know which resolution to emulate in order to read those files correctly\.
You will probably want to leave this property to the default value of 100, but you can change it if needed\.



For more information, please read [https://www.tmssoftware.com/site/blog.asp?post=311](https://www.tmssoftware.com/site/blog.asp?post=311)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TXlsFile/index.md">TXlsFile</a>.ScreenScaling: Integer</code></pre>

## See also

* [TXlsFile](../TXlsFile/index.md)

