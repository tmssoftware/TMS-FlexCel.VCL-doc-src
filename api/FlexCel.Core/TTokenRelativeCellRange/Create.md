---
uid: TTokenRelativeCellRange.Create
description: TTokenRelativeCellRange.Create
---

# TTokenRelativeCellRange\.Create Constructor

Creates a new relative cell range token\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TTokenRelativeCellRange/index.md">TTokenRelativeCellRange</a>.Create(const aExternalBookName: string; const aSheet1: string; const aSheet2: string; const aRowOffset1: Integer; const aColOffset1: Integer; const aRowOffset2: Integer; const aColOffset2: Integer);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aExternalBookName**|string|File where the reference points to, when this is a reference to other file\. Empty or null if the reference is to the same file\.|
|const|**aSheet1**|string|First sheet where the reference points to\. Empty or null if the reference points to the same sheet\.|
|const|**aSheet2**|string|Second where the reference points to\. Empty or null if the reference points to the same sheet\.|
|const|**aRowOffset1**|Integer|First row \(1 based\)\.|
|const|**aColOffset1**|Integer|First column \(1 based\)\.|
|const|**aRowOffset2**|Integer|Last row \(1 based\)\.|
|const|**aColOffset2**|Integer|Last column \(1 based\)\.|


## See also

* [TTokenRelativeCellRange](../TTokenRelativeCellRange/index.md)

