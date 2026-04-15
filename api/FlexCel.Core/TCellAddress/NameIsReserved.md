---
uid: TCellAddress.NameIsReserved
description: TCellAddress.NameIsReserved
---

# TCellAddress\.NameIsReserved Method

Returns true if the string can be a cell reference, like A1 or LVM78, or "R", "C", "TRUE" or "FALSE"\.
If this method returns true, you can't name a sheet or a named range with name\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TCellAddress/index.md">TCellAddress</a>.NameIsReserved(const Name: string): Boolean; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**Name**|string||


## See also

* [TCellAddress](../TCellAddress/index.md)

