---
uid: TTokenName.Create
description: TTokenName.Create
---

# TTokenName\.Create Constructor

Creates a new name token\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TTokenName/index.md">TTokenName</a>.Create(const aName: string; const aWorkbookName: string; const aSheet: string);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aName**|string|Named range\.|
|const|**aWorkbookName**|string|Workbook where the name is, if this is an external name\. If the name is in the same file as the reference, this value will be null or empty\.|
|const|**aSheet**|string|Sheet where the name is stored\. Make it null or empty if the name is a global name\.|


## See also

* [TTokenName](../TTokenName/index.md)

