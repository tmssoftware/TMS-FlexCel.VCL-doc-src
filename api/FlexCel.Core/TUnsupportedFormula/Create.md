---
uid: TUnsupportedFormula.Create
description: TUnsupportedFormula.Create
---

# TUnsupportedFormula\.Create Constructor

## Overloads

* [TUnsupportedFormula\.Create](#tunsupportedformulacreate)
* [TUnsupportedFormula\.Create\(TUnsupportedFormulaErrorType, TCellAddress, string, string\)](#tunsupportedformulacreatetunsupportedformulaerrortype-tcelladdress-string-string)
* [TUnsupportedFormula\.Create\(TUnsupportedFormulaErrorType, TCellAddress, string, string, TCellAddressWithFileNameArray\)](#tunsupportedformulacreatetunsupportedformulaerrortype-tcelladdress-string-string-tcelladdresswithfilenamearray)

# TUnsupportedFormula\.Create
Creates a new empty instance\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TUnsupportedFormula/index.md">TUnsupportedFormula</a>.Create;</code></pre>

## See also

* [TUnsupportedFormula](../TUnsupportedFormula/index.md)

# TUnsupportedFormula\.Create\(TUnsupportedFormulaErrorType, TCellAddress, string, string\)
Creates a new instance of a TUnsupported formula class\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TUnsupportedFormula/index.md">TUnsupportedFormula</a>.Create(const aErrorType: <a href="../TUnsupportedFormulaErrorType.md">TUnsupportedFormulaErrorType</a>; const aCell: <a href="../TCellAddress/index.md">TCellAddress</a>; const aFunctionName: string; const aFileName: string);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aErrorType**|[TUnsupported&#8203;Formula&#8203;Error&#8203;Type](../TUnsupportedFormulaErrorType.md)|See [ErrorType](ErrorType.md)|
|const|**aCell**|[TCellAddress](../TCellAddress/index.md)|See [Cell](Cell.md)|
|const|**aFunctionName**|string|See [FunctionName](FunctionName.md)|
|const|**aFileName**|string|See [FileName](FileName.md)|


## See also

* [TUnsupportedFormula](../TUnsupportedFormula/index.md)

# TUnsupportedFormula\.Create\(TUnsupportedFormulaErrorType, TCellAddress, string, string, TCellAddressWithFileNameArray\)
Creates a new instance of a TUnsupported formula class\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TUnsupportedFormula/index.md">TUnsupportedFormula</a>.Create(const aErrorType: <a href="../TUnsupportedFormulaErrorType.md">TUnsupportedFormulaErrorType</a>; const aCell: <a href="../TCellAddress/index.md">TCellAddress</a>; const aFunctionName: string; const aFileName: string; const aStackTrace: <a href="../TCellAddressWithFileName/index.md">TArray&lt;TCellAddressWithFileName></a>);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aErrorType**|[TUnsupported&#8203;Formula&#8203;Error&#8203;Type](../TUnsupportedFormulaErrorType.md)|See [ErrorType](ErrorType.md)|
|const|**aCell**|[TCellAddress](../TCellAddress/index.md)|See [Cell](Cell.md)|
|const|**aFunctionName**|string|See [FunctionName](FunctionName.md)|
|const|**aFileName**|string|See [FileName](FileName.md)|
|const|**aStackTrace**|[TArray\<&#8203;TCell&#8203;Address&#8203;With&#8203;File&#8203;Name>](../TCellAddressWithFileName/index.md)|See [StackTrace](StackTrace.md)|


## See also

* [TUnsupportedFormula](../TUnsupportedFormula/index.md)

