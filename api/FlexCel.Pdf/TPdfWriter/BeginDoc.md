---
uid: TPdfWriter.BeginDoc
description: TPdfWriter.BeginDoc
---

# TPdfWriter\.BeginDoc Method

Call this method before starting the output\.
It will initialize a new page\. After this you can call [DrawString\(string, TUIFont, TUIBrush, Double, Double\)](DrawString.md#tpdfwriterdrawstringstring-tuifont-tuibrush-double-double), [NewPage](NewPage.md), etc\.
Always end the document with a call to [EndDoc](EndDoc.md) and then remember to close the stream\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TPdfWriter/index.md">TPdfWriter</a>.BeginDoc(const aDataStream: TStream);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aDataStream**|TStream||


## See also

* [TPdfWriter](../TPdfWriter/index.md)

