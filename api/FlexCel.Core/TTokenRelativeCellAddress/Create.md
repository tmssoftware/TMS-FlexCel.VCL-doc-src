---
uid: TTokenRelativeCellAddress.Create
description: TTokenRelativeCellAddress.Create
---

# TTokenRelativeCellAddress\.Create Constructor

Creates a new relative cell address token\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TTokenRelativeCellAddress/index.md">TTokenRelativeCellAddress</a>.Create(const aExternalBookName: string; const aSheet: string; const aRowOffset: Integer; const aColOffset: Integer);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aExternalBookName**|string|File where the reference points to, when this is a reference to other file\. Empty or null if the reference is to the same file\.|
|const|**aSheet**|string|Sheet where the reference points to\. Empty or null if the reference points to the same sheet\.|
|const|**aRowOffset**|Integer|The number of rows after or before the current row\. It might be negative\.|
|const|**aColOffset**|Integer|The number of columns after or before the current column\. It might be negative\.|


## See also

* [TTokenRelativeCellAddress](../TTokenRelativeCellAddress/index.md)

