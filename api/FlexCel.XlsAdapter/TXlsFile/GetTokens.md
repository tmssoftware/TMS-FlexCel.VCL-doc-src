---
uid: TXlsFile.GetTokens
description: TXlsFile.GetTokens
---

# TXlsFile\.GetTokens Method

Returns the tokens for a formula in text form\. See [TExcelFile.GetFormulaTokens\(Integer, Integer\)](../../FlexCel.Core/TExcelFile/GetFormulaTokens.md#texcelfilegetformulatokensinteger-integer) for more information\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetTokens(const sheet: Integer; const formula: string): <a href="../../FlexCel.Core/ITokenList/index.md">ITokenList</a>; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer|Sheet where the formula is\. This is used to know if the A1 in the formula "=A1" refers to Sheet1\!A1 or Sheet2\!A1\.<br />This value is 1 based, and you can pass [TExcelFile.ActiveSheet](../../FlexCel.Core/TExcelFile/ActiveSheet.md) if the formula is in the active sheet\.|
|const|**formula**|string|Formula we want to convert into tokens\. Must start with an "=" sign\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

