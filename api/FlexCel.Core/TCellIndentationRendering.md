---
uid: TCellIndentationRendering
description: TCellIndentationRendering
---

# TCellIndentationRendering Enumeration

Defines how FlexCel renders cell indentation when exporting to pdf or printing\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|ScaleIndentationWithPrintScale|0|The cell indentation is made smaller when the print scale is smaller and vice\-versa\.<br />This is the most logical setting, but it is not how Excel behaves\. See ['Cell indentation' in the Api Developer Guide](xref:ApiDeveloperGuide#cell-indentation)|
|DontScaleIndentationWithPrintScale|1|Keep the absolute value of cell indentation fixed in inches/cm when scaling the sheet\.<br />This is the mode in which FlexCel 6\.23 and older behaved\.<br />|
|DontScaleIndentationWithPrintScaleExceptWhenPrintHeadings|2|Behaves like DontScaleIndentationWithPrintScale if "Print Headings" is false, and like ScaleIndentationWithPrintScale if "Print Headings" is true\. This is how Excel behaves\.<br />|


