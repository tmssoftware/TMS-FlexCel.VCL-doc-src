---
uid: TXlsFile.ConditionallyModifyFormat
description: TXlsFile.ConditionallyModifyFormat
---

# TXlsFile\.ConditionallyModifyFormat Method

Modifies the format of the specified cell if it has a conditional format active\.
Returns a modified format with the applied conditional format if there was any change, null otherwise\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.ConditionallyModifyFormat(const format: <a href="../../FlexCel.Core/TFlxFormat/index.md">TFlxFormat</a>; const row: Integer; const col: Integer; const includeTables: Boolean; out ExtraInfo: <a href="../../FlexCel.Core/IDrawingConditionalFormat/index.md">IDrawingConditionalFormat</a>): <a href="../../FlexCel.Core/TFlxFormat/index.md">TFlxFormat</a>; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**format**|[TFlxFormat](../../FlexCel.Core/TFlxFormat/index.md)|Original format of the cell\.|
|const|**row**|Integer|Row of the cell \(1 based\)|
|const|**col**|Integer|Column of the cell \(1 based\)|
|const|**includeTables**|Boolean|If true and the cell is inside a table, the format for the table will be also taken in account\.|
|out|**ExtraInfo**|[IDrawingConditional&#8203;Format](../../FlexCel.Core/IDrawingConditionalFormat/index.md)||


## Returns

If the format is modified by a conditional format, it returns the new format\.
If there are no changes returns null, to avoid creating new instances of TFlxFormat\.

## See also

* [TXlsFile](../TXlsFile/index.md)

