---
uid: TPdfType
description: TPdfType
---

# TPdfType Enumeration

The variant of pdf that will be created\.


## Syntax

**Unit:** [FlexCel.Pdf](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|Standard|0|A normal pdf file\.<br />|
|PDFA1|1|PDF/A\-1a or b  \(http://en\.wikipedia\.org/?title=PDF/A\) Note that PDF/A\-1 generates larger files than PDF/A\-2, and also doesn't support transparency\.<br />But PDF/A\-1 is a more commonly used standard at the time of writing this documentation\.<br />|
|PDFA2|2|PDF/A\-2a or b\. FlexCel will create smaller files in PDF/A\-2 mode than in PDF/A\-1 mode, so if possible you should try to use PDF/A\-2 instead of A1\. A2 also supports transparency\. In FlexCel case, FlexCel can also sign PDF/A\-2 files, but no PDF/A\-1\.<br />|
|PDFA3|3|PDF/A\-3\. Note that the only difference with PDF/A2 is the ability to embed other files inside the PDF file\.<br />|


