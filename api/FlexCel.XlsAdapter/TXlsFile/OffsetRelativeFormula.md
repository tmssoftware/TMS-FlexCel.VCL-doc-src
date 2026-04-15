---
uid: TXlsFile.OffsetRelativeFormula
description: TXlsFile.OffsetRelativeFormula
---

# TXlsFile\.OffsetRelativeFormula Method

Use this method to know the actual formula that applies to a cell when the formula is relative\.
In some places, mostly data validations and names, Excel returns relative formulas\.

So for example you might have a name with a definition of "=Sheet1\!A2" when you are positioned at cell A1\. If you now move the cursor to cell A2 in Excel, the name definition will be "=Sheet1\!A3" since the reference is relative to the cell where the cursor is\. If you retrieve the name formula with FlexCel, as FlexCel  doesn't have a cursor, it will always return the canonical formula as if you were positioned at A1\. If you want to know the real formula when you are positioned at A2, you need to call this method with cellRow =3, cellCol = 1 and expression = "=Sheet1\!A2"\. It will return "=Sheet1\!A3"\.


## Remarks

Remember that you can use [TExcelFile.FormulaReferenceStyle](../../FlexCel.Core/TExcelFile/FormulaReferenceStyle.md) to change the formulas to R1C1 style\. R1C1 formulas are nicer for relative formulas, since they don't change when you change the cursor\. \(R1C1 references are already relative to the cell where the cursor is\)\.

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.OffsetRelativeFormula(const activeSheet: Integer; const cellRow: Integer; const cellCol: Integer; const expression: string): string; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**activeSheet**|Integer|Sheet where you are positioned when doing the calculation\. You might pass xls\.ActiveSheet here\.|
|const|**cellRow**|Integer|Row of the cell where the relative formula is\.|
|const|**cellCol**|Integer|Column of the cell where the relative formula is\.|
|const|**expression**|string|Formula to offset\. It must start with "=", and be a valid Excel formula\.|


## Returns

The formula with relative references changed to match the cell at cellRow, cellCol

## See also

* [TXlsFile](../TXlsFile/index.md)

