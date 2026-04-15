---
uid: TFormula.Create
description: TFormula.Create
---

# TFormula\.Create Method

## Overloads

* [TFormula\.Create](#tformulacreate)
* [TFormula\.Create\(string\)](#tformulacreatestring)
* [TFormula\.Create\(string, TSingleFormulaValue\)](#tformulacreatestring-tsingleformulavalue)
* [TFormula\.Create\(string, TSingleFormulaValue, TFormulaSpan\)](#tformulacreatestring-tsingleformulavalue-tformulaspan)

# TFormula\.Create
Creates an empty Excel formula

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TFormula/index.md">TFormula</a>.Create: <a href="../TFormula/index.md">TFormula</a>; static; overload;</code></pre>

## See also

* [TFormula](../TFormula/index.md)

# TFormula\.Create\(string\)
Creates a formula with the corresponding text and result=null\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TFormula/index.md">TFormula</a>.Create(const aText: string): <a href="../TFormula/index.md">TFormula</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aText**|string|Formula Text|


## See also

* [TFormula](../TFormula/index.md)

# TFormula\.Create\(string, TSingleFormulaValue\)
Creates a formula with the corresponding text and result\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TFormula/index.md">TFormula</a>.Create(const aText: string; const aResult: <a href="../TSingleFormulaValue/index.md">TSingleFormulaValue</a>): <a href="../TFormula/index.md">TFormula</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aText**|string|Formula Text|
|const|**aResult**|[TSingleFormulaValue](../TSingleFormulaValue/index.md)|Formula Result|


## See also

* [TFormula](../TFormula/index.md)

# TFormula\.Create\(string, TSingleFormulaValue, TFormulaSpan\)
Creates a formula that spans to more than one row or column\. Use it to create multicell array formulas or what\-if tables\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TFormula/index.md">TFormula</a>.Create(const aText: string; const aResult: <a href="../TSingleFormulaValue/index.md">TSingleFormulaValue</a>; const aSpan: <a href="../TFormulaSpan/index.md">TFormulaSpan</a>): <a href="../TFormula/index.md">TFormula</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aText**|string|Formula Text|
|const|**aResult**|[TSingleFormulaValue](../TSingleFormulaValue/index.md)|Formula Result\. You will normally want to set this to null, as it will be recalculated by FlexCel\.|
|const|**aSpan**|[TFormulaSpan](../TFormulaSpan/index.md)|How many rows and columns this formula will span, and in which position for the array the formula is\.|


## See also

* [TFormula](../TFormula/index.md)

