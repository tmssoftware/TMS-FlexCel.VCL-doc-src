---
uid: TXlsFile.InsertHPageBreak
description: TXlsFile.InsertHPageBreak
---

# TXlsFile\.InsertHPageBreak Method

Inserts a Horizontal Page Break at the specified row\. If there is one already, it will do nothing\.
If the number of pagebreaks is bigger than the maximum Excel can admit, it will add it anyway, but you might get an  exception when saving the file as xls\. Exporting as images or PDF will use those additional page breaks\.
To control what to do when there are too many page breaks, see [TExcelFile.ErrorActions](../../FlexCel.Core/TExcelFile/ErrorActions.md)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.InsertHPageBreak(const row: Integer; const aGoesAfter: Boolean); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row where to insert the page break\. All row numbers are 1\-based, and **the breaks occur after the row\.**<br />Note that row can be 0, and this would mean a page break before row 1\. \(which Excel will ignore\)|
|const|**aGoesAfter**|Boolean|This is used by FlexCelReport to add page breaks that behave as if they affected the next row, not the row at the top\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

