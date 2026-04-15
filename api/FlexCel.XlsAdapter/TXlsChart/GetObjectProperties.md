---
uid: TXlsChart.GetObjectProperties
description: TXlsChart.GetObjectProperties
---

# TXlsChart\.GetObjectProperties Method

Returns information on an object and all of its children\. If the shape doesn't exist, this method returns null\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsChart/index.md">TXlsChart</a>.GetObjectProperties(const objectIndex: Integer; const GetShapeOptions: Boolean): <a href="../../FlexCel.Core/IShapeProperties/index.md">IShapeProperties</a>; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1\-based\)|
|const|**GetShapeOptions**|Boolean|When true, shape options will be retrieved\. As this can be a slow operation, only specify true when you really need those options\.|


## See also

* [TXlsChart](../TXlsChart/index.md)

