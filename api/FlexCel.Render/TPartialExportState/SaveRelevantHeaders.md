---
uid: TPartialExportState.SaveRelevantHeaders
description: TPartialExportState.SaveRelevantHeaders
---

# TPartialExportState\.SaveRelevantHeaders Method

This method is a middle ground between [SaveCss\(TFlexCelWriter\)](SaveCss.md#tpartialexportstatesavecsstflexcelwriter) and [SaveFullHeaders](SaveFullHeaders.md)\.
It will output only the headers that you need to add to an existing HTML file in order to include the body in the body part\.
This means that the tags like \<html> are not included\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TPartialExportState/index.md">TPartialExportState</a>.SaveRelevantHeaders(const writer: <a href="../../FlexCel.Core/TFlexCelWriter/index.md">TFlexCelWriter</a>);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**writer**|[TFlexCelWriter](../../FlexCel.Core/TFlexCelWriter/index.md)||


## See also

* [TPartialExportState](../TPartialExportState/index.md)

