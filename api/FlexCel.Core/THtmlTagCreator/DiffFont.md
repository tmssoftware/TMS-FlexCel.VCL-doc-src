---
uid: THtmlTagCreator.DiffFont
description: THtmlTagCreator.DiffFont
---

# THtmlTagCreator\.DiffFont Method

Returns the tags for a difference between one font and the next\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../THtmlTagCreator/index.md">THtmlTagCreator</a>.DiffFont(const xls: TCoreExcelFile; const originalFont: <a href="../TFlxFont/index.md">TFlxFont</a>; const nextFont: <a href="../TFlxFont/index.md">TFlxFont</a>; const htmlVersion: <a href="../THtmlVersion.md">THtmlVersion</a>; const htmlStyle: <a href="../THtmlStyle.md">THtmlStyle</a>; var tagsToClose: string; const OnHtmlFont: <a href="../IHtmlFontEvent/index.md">IHtmlFontEvent</a>; const MsFormat: Boolean; const IncludeFmtInCell: Boolean; const origFontScale: Double; const nextFontScale: Double): string; static;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**xls**|TCoreExcelFile||
|const|**originalFont**|[TFlxFont](../TFlxFont/index.md)||
|const|**nextFont**|[TFlxFont](../TFlxFont/index.md)||
|const|**htmlVersion**|[THtmlVersion](../THtmlVersion.md)||
|const|**htmlStyle**|[THtmlStyle](../THtmlStyle.md)||
|var|**tagsToClose**|string|Tags that need to be closed\. This method might decide to accumulate font tags or not, depending on the case\.|
|const|**OnHtmlFont**|[IHtmlFontEvent](../IHtmlFontEvent/index.md)||
|const|**MsFormat**|Boolean||
|const|**IncludeFmtInCell**|Boolean||
|const|**origFontScale**|Double||
|const|**nextFontScale**|Double||


## See also

* [THtmlTagCreator](../THtmlTagCreator/index.md)

