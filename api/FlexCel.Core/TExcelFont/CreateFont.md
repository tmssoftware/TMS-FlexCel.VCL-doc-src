---
uid: TExcelFont.CreateFont
description: TExcelFont.CreateFont
---

# TExcelFont\.CreateFont Method

## Overloads

* [TExcelFont\.CreateFont\(string, Double, TUIFontStyleSet\)](#texcelfontcreatefontstring-double-tuifontstyleset)
* [TExcelFont\.CreateFont\(TUIFont, TUIColor, TUITextDecoration, Double\)](#texcelfontcreatefonttuifont-tuicolor-tuitextdecoration-double)

# TExcelFont\.CreateFont\(string, Double, TUIFontStyleSet\)
Tries to create a new font given the Excel data\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TExcelFont/index.md">TExcelFont</a>.CreateFont(const FontName: string; const FontSize: Double; const Style: <a href="../TUIFontStyle.md">Set of TUIFontStyle</a>): <a href="../TUIFont/index.md">TUIFont</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**FontName**|string|Name of the font we want to create\.|
|const|**FontSize**|Double|Size of the font\.|
|const|**Style**|[Set of TUIFontStyle](../TUIFontStyle.md)|Style of the font\.|


## Returns

A new font with the desired parameters\.

## See also

* [TExcelFont](../TExcelFont/index.md)

# TExcelFont\.CreateFont\(TUIFont, TUIColor, TUITextDecoration, Double\)
Creates a font given another font, with a different color\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TExcelFont/index.md">TExcelFont</a>.CreateFont(const aFont: <a href="../TUIFont/index.md">TUIFont</a>; const aFontColor: <a href="../TUIColor/index.md">TUIColor</a>; const aTextDecoration: <a href="../TUITextDecoration/index.md">TUITextDecoration</a>; const aScale: Double): <a href="../TFlxFont/index.md">TFlxFont</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aFont**|[TUIFont](../TUIFont/index.md)|Font to be used as base\.|
|const|**aFontColor**|[TUIColor](../TUIColor/index.md)|New font color\.|
|const|**aTextDecoration**|[TUITextDecoration](../TUITextDecoration/index.md)|Underline/strikeout|
|const|**aScale**|Double|Scale for the font\. For normal uses, specify 1\. A value of 2 would mean to create a file with twice the size\.|


## See also

* [TExcelFont](../TExcelFont/index.md)

