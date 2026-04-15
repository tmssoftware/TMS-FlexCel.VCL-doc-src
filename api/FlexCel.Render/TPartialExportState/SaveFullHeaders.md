---
uid: TPartialExportState.SaveFullHeaders
description: TPartialExportState.SaveFullHeaders
---

# TPartialExportState\.SaveFullHeaders Method

This method will output the full HTML headers needed to create an HTML file with the information in this object\.
If you wish to mix the output of the file with existing headers, you can use [SaveRelevantHeaders](SaveRelevantHeaders.md) instead to get only the relevant information to mix in the headers, or [SaveCss\(TFlexCelWriter\)](SaveCss.md#tpartialexportstatesavecsstflexcelwriter) to get only the CSS classes that need to be put in the header\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TPartialExportState/index.md">TPartialExportState</a>.SaveFullHeaders(const writer: <a href="../../FlexCel.Core/TFlexCelWriter/index.md">TFlexCelWriter</a>; htmlFileName: string);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**writer**|[TFlexCelWriter](../../FlexCel.Core/TFlexCelWriter/index.md)|Writer where you are going to write the information\.|
||**htmlFileName**|string|File name of the file you are generating\. There is no need to supply this parameter, it is only to add extra information to the generated file\. You can leave it null\.|


## See also

* [TPartialExportState](../TPartialExportState/index.md)

