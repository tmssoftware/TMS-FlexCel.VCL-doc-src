---
uid: TCellAddress.TrySetCellRef
description: TCellAddress.TrySetCellRef
---

# TCellAddress\.TrySetCellRef Method

## Overloads

* [TCellAddress\.TrySetCellRef\(string\)](#tcelladdresstrysetcellrefstring)
* [TCellAddress\.TrySetCellRef\(string, TReferenceStyle, Integer, Integer\)](#tcelladdresstrysetcellrefstring-treferencestyle-integer-integer)

# TCellAddress\.TrySetCellRef\(string\)
Tries to set a cell reference, and returns true if the cell is a correct A1 reference\. This is similar to setting [CellRef](CellRef.md) to a string, but it will not raise an exception\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TCellAddress/index.md">TCellAddress</a>.TrySetCellRef(const value: string): Boolean; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**value**|string|String with the cell reference, in A1 format\. To use R1C1 notation, see [TrySetCellRef\(string, TReferenceStyle, Integer, Integer\)](TrySetCellRef.md#tcelladdresstrysetcellrefstring-treferencestyle-integer-integer)|


## Returns

True if value was a correct cell reference, false otherwise\.

## See also

* [TCellAddress](../TCellAddress/index.md)

# TCellAddress\.TrySetCellRef\(string, TReferenceStyle, Integer, Integer\)
Tries to set a cell reference, and returns true if the cell is a correct A1 or R1C1 reference\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TCellAddress/index.md">TCellAddress</a>.TrySetCellRef(const value: string; const referenceStyle: <a href="../TReferenceStyle.md">TReferenceStyle</a>; const cellRow: Integer; const cellCol: Integer): Boolean; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**value**|string|String with the cell reference, in A1 or R1C1 format\.|
|const|**referenceStyle**|[TReferenceStyle](../TReferenceStyle.md)|Style the reference is in \(A1 or R1C1\)\.|
|const|**cellRow**|Integer|Row where the cell is\. This is only used for R1C1 relative references, to know where the cell is\. For example, the reference R\[1\]C\[1\] when cellRow is 5 will reference row 6\. A1 references or absolute R1C1 references ignore this parameter\.|
|const|**cellCol**|Integer|Column where the cell is\. This is only used for R1C1 relative references, to know where the cell is\. For example, the reference R\[1\]C\[1\] when cellCol is 5 will reference column 6\. A1 references or absolute R1C1 references ignore this parameter\.|


## Returns

True if value was a correct cell reference, false otherwise\.

## See also

* [TCellAddress](../TCellAddress/index.md)

