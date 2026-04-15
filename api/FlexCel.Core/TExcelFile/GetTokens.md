---
uid: TExcelFile.GetTokens
description: TExcelFile.GetTokens
---

# TExcelFile\.GetTokens Method

Returns the tokens for a formula in text form\. See [GetFormulaTokens\(Integer, Integer\)](GetFormulaTokens.md#texcelfilegetformulatokensinteger-integer) for more information\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetTokens(const sheet: Integer; const formula: string): <a href="../ITokenList/index.md">ITokenList</a>; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer|Sheet where the formula is\. This is used to know if the A1 in the formula "=A1" refers to Sheet1\!A1 or Sheet2\!A1\.<br />This value is 1 based, and you can pass [ActiveSheet](ActiveSheet.md) if the formula is in the active sheet\.|
|const|**formula**|string|Formula we want to convert into tokens\. Must start with an "=" sign\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

