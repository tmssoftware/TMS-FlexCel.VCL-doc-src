---
uid: TXls3DRange.TrySetRange3DRef
description: TXls3DRange.TrySetRange3DRef
---

# TXls3DRange\.TrySetRange3DRef Method

Tries to set the value of the 3d range based on the string that defines the range in A1 notation\. If the name can't be set, no data is modified and this method returns false\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXls3DRange/index.md">TXls3DRange</a>.TrySetRange3DRef(const xls: TCoreExcelFile; const rangeDef: string): Boolean;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**xls**|TCoreExcelFile|ExcelFile where the range is defined\.|
|const|**rangeDef**|string|String that defines the range, like for example "=\[Sheet2:Sheet3\]\!A1:A3|


## See also

* [TXls3DRange](../TXls3DRange/index.md)

