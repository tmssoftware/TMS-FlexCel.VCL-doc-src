---
uid: TXlsFile.SetTokens
description: TXlsFile.SetTokens
---

# TXlsFile\.SetTokens Method

This method converts a list of tokens in the corresponding string\. Normally you get the tokens from [TExcelFile.GetTokens](../../FlexCel.Core/TExcelFile/GetTokens.md) or [TExcelFile.GetFormulaTokens\(Integer, Integer\)](../../FlexCel.Core/TExcelFile/GetFormulaTokens.md#texcelfilegetformulatokensinteger-integer)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.SetTokens(const sheet: Integer; const row: Integer; const col: Integer; tokens: <a href="../../FlexCel.Core/ITokenList/index.md">ITokenList</a>): string; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer|Sheet where the formula is\. This is used to know if the A1 in the formula "=A1" refers to Sheet1\!A1 or Sheet2\!A1\.<br />This value is 1 based, and you can pass [TExcelFile.ActiveSheet](../../FlexCel.Core/TExcelFile/ActiveSheet.md) if the formula is in the active sheet\.|
|const|**row**|Integer|Row where the formula is going to be\. \(1 based\)|
|const|**col**|Integer|Column where the formula is going to be\. \(1 based\)|
||**tokens**|[ITokenList](../../FlexCel.Core/ITokenList/index.md)|A collection of tokens which define the formula\.|


## Returns

A string representing the formula\. Includes the "=" sign at the start\.

## See also

* [TXlsFile](../TXlsFile/index.md)

