---
uid: TPartialExportState.StartBody
description: TPartialExportState.StartBody
---

# TPartialExportState\.StartBody Method

Starts writing a body declaration\. After calling this method, you should call [SaveBody](SaveBody.md) for the parts you want to save, and end up with a call to [EndHtmlFile](EndHtmlFile.md)

## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TPartialExportState/index.md">TPartialExportState</a>.StartBody(const writer: <a href="../../FlexCel.Core/TFlexCelWriter/index.md">TFlexCelWriter</a>);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**writer**|[TFlexCelWriter](../../FlexCel.Core/TFlexCelWriter/index.md)|TextWriter where we are going to save the results\.|


## See also

* [TPartialExportState](../TPartialExportState/index.md)

