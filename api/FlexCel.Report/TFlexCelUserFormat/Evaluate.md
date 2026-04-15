---
uid: TFlexCelUserFormat.Evaluate
description: TFlexCelUserFormat.Evaluate
---

# TFlexCelUserFormat\.Evaluate Method

Override this method on a derived class to implement your own defined function\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TFlexCelUserFormat/index.md">TFlexCelUserFormat</a>.Evaluate(const workbook: <a href="../../FlexCel.Core/TExcelFile/index.md">TExcelFile</a>; const rangeToFormat: <a href="../../FlexCel.Core/TXlsCellRange/index.md">TXlsCellRange</a>; const parameters: <a href="../../FlexCel.Core/TFormulaValue/index.md">TArray&lt;TFormulaValue></a>): <a href="../../FlexCel.Core/TFlxPartialFormat/index.md">TFlxPartialFormat</a>; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**workbook**|[TExcelFile](../../FlexCel.Core/TExcelFile/index.md)|File where we are setting the format\.|
|const|**rangeToFormat**|[TXlsCellRange](../../FlexCel.Core/TXlsCellRange/index.md)|Range of cells being formatted\. Note that it might be a full row or column if using Format Row or Format Column\.|
|const|**parameters**|[TArray\<&#8203;TFormula&#8203;Value>](../../FlexCel.Core/TFormulaValue/index.md)|An array of objects\.|


## Returns

The derived class should return the value of the function on the return parameter\.

## See also

* [TFlexCelUserFormat](../TFlexCelUserFormat/index.md)

