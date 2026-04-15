---
uid: TXlsFile.GetUsedNamedRanges
description: TXlsFile.GetUsedNamedRanges
---

# TXlsFile\.GetUsedNamedRanges Method

Returns an array of booleans where each value indicates if the name at position "i\-1" is used by any formula, chart, or object in the file\. If the name is in use, it can't be deleted\. Note that the index here is Zero\-based, different from all other Name indexes in FlexCel, because arrays in C\# are always 0\-based\. So UsedRange\[0\] corresponds to GetNamedRange\(1\) and so on\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetUsedNamedRanges: TArray&lt;Boolean>; override;</code></pre>

## See also

* [TXlsFile](../TXlsFile/index.md)

