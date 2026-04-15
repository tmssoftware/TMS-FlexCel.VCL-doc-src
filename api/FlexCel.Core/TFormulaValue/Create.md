---
uid: TFormulaValue.Create
description: TFormulaValue.Create
---

# TFormulaValue\.Create Method

## Overloads

* [TFormulaValue\.Create\(Double\)](#tformulavaluecreatedouble)
* [TFormulaValue\.Create\(Int64\)](#tformulavaluecreateint64)
* [TFormulaValue\.Create\(TDateTime\)](#tformulavaluecreatetdatetime)
* [TFormulaValue\.Create\(string\)](#tformulavaluecreatestring)
* [TFormulaValue\.Create\(Boolean\)](#tformulavaluecreateboolean)
* [TFormulaValue\.Create\(TFlxFormulaErrorValue\)](#tformulavaluecreatetflxformulaerrorvalue)
* [TFormulaValue\.Create\(TFormulaValueArray2\)](#tformulavaluecreatetformulavaluearray2)
* [TFormulaValue\.Create\(TAddress\)](#tformulavaluecreatetaddress)
* [TFormulaValue\.Create\(TSingleFormulaValue\)](#tformulavaluecreatetsingleformulavalue)
* [TFormulaValue\.Create\(TAverageValue\)](#tformulavaluecreatetaveragevalue)
* [TFormulaValue\.Create\(TArray\<TAddress>, Boolean\)](#tformulavaluecreatetarraytaddress-boolean)
* [TFormulaValue\.Create\(Integer, Integer\)](#tformulavaluecreateinteger-integer)
* [TFormulaValue\.Create\(TAddress, TAddress, Boolean\)](#tformulavaluecreatetaddress-taddress-boolean)

# TFormulaValue\.Create\(Double\)
Creates a formula value containing a number\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TFormulaValue/index.md">TFormulaValue</a>.Create(const a: Double): <a href="../TFormulaValue/index.md">TFormulaValue</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**a**|Double||


## See also

* [TFormulaValue](../TFormulaValue/index.md)

# TFormulaValue\.Create\(Int64\)
Creates a formula value containing a number\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TFormulaValue/index.md">TFormulaValue</a>.Create(const a: Int64): <a href="../TFormulaValue/index.md">TFormulaValue</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**a**|Int64||


## See also

* [TFormulaValue](../TFormulaValue/index.md)

# TFormulaValue\.Create\(TDateTime\)
Creates a formula value containing a DateTime\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TFormulaValue/index.md">TFormulaValue</a>.Create(const a: TDateTime): <a href="../TFormulaValue/index.md">TFormulaValue</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**a**|TDateTime||


## See also

* [TFormulaValue](../TFormulaValue/index.md)

# TFormulaValue\.Create\(string\)
Creates a formula value containing a string\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TFormulaValue/index.md">TFormulaValue</a>.Create(const a: string): <a href="../TFormulaValue/index.md">TFormulaValue</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**a**|string||


## See also

* [TFormulaValue](../TFormulaValue/index.md)

# TFormulaValue\.Create\(Boolean\)
Creates a formula value containing a boolean\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TFormulaValue/index.md">TFormulaValue</a>.Create(const a: Boolean): <a href="../TFormulaValue/index.md">TFormulaValue</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**a**|Boolean||


## See also

* [TFormulaValue](../TFormulaValue/index.md)

# TFormulaValue\.Create\(TFlxFormulaErrorValue\)
Creates a formula value containing an error\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TFormulaValue/index.md">TFormulaValue</a>.Create(const a: <a href="../TFlxFormulaErrorValue.md">TFlxFormulaErrorValue</a>): <a href="../TFormulaValue/index.md">TFormulaValue</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**a**|[TFlxFormulaError&#8203;Value](../TFlxFormulaErrorValue.md)||


## See also

* [TFormulaValue](../TFormulaValue/index.md)

# TFormulaValue\.Create\(TFormulaValueArray2\)
Creates a formula value containing an array\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TFormulaValue/index.md">TFormulaValue</a>.Create(const a: <a href="../TFormulaValue/index.md">TArray&lt;TArray&lt;TFormulaValue>></a>): <a href="../TFormulaValue/index.md">TFormulaValue</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**a**|[TArray\<&#8203;TArray\<&#8203;TFormula&#8203;Value>&#8203;>](../TFormulaValue/index.md)||


## See also

* [TFormulaValue](../TFormulaValue/index.md)

# TFormulaValue\.Create\(TAddress\)
Creates a formula value containing a cell address\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TFormulaValue/index.md">TFormulaValue</a>.Create(const a: <a href="../TAddress/index.md">TAddress</a>): <a href="../TFormulaValue/index.md">TFormulaValue</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**a**|[TAddress](../TAddress/index.md)||


## See also

* [TFormulaValue](../TFormulaValue/index.md)

# TFormulaValue\.Create\(TSingleFormulaValue\)
Creates a formula value containing a single formula value\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TFormulaValue/index.md">TFormulaValue</a>.Create(const a: <a href="../TSingleFormulaValue/index.md">TSingleFormulaValue</a>): <a href="../TFormulaValue/index.md">TFormulaValue</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**a**|[TSingleFormulaValue](../TSingleFormulaValue/index.md)||


## See also

* [TFormulaValue](../TFormulaValue/index.md)

# TFormulaValue\.Create\(TAverageValue\)
Creates a formula value containing an Average Value\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TFormulaValue/index.md">TFormulaValue</a>.Create(const a: <a href="../TAverageValue/index.md">TAverageValue</a>): <a href="../TFormulaValue/index.md">TFormulaValue</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**a**|[TAverageValue](../TAverageValue/index.md)||


## See also

* [TFormulaValue](../TFormulaValue/index.md)

# TFormulaValue\.Create\(TArray\<TAddress>, Boolean\)
Creates a formula value containing a list of cell addresses\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TFormulaValue/index.md">TFormulaValue</a>.Create(const a: TArray&lt;<a href="../TAddress/index.md">TAddress</a>&gt;; const IsRange: Boolean): <a href="../TFormulaValue/index.md">TFormulaValue</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**a**|TArray\<[TAddress](../TAddress/index.md)>||
|const|**IsRange**|Boolean||


## See also

* [TFormulaValue](../TFormulaValue/index.md)

# TFormulaValue\.Create\(Integer, Integer\)
Creates a formula value with an array of empty TSingleFormulaValue entries\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TFormulaValue/index.md">TFormulaValue</a>.Create(const aRowCount: Integer; const aColCount: Integer): <a href="../TFormulaValue/index.md">TFormulaValue</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aRowCount**|Integer||
|const|**aColCount**|Integer||


## See also

* [TFormulaValue](../TFormulaValue/index.md)

# TFormulaValue\.Create\(TAddress, TAddress, Boolean\)
Creates a formula value containing two cell addresses\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TFormulaValue/index.md">TFormulaValue</a>.Create(const a: <a href="../TAddress/index.md">TAddress</a>; const b: <a href="../TAddress/index.md">TAddress</a>; const IsRange: Boolean): <a href="../TFormulaValue/index.md">TFormulaValue</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**a**|[TAddress](../TAddress/index.md)||
|const|**b**|[TAddress](../TAddress/index.md)||
|const|**IsRange**|Boolean||


## See also

* [TFormulaValue](../TFormulaValue/index.md)

