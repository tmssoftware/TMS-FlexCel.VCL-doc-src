---
uid: TWorkspace.Recalc
description: TWorkspace.Recalc
---

# TWorkspace\.Recalc Method

Use this method to force a recalculation of all the spreadsheets in the workspace\. This is the same as calling Recalc\(\) in any of the files in the workspace\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TWorkspace/index.md">TWorkspace</a>.Recalc(const forced: Boolean);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**forced**|Boolean|When true this method will perform a recalc in all files\. When false, it will only recalculate the files where there has been a change\.|


## See also

* [TWorkspace](../TWorkspace/index.md)

