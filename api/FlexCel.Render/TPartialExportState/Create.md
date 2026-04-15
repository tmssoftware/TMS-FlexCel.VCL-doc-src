---
uid: TPartialExportState.Create
description: TPartialExportState.Create
---

# TPartialExportState\.Create Constructor

Creates a new instance of TPartialExportState\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TPartialExportState/index.md">TPartialExportState</a>.Create(const aCssData: <a href="../../FlexCel.Core/TFlexCelWriter/index.md">TFlexCelWriter</a>; const aCssUrl: string);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aCssData**|[TFlexCelWriter](../../FlexCel.Core/TFlexCelWriter/index.md)|TextWriter where an external CSS file will be stored\. If null, no CSS file will be created, even when a link to a external file might\.|
|const|**aCssUrl**|string|URL of the css file that will be linked to this file\. If null, all css information will be stored inside the html file\.|


## See also

* [TPartialExportState](../TPartialExportState/index.md)

