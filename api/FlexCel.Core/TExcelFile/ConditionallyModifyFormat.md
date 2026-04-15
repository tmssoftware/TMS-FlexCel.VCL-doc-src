---
uid: TExcelFile.ConditionallyModifyFormat
description: TExcelFile.ConditionallyModifyFormat
---

# TExcelFile\.ConditionallyModifyFormat Method

## Overloads

* [TExcelFile\.ConditionallyModifyFormat\(TFlxFormat, Integer, Integer, IDrawingConditionalFormat\)](#texcelfileconditionallymodifyformattflxformat-integer-integer-idrawingconditionalformat)
* [TExcelFile\.ConditionallyModifyFormat\(TFlxFormat, Integer, Integer, Boolean, IDrawingConditionalFormat\)](#texcelfileconditionallymodifyformattflxformat-integer-integer-boolean-idrawingconditionalformat)

# TExcelFile\.ConditionallyModifyFormat\(TFlxFormat, Integer, Integer, IDrawingConditionalFormat\)
Modifies the format of the specified cell if it has a conditional format active\.
Returns a modified format with the applied conditional format if there was any change, null otherwise\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.ConditionallyModifyFormat(const format: <a href="../TFlxFormat/index.md">TFlxFormat</a>; const row: Integer; const col: Integer; out extraInfo: <a href="../IDrawingConditionalFormat/index.md">IDrawingConditionalFormat</a>): <a href="../TFlxFormat/index.md">TFlxFormat</a>; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**format**|[TFlxFormat](../TFlxFormat/index.md)|Original format of the cell\.|
|const|**row**|Integer|Row of the cell \(1 based\)|
|const|**col**|Integer|Column of the cell \(1 based\)|
|out|**extraInfo**|[IDrawingConditional&#8203;Format](../IDrawingConditionalFormat/index.md)|Extra information about the format of the cell, like if it has to draw an icon or a databar\.|


## Returns

If the format is modified by a conditional format, it returns the new format\.
If there are no changes returns null, to avoid creating new instances of TFlxFormat\.

## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.ConditionallyModifyFormat\(TFlxFormat, Integer, Integer, Boolean, IDrawingConditionalFormat\)
Modifies the format of the specified cell if it has a conditional format active\.
Returns a modified format with the applied conditional format if there was any change, null otherwise\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.ConditionallyModifyFormat(const format: <a href="../TFlxFormat/index.md">TFlxFormat</a>; const row: Integer; const col: Integer; const includeTables: Boolean; out extraInfo: <a href="../IDrawingConditionalFormat/index.md">IDrawingConditionalFormat</a>): <a href="../TFlxFormat/index.md">TFlxFormat</a>; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**format**|[TFlxFormat](../TFlxFormat/index.md)|Original format of the cell\.|
|const|**row**|Integer|Row of the cell \(1 based\)|
|const|**col**|Integer|Column of the cell \(1 based\)|
|const|**includeTables**|Boolean|If true and the cell is inside a table, the format for the table will be also taken in account\.|
|out|**extraInfo**|[IDrawingConditional&#8203;Format](../IDrawingConditionalFormat/index.md)|Extra information about the format of the cell, like if it has to draw an icon or a databar\.|


## Returns

If the format is modified by a conditional format, it returns the new format\.
If there are no changes returns null, to avoid creating new instances of TFlxFormat\.

## See also

* [TExcelFile](../TExcelFile/index.md)

