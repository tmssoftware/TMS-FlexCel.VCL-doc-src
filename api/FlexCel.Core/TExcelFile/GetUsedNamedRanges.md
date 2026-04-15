---
uid: TExcelFile.GetUsedNamedRanges
description: TExcelFile.GetUsedNamedRanges
---

# TExcelFile\.GetUsedNamedRanges Method

Returns an array of booleans where each value indicates if the name at position "i\-1" is used by any formula, chart, or object in the file\. If the name is in use, it can't be deleted\. Note that the index here is Zero\-based, different from all other Name indexes in FlexCel, because arrays in C\# are always 0\-based\. So UsedRange\[0\] corresponds to GetNamedRange\(1\) and so on\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetUsedNamedRanges: TArray&lt;Boolean>; virtual; abstract;</code></pre>

## See also

* [TExcelFile](../TExcelFile/index.md)

