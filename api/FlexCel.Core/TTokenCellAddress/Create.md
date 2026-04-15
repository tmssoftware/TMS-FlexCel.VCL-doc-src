---
uid: TTokenCellAddress.Create
description: TTokenCellAddress.Create
---

# TTokenCellAddress\.Create Constructor

Creates a new Cell address token\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TTokenCellAddress/index.md">TTokenCellAddress</a>.Create(const aExternalBookName: string; const aAddress: <a href="../TCellAddress/index.md">TCellAddress</a>);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aExternalBookName**|string|File where the reference points to, when this is a reference to other file\. Empty or null if the reference is to the same file\.|
|const|**aAddress**|[TCellAddress](../TCellAddress/index.md)|Cell where this token will point to\.|


## See also

* [TTokenCellAddress](../TTokenCellAddress/index.md)

