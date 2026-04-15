---
uid: TSortFormulaMode
description: TSortFormulaMode
---

# TSortFormulaMode Enumeration

Defines how FlexCel will sort a range of cells, when you call XlsFile\.Sort\. You will normally want to specify "MoveFormulas",  but for huge amounts of data where you know formulas won't matter, you might choose the "ExcelLike" mode\. Note that Excel itself doesn't adapt correctly the formulas when sorting, and it works like the ExcelLike mode\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|MoveFormulas|0|All formulas will remain pointing to the right places after the sort\. This is the correct thing to do, and you will normally want to use this mode,  unless it is too slow\.<br />|
|ExcelLike|1|Formulas that are outside the range being sorted won't change\. So if you are sorting for example the range A1:B10, and have a formula in A20: = A1, after sorting A20 will still be A1, and not reference the cell it used to reference\.<br />Formulas inside the range being sorted that point to different rows will not keep pointing to the same row\.<br />If for example in A1 you have =A2 and the sorting moves row 1 to 5, then the formula will be =A6, instead of pointing to the place where row 2 moved\.<br />This method is faster than the "MoveFormulas" approach, and it is the method Excel itself uses\. If you don't have formulas pointing to other places in the row being moved, this method can be much faster\.<br />|


