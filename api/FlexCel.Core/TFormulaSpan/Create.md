---
uid: TFormulaSpan.Create
description: TFormulaSpan.Create
---

# TFormulaSpan\.Create Method

## Overloads

* [TFormulaSpan\.Create](#tformulaspancreate)
* [TFormulaSpan\.Create\(Integer, Integer, Boolean\)](#tformulaspancreateinteger-integer-boolean)

# TFormulaSpan\.Create
Creates a new TFormulaSpan and sets its values to the default values\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TFormulaSpan/index.md">TFormulaSpan</a>.Create: <a href="../TFormulaSpan/index.md">TFormulaSpan</a>; static; overload;</code></pre>

## See also

* [TFormulaSpan](../TFormulaSpan/index.md)

# TFormulaSpan\.Create\(Integer, Integer, Boolean\)
Creates a new TFormulaSpan and sets its values\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TFormulaSpan/index.md">TFormulaSpan</a>.Create(const aRowSpan: Integer; const aColSpan: Integer; const aIsTopLeft: Boolean): <a href="../TFormulaSpan/index.md">TFormulaSpan</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aRowSpan**|Integer|How many rows the formula will use\.|
|const|**aColSpan**|Integer|How many columns the formula will use\.|
|const|**aIsTopLeft**|Boolean|Indicates if this is the first formula of the array\. Only the formula that is at the top left cell of the group will be used when setting a formula\. Other formulas will be ignored, so you can copy formulas in a loop from one place to the other without worring if the cell is at the top left or not\.|


## See also

* [TFormulaSpan](../TFormulaSpan/index.md)

