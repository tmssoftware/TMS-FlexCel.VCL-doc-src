---
uid: TCellAddress.DecodeColumn
description: TCellAddress.DecodeColumn
---

# TCellAddress\.DecodeColumn Method

Returns 1 for column "A", 2 for "B" and so on\. If the string isn't a valid column name, this method will return \-1\.
You normally will just want to create TCellAddress to convert between  cell references \(var cell = new TCellAddress\(row, col\); DoSomething\(cell\.CellRef\)\.
But this method could be used in specific cases where you want only the column string and not the full address\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TCellAddress/index.md">TCellAddress</a>.DecodeColumn(const col: string): Integer; static;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**col**|string|String which defines a column\.|


## Returns

\-1 if col can't be converted to a column reference, or the column number \(1 based\) otherwise\.

## See also

* [TCellAddress](../TCellAddress/index.md)

