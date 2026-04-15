---
uid: TXlsFile.GetDataValidation
description: TXlsFile.GetDataValidation
---

# TXlsFile\.GetDataValidation Method

Returns the validation information for a specific cell\. If the cell has no Data Validation associated, this method returns null\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetDataValidation(const row: Integer; const col: Integer; out dvRange: <a href="../../FlexCel.Core/TXlsCellRange/index.md">TXlsCellRange</a>): <a href="../../FlexCel.Core/TDataValidationInfo/index.md">TDataValidationInfo</a>; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row of the cell \(1 based\)|
|const|**col**|Integer|Column of the cell \(1 based\)|
|out|**dvRange**|[TXlsCellRange](../../FlexCel.Core/TXlsCellRange/index.md)|Range of cells where the data validation is applied\.|


## Returns

The data validation for a cell, or null if the cell has no Data Validation associated\.

## See also

* [TXlsFile](../TXlsFile/index.md)

