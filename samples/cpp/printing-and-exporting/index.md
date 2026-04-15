---
uid: Printing_and_Exporting-CPlusPlus
description: Printing_and_Exporting-CPlusPlus
---


# Printing, previewing and exporting files (C++)

## Overview


FlexCel reporting is oriented to creating files, not to print them. Once you have the files you can
save them, email them or just print them if that's what you really need. But, sometimes you
might want to directly print the report, and here is where
[TFlexCelPrintDocument](~/api/FlexCel.Render/TFlexCelPrintDocument/index.md) can be helpful. You might want also to export
the report to PDF, and then you would use [TFlexCelPdfExport](~/api/FlexCel.Render/TFlexCelPdfExport/index.md). Or you might want to export
the Excel file as an image, or to fax it, using [TFlexCelImgExport](~/api/FlexCel.Render/TFlexCelImgExport/index.md).

All of those components share a common rendering engine, that
\"renders\" the xls file to a canvas, so it can be printed or saved.
Keep in mind that results are not 100% the same, and they cannot be, but
they are very similar.


## In this section
* [Custom previewing](custompreview/index.md)

