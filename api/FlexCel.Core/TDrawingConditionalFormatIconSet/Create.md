---
uid: TDrawingConditionalFormatIconSet.Create
description: TDrawingConditionalFormatIconSet.Create
---

# TDrawingConditionalFormatIconSet\.Create Method

Creates a new struct and initializes the data\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TDrawingConditionalFormatIconSet/index.md">TDrawingConditionalFormatIconSet</a>.Create(const aHasIcon: Boolean; const aIcon: <a href="../TConditionalFormatCustomIconDef/index.md">TConditionalFormatCustomIconDef</a>; const aHideValues: Boolean): <a href="../TDrawingConditionalFormatIconSet/index.md">TDrawingConditionalFormatIconSet</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aHasIcon**|Boolean|If false, this cell doesn't have an icon and the Icon property will be ignored and set to TCondFmtIconSet\.None\.|
|const|**aIcon**|[TConditional&#8203;Format&#8203;Custom&#8203;IconDef](../TConditionalFormatCustomIconDef/index.md)|Icon that needs to be rendered in the cell\. It will be ignored if aHasIcon is false\.|
|const|**aHideValues**|Boolean|If true, the text in the cell won't be shown\.|


## See also

* [TDrawingConditionalFormatIconSet](../TDrawingConditionalFormatIconSet/index.md)

