---
uid: TExcelFile.GetFormulaTokens
description: TExcelFile.GetFormulaTokens
---

# TExcelFile\.GetFormulaTokens Method

## Overloads

* [TExcelFile\.GetFormulaTokens\(Integer, Integer\)](#texcelfilegetformulatokensinteger-integer)
* [TExcelFile\.GetFormulaTokens\(Integer, Integer, Integer\)](#texcelfilegetformulatokensinteger-integer-integer)

# TExcelFile\.GetFormulaTokens\(Integer, Integer\)
Returns the formula of a cell as an RPN list of tokens that you can use to analyze it\. If the cell doesn't have a formula, then this method will return null\.


Note that the result is an RPN expression, so for example the formula "= 1 \* 2 \+ 3" would be returned as "1, 2, \*, 3, \+"\. While the formula "= 1 \* \(2 \+ 3\)" would be returned as "1, 2, 3, \+, \*"



## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetFormulaTokens(const row: Integer; const col: Integer): <a href="../ITokenList/index.md">ITokenList</a>; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row of the cell with the formula\. \(1 based\)|
|const|**col**|Integer|Column of the cell with the formula\. \(1 based\)|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.GetFormulaTokens\(Integer, Integer, Integer\)
Returns the formula of a cell as an RPN list of tokens that you can use to analyze it\. If the cell doesn't have a formula, then this method will return null\.


Note that the result is an RPN expression, so for example the formula "= 1 \* 2 \+ 3" would be returned as "1, 2, \*, 3, \+"\. While the formula "= 1 \* \(2 \+ 3\)" would be returned as "1, 2, 3, \+, \*"


See [Using Tokens](xref:UsingTokens) for more information\.




## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetFormulaTokens(const sheet: Integer; const row: Integer; const col: Integer): <a href="../ITokenList/index.md">ITokenList</a>; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer|Sheet where the formula is\.|
|const|**row**|Integer|Row of the cell with the formula\. \(1 based\)|
|const|**col**|Integer|Column of the cell with the formula\. \(1 based\)|


## See also

* [TExcelFile](../TExcelFile/index.md)

