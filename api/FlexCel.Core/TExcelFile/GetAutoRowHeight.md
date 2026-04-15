---
uid: TExcelFile.GetAutoRowHeight
description: TExcelFile.GetAutoRowHeight
---

# TExcelFile\.GetAutoRowHeight Method

Returns if the row is adjusting its size to the cell \(the default\) or if it has a fixed height\.


## Remarks

By default, Excel rows auto adapt their size to the font size\.
If you set the row height manually, it will remain fixed to this size until you set  AutoFit \(Menu\->Format\->Row\->AutoFit\) back\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetAutoRowHeight(const row: Integer): Boolean; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row index \(1\-based\)|


## Returns

True if AutoFit is on for the row, False if it has a fixed size

## See also

* [TExcelFile](../TExcelFile/index.md)

