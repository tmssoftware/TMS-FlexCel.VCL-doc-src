---
uid: IXmlMap.GetMap
description: IXmlMap.GetMap
---

# IXmlMap\.GetMap Method

Gets the map at position index\. \(0 based\)\. The map returned is not a copy but the actual map in the class, so modifying it will modify the map in the class\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../IXmlMap/index.md">IXmlMap</a>.GetMap(const index: Integer): <a href="../TXmlMapMap/index.md">TXmlMapMap</a>; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**index**|Integer|Index of the map to return, 0 based\.|


## See also

* [IXmlMap](../IXmlMap/index.md)

