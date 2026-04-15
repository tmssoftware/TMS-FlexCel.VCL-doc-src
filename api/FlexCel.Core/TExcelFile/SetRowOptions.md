---
uid: TExcelFile.SetRowOptions
description: TExcelFile.SetRowOptions
---

# TExcelFile\.SetRowOptions Method

Sets all Row options at once \(if the row is autosize, if it is hidden, etc\)\.


## Remarks

To set individual values, use the corresponding methods \(i\.e\. [SetAutoRowHeight](SetAutoRowHeight.md)\) Use this method only to copy the options from one row to another\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetRowOptions(const row: Integer; const options: Integer); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row Index \(1 based\)|
|const|**options**|Integer|A flag with all row options|


## Examples

To copy all the row options from row 1 to 2, use

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls.SetRowOptions(</span><span style="color:#098658;--shiki-dark:#B5CEA8">2</span><span style="color:#000000;--shiki-dark:#D4D4D4">, xls.GetRowOptions(</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">));</span></span>
<span class="line"></span></code></pre>

This is faster and simpler than assigning each option one by one\.


## See also

* [TExcelFile](../TExcelFile/index.md)

