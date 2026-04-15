---
uid: IXmlMap.GetSchema
description: IXmlMap.GetSchema
---

# IXmlMap\.GetSchema Method

Gets the schema at position index\. \(0 based\)\. The schema returned is not a copy but the actual schema in the class, so modifying it will modify the schema in the class\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../IXmlMap/index.md">IXmlMap</a>.GetSchema(const index: Integer): <a href="../TXmlMapSchema/index.md">TXmlMapSchema</a>; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**index**|Integer|Index of the schema to return, 0 based\.|


## See also

* [IXmlMap](../IXmlMap/index.md)

