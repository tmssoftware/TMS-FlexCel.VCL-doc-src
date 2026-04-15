---
uid: TXlsFile.SetFormulaTokens
description: TXlsFile.SetFormulaTokens
---

# TXlsFile\.SetFormulaTokens Method

Sets a cell with the formula specified by its tokens\. Normally you will get the tokens by modifying the result  of [TExcelFile.GetFormulaTokens\(Integer, Integer\)](../../FlexCel.Core/TExcelFile/GetFormulaTokens.md#texcelfilegetformulatokensinteger-integer)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetFormulaTokens(const sheet: Integer; const row: Integer; const col: Integer; tokens: <a href="../../FlexCel.Core/ITokenList/index.md">ITokenList</a>); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer|Sheet of the cell with the formula\. \(1 based\)|
|const|**row**|Integer|Row of the cell with the formula\. \(1 based\)|
|const|**col**|Integer|Column of the cell with the formula\. \(1 based\)|
||**tokens**|[ITokenList](../../FlexCel.Core/ITokenList/index.md)|A collection of tokens which define the formula\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

