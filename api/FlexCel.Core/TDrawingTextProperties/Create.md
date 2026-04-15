---
uid: TDrawingTextProperties.Create
description: TDrawingTextProperties.Create
---

# TDrawingTextProperties\.Create Method

## Overloads

* [TDrawingTextProperties\.Create\(IFillStyle, TDrawingTextAttributes\)](#tdrawingtextpropertiescreateifillstyle-tdrawingtextattributes)
* [TDrawingTextProperties\.Create\(IFillStyle, ILineStyle, IEffectProperties, NullableTDrawingColor, TDrawingUnderline, NullableTThemeTextFont, NullableTThemeTextFont, NullableTThemeTextFont, NullableTThemeTextFont, TDrawingHyperlink, TDrawingHyperlink, Boolean, TDrawingTextAttributes\)](#tdrawingtextpropertiescreateifillstyle-ilinestyle-ieffectproperties-nullabletdrawingcolor-tdrawingunderline-nullabletthemetextfont-nullabletthemetextfont-nullabletthemetextfont-nullabletthemetextfont-tdrawinghyperlink-tdrawinghyperlink-boolean-tdrawingtextattributes)

# TDrawingTextProperties\.Create\(IFillStyle, TDrawingTextAttributes\)
Creates a new instance\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TDrawingTextProperties/index.md">TDrawingTextProperties</a>.Create(aFill: <a href="../IFillStyle/index.md">IFillStyle</a>; const aAttributes: <a href="../TDrawingTextAttributes/index.md">TDrawingTextAttributes</a>): <a href="../TDrawingTextProperties/index.md">TDrawingTextProperties</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
||**aFill**|[IFillStyle](../IFillStyle/index.md)||
|const|**aAttributes**|[TDrawingText&#8203;Attributes](../TDrawingTextAttributes/index.md)||


## See also

* [TDrawingTextProperties](../TDrawingTextProperties/index.md)

# TDrawingTextProperties\.Create\(IFillStyle, ILineStyle, IEffectProperties, NullableTDrawingColor, TDrawingUnderline, NullableTThemeTextFont, NullableTThemeTextFont, NullableTThemeTextFont, NullableTThemeTextFont, TDrawingHyperlink, TDrawingHyperlink, Boolean, TDrawingTextAttributes\)
Creates a new instance\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TDrawingTextProperties/index.md">TDrawingTextProperties</a>.Create(aFill: <a href="../IFillStyle/index.md">IFillStyle</a>; aLine: <a href="../ILineStyle/index.md">ILineStyle</a>; aEffects: <a href="../IEffectProperties/index.md">IEffectProperties</a>; const aHighlight: NullableTDrawingColor; const aUnderline: <a href="../TDrawingUnderline/index.md">TDrawingUnderline</a>; const aLatin: NullableTThemeTextFont; const aEastAssian: NullableTThemeTextFont; const aComplexScript: NullableTThemeTextFont; const aSymbol: NullableTThemeTextFont; const aHyperlinkClick: <a href="../TDrawingHyperlink/index.md">TDrawingHyperlink</a>; const aHyperlinkMouseOver: <a href="../TDrawingHyperlink/index.md">TDrawingHyperlink</a>; const aRightToLeft: Boolean; const aAttributes: <a href="../TDrawingTextAttributes/index.md">TDrawingTextAttributes</a>): <a href="../TDrawingTextProperties/index.md">TDrawingTextProperties</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
||**aFill**|[IFillStyle](../IFillStyle/index.md)||
||**aLine**|[ILineStyle](../ILineStyle/index.md)||
||**aEffects**|[IEffectProperties](../IEffectProperties/index.md)||
|const|**aHighlight**|NullableTDrawingColor||
|const|**aUnderline**|[TDrawingUnderline](../TDrawingUnderline/index.md)||
|const|**aLatin**|NullableTThemeTextFont||
|const|**aEastAssian**|NullableTThemeTextFont||
|const|**aComplexScript**|NullableTThemeTextFont||
|const|**aSymbol**|NullableTThemeTextFont||
|const|**aHyperlinkClick**|[TDrawingHyperlink](../TDrawingHyperlink/index.md)||
|const|**aHyperlinkMouseOver**|[TDrawingHyperlink](../TDrawingHyperlink/index.md)||
|const|**aRightToLeft**|Boolean||
|const|**aAttributes**|[TDrawingText&#8203;Attributes](../TDrawingTextAttributes/index.md)||


## See also

* [TDrawingTextProperties](../TDrawingTextProperties/index.md)

