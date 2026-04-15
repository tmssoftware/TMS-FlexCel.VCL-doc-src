---
uid: TXlsFile.InsertVPageBreak
description: TXlsFile.InsertVPageBreak
---

# TXlsFile\.InsertVPageBreak Method

Inserts a Vertical Page Break at the specified column\. If there is one already, it will do nothing\.
If the number of pagebreaks is bigger than the maximum Excel can admit, it will add it anyway, but you might get an  exception when saving the file as xls\. Exporting as images or PDF will use those additional page breaks\.
To control what to do when there are too many page breaks, see [TExcelFile.ErrorActions](../../FlexCel.Core/TExcelFile/ErrorActions.md)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.InsertVPageBreak(const col: Integer; const aGoesAfter: Boolean); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**col**|Integer|Column where to insert the page break All column numbers are 1\-based, and **the breaks occur after the column\.**<br />Note that col can be 0, and this would mean a page break before column 1\. \(which Excel will ignore\)|
|const|**aGoesAfter**|Boolean|This is used by FlexCelReport to add page breaks that behave as if they affected the next column, not the column to the left\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

