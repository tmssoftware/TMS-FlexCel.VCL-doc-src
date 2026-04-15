---
uid: TXlsFile.SetColOptions
description: TXlsFile.SetColOptions
---

# TXlsFile\.SetColOptions Method

Sets all Column options at once \(if the column is hidden, etc\)\.


## Remarks

To set individual values, use the corresponding methods \(i\.e\. [TExcelFile.SetColHidden\(Integer, Integer, Boolean\)](../../FlexCel.Core/TExcelFile/SetColHidden.md#texcelfilesetcolhiddeninteger-integer-boolean)\) Use this method only to copy the options from one column to another\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetColOptions(const col: Integer; const options: Integer); override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**col**|Integer|Column Index \(1 based\)|
|const|**options**|Integer|A flag with all column options\.|


## Examples

To copy all the column options from column 1 to 2, use

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls.SetColOptions(</span><span style="color:#098658;--shiki-dark:#B5CEA8">2</span><span style="color:#000000;--shiki-dark:#D4D4D4">, xls.GetColOptions(</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">));</span></span>
<span class="line"></span></code></pre>

This is faster and simpler than assigning each option alone\.


## See also

* [TXlsFile](../TXlsFile/index.md)

