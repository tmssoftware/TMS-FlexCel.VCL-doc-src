---
uid: TExcelFile.SetFormulaTokens
description: TExcelFile.SetFormulaTokens
---

# TExcelFile\.SetFormulaTokens Method

## Overloads

* [TExcelFile\.SetFormulaTokens\(Integer, Integer, ITokenList\)](#texcelfilesetformulatokensinteger-integer-itokenlist)
* [TExcelFile\.SetFormulaTokens\(Integer, Integer, Integer, ITokenList\)](#texcelfilesetformulatokensinteger-integer-integer-itokenlist)

# TExcelFile\.SetFormulaTokens\(Integer, Integer, ITokenList\)
Sets a cell with the formula specified by its tokens\. Normally you will get the tokens by modifying the result  of [GetFormulaTokens\(Integer, Integer\)](GetFormulaTokens.md#texcelfilegetformulatokensinteger-integer)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetFormulaTokens(const row: Integer; const col: Integer; tokens: <a href="../ITokenList/index.md">ITokenList</a>); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row of the cell with the formula\. \(1 based\)|
|const|**col**|Integer|Column of the cell with the formula\. \(1 based\)|
||**tokens**|[ITokenList](../ITokenList/index.md)|A collection of tokens which define the formula\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.SetFormulaTokens\(Integer, Integer, Integer, ITokenList\)
Sets a cell with the formula specified by its tokens\. Normally you will get the tokens by modifying the result  of [GetFormulaTokens\(Integer, Integer\)](GetFormulaTokens.md#texcelfilegetformulatokensinteger-integer)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetFormulaTokens(const sheet: Integer; const row: Integer; const col: Integer; tokens: <a href="../ITokenList/index.md">ITokenList</a>); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer|Sheet of the cell with the formula\. \(1 based\)|
|const|**row**|Integer|Row of the cell with the formula\. \(1 based\)|
|const|**col**|Integer|Column of the cell with the formula\. \(1 based\)|
||**tokens**|[ITokenList](../ITokenList/index.md)|A collection of tokens which define the formula\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

