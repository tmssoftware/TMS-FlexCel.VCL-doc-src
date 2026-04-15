---
uid: TExcelFile.SetAutoRowHeight
description: TExcelFile.SetAutoRowHeight
---

# TExcelFile\.SetAutoRowHeight Method

Sets the current row to automatically autosize to the biggest cell or not\.


## Remarks

By default, Excel rows auto adapt their size to the font size\.
If you set the row height manually, it will remain fixed to this size until you set  AutoFit \(Menu\->Format\->Row\->AutoFit\) back\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetAutoRowHeight(const row: Integer; const autoRowHeight: Boolean); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row index \(1\-based\)|
|const|**autoRowHeight**|Boolean|If true, row will have autofit\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

