---
uid: TCellAddress.CellRefR1C1
description: TCellAddress.CellRefR1C1
---

# TCellAddress\.CellRefR1C1 Method

Returns the cell reference in the objects in R1C1 notation\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TCellAddress/index.md">TCellAddress</a>.CellRefR1C1(const cellRow: Integer; const cellCol: Integer): string;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**cellRow**|Integer|Row where the cell that has the formula is\. This is used in relative R1C1 references, so for example, if the cell with the formula is B7, and this object holds a relative C9, the result would be R\[2\]C\[1\]|
|const|**cellCol**|Integer|Column where the cell that has the formula is\. This is used in relative R1C1 references, so for example, if the cell with the formula is B7, and this object holds a relative C9, the result would be R\[2\]C\[1\]|


## Returns

The cell reference in R1C1 notation\.

## See also

* [TCellAddress](../TCellAddress/index.md)

