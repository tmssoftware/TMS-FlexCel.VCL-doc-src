---
uid: TXlsFile.GetFormulaTokens
description: TXlsFile.GetFormulaTokens
---

# TXlsFile\.GetFormulaTokens Method

Returns the formula of a cell as an RPN list of tokens that you can use to analyze it\. If the cell doesn't have a formula, then this method will return null\.


Note that the result is an RPN expression, so for example the formula "= 1 \* 2 \+ 3" would be returned as "1, 2, \*, 3, \+"\. While the formula "= 1 \* \(2 \+ 3\)" would be returned as "1, 2, 3, \+, \*"


See [Using Tokens](xref:UsingTokens) for more information\.




## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetFormulaTokens(const sheet: Integer; const row: Integer; const col: Integer): <a href="../../FlexCel.Core/ITokenList/index.md">ITokenList</a>; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer|Sheet where the formula is\.|
|const|**row**|Integer|Row of the cell with the formula\. \(1 based\)|
|const|**col**|Integer|Column of the cell with the formula\. \(1 based\)|


## See also

* [TXlsFile](../TXlsFile/index.md)

