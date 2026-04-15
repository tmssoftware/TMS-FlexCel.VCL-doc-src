---
uid: TGetIncludeEventArgs.IncludeData
description: TGetIncludeEventArgs.IncludeData
---

# TGetIncludeEventArgs.IncludeData Property

Here you can return the included file as an array of bytes\.
If you return null, the filename will be used to search for a file on the disk\.
If the including file is a real file \(not an stream\) and FileName is relative, it will be relative to the including file path\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TGetIncludeEventArgs/index.md">TGetIncludeEventArgs</a>.IncludeData: TArray&lt;Byte&gt;</code></pre>

## See also

* [TGetIncludeEventArgs](../TGetIncludeEventArgs/index.md)

