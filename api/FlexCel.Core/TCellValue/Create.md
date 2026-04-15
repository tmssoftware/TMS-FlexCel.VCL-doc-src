---
uid: TCellValue.Create
description: TCellValue.Create
---

# TCellValue\.Create Method

## Overloads

* [TCellValue\.Create\(Double\)](#tcellvaluecreatedouble)
* [TCellValue\.Create\(Int64\)](#tcellvaluecreateint64)
* [TCellValue\.Create\(TDateTime\)](#tcellvaluecreatetdatetime)
* [TCellValue\.Create\(string\)](#tcellvaluecreatestring)
* [TCellValue\.Create\(TRichString\)](#tcellvaluecreatetrichstring)
* [TCellValue\.Create\(Boolean\)](#tcellvaluecreateboolean)
* [TCellValue\.Create\(TFlxFormulaErrorValue\)](#tcellvaluecreatetflxformulaerrorvalue)
* [TCellValue\.Create\(TFormula\)](#tcellvaluecreatetformula)
* [TCellValue\.Create\(Variant\)](#tcellvaluecreatevariant)
* [TCellValue\.Create\(TValue\)](#tcellvaluecreatetvalue)

# TCellValue\.Create\(Double\)
Creates a cell value containing a number\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TCellValue/index.md">TCellValue</a>.Create(const a: Double): <a href="../TCellValue/index.md">TCellValue</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**a**|Double||


## See also

* [TCellValue](../TCellValue/index.md)

# TCellValue\.Create\(Int64\)
Creates a cell value containing a number\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TCellValue/index.md">TCellValue</a>.Create(const a: Int64): <a href="../TCellValue/index.md">TCellValue</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**a**|Int64||


## See also

* [TCellValue](../TCellValue/index.md)

# TCellValue\.Create\(TDateTime\)
Creates a cell value containing a datetime\. Note that cells in Excel don't have datetimes, they will be converted to numbers\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TCellValue/index.md">TCellValue</a>.Create(const a: TDateTime): <a href="../TCellValue/index.md">TCellValue</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**a**|TDateTime||


## See also

* [TCellValue](../TCellValue/index.md)

# TCellValue\.Create\(string\)
Creates a cell value containing a string\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TCellValue/index.md">TCellValue</a>.Create(const a: string): <a href="../TCellValue/index.md">TCellValue</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**a**|string||


## See also

* [TCellValue](../TCellValue/index.md)

# TCellValue\.Create\(TRichString\)
Creates a cell value containing a rich string\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TCellValue/index.md">TCellValue</a>.Create(const a: <a href="../TRichString/index.md">TRichString</a>): <a href="../TCellValue/index.md">TCellValue</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**a**|[TRichString](../TRichString/index.md)||


## See also

* [TCellValue](../TCellValue/index.md)

# TCellValue\.Create\(Boolean\)
Creates a cell value containing a boolean\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TCellValue/index.md">TCellValue</a>.Create(const a: Boolean): <a href="../TCellValue/index.md">TCellValue</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**a**|Boolean||


## See also

* [TCellValue](../TCellValue/index.md)

# TCellValue\.Create\(TFlxFormulaErrorValue\)
Creates a cell value containing an error\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TCellValue/index.md">TCellValue</a>.Create(const a: <a href="../TFlxFormulaErrorValue.md">TFlxFormulaErrorValue</a>): <a href="../TCellValue/index.md">TCellValue</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**a**|[TFlxFormulaError&#8203;Value](../TFlxFormulaErrorValue.md)||


## See also

* [TCellValue](../TCellValue/index.md)

# TCellValue\.Create\(TFormula\)
Creates a cell value containing a formula\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TCellValue/index.md">TCellValue</a>.Create(const a: <a href="../TFormula/index.md">TFormula</a>): <a href="../TCellValue/index.md">TCellValue</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**a**|[TFormula](../TFormula/index.md)||


## See also

* [TCellValue](../TCellValue/index.md)

# TCellValue\.Create\(Variant\)
Creates a cell value containing a variant\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TCellValue/index.md">TCellValue</a>.Create(const a: Variant): <a href="../TCellValue/index.md">TCellValue</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**a**|Variant||


## See also

* [TCellValue](../TCellValue/index.md)

# TCellValue\.Create\(TValue\)
Creates a cell value containing a TValue\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TCellValue/index.md">TCellValue</a>.Create(const a: TValue): <a href="../TCellValue/index.md">TCellValue</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**a**|TValue||


## See also

* [TCellValue](../TCellValue/index.md)

