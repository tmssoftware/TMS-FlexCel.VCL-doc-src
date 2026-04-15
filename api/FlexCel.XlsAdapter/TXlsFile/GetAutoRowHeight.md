---
uid: TXlsFile.GetAutoRowHeight
description: TXlsFile.GetAutoRowHeight
---

# TXlsFile\.GetAutoRowHeight Method

Returns if the row is adjusting its size to the cell \(the default\) or if it has a fixed height\.


## Remarks

By default, Excel rows auto adapt their size to the font size\.
If you set the row height manually, it will remain fixed to this size until you set  AutoFit \(Menu\->Format\->Row\->AutoFit\) back\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetAutoRowHeight(const row: Integer): Boolean; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row index \(1\-based\)|


## Returns

True if AutoFit is on for the row, False if it has a fixed size

## See also

* [TXlsFile](../TXlsFile/index.md)

