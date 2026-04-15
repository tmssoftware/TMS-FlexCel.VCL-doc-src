---
uid: TPdfWriter.DrawString
description: TPdfWriter.DrawString
---

# TPdfWriter\.DrawString Method

## Overloads

* [TPdfWriter\.DrawString\(string, TUIFont, TUIBrush, Double, Double\)](#tpdfwriterdrawstringstring-tuifont-tuibrush-double-double)
* [TPdfWriter\.DrawString\(string, TUIFont, TUITextDecoration, TUIBrush, Double, Double\)](#tpdfwriterdrawstringstring-tuifont-tuitextdecoration-tuibrush-double-double)
* [TPdfWriter\.DrawString\(string, TUIFont, TUIPen, TUIBrush, Double, Double\)](#tpdfwriterdrawstringstring-tuifont-tuipen-tuibrush-double-double)
* [TPdfWriter\.DrawString\(string, TUIFont, TUITextDecoration, TUIPen, TUIBrush, Double, Double\)](#tpdfwriterdrawstringstring-tuifont-tuitextdecoration-tuipen-tuibrush-double-double)

# TPdfWriter\.DrawString\(string, TUIFont, TUIBrush, Double, Double\)
Writes a string to the current page\. This overload doesn't do text decorations like underline or strike\-through\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TPdfWriter/index.md">TPdfWriter</a>.DrawString(const s: string; const aFont: <a href="../../FlexCel.Core/TUIFont/index.md">TUIFont</a>; const aBrush: <a href="../../FlexCel.Core/TUIBrush/index.md">TUIBrush</a>; const x: Double; const y: Double); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**s**|string|String to write\.|
|const|**aFont**|[TUIFont](../../FlexCel.Core/TUIFont/index.md)|Font to draw the text\.|
|const|**aBrush**|[TUIBrush](../../FlexCel.Core/TUIBrush/index.md)|Brush used for Color\.|
|const|**x**|Double|X coord\. \(default from bottom left\)|
|const|**y**|Double|Y coord\. \(default from bottom left\. Might change with [YAxisGrowsDown](YAxisGrowsDown.md) value\)|


## See also

* [TPdfWriter](../TPdfWriter/index.md)

# TPdfWriter\.DrawString\(string, TUIFont, TUITextDecoration, TUIBrush, Double, Double\)
Writes a string to the current page\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TPdfWriter/index.md">TPdfWriter</a>.DrawString(const s: string; const aFont: <a href="../../FlexCel.Core/TUIFont/index.md">TUIFont</a>; const aTextDecoration: <a href="../../FlexCel.Core/TUITextDecoration/index.md">TUITextDecoration</a>; const aBrush: <a href="../../FlexCel.Core/TUIBrush/index.md">TUIBrush</a>; const x: Double; const y: Double); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**s**|string|String to write\.|
|const|**aFont**|[TUIFont](../../FlexCel.Core/TUIFont/index.md)|Font to draw the text\.|
|const|**aTextDecoration**|[TUITextDecoration](../../FlexCel.Core/TUITextDecoration/index.md)|Text decorations, like underline or strikeout\.|
|const|**aBrush**|[TUIBrush](../../FlexCel.Core/TUIBrush/index.md)|Brush used for Color\.|
|const|**x**|Double|X coord\. \(default from bottom left\)|
|const|**y**|Double|Y coord\. \(default from bottom left\. Might change with [YAxisGrowsDown](YAxisGrowsDown.md) value\)|


## See also

* [TPdfWriter](../TPdfWriter/index.md)

# TPdfWriter\.DrawString\(string, TUIFont, TUIPen, TUIBrush, Double, Double\)
Writes a string to the current page\. \. This overload doesn't do text decorations like underline or strike\-through\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TPdfWriter/index.md">TPdfWriter</a>.DrawString(const s: string; const aFont: <a href="../../FlexCel.Core/TUIFont/index.md">TUIFont</a>; const aPen: <a href="../../FlexCel.Core/TUIPen/index.md">TUIPen</a>; const aBrush: <a href="../../FlexCel.Core/TUIBrush/index.md">TUIBrush</a>; const x: Double; y: Double); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**s**|string|String to write\.|
|const|**aFont**|[TUIFont](../../FlexCel.Core/TUIFont/index.md)|Font to draw the text\.|
|const|**aPen**|[TUIPen](../../FlexCel.Core/TUIPen/index.md)|Pen to draw the text outline\. If null, no outline will be drawn\.|
|const|**aBrush**|[TUIBrush](../../FlexCel.Core/TUIBrush/index.md)|Brush used for Color\. If null, only the outline will be drawn\.|
|const|**x**|Double|X coord\. \(default from bottom left\)|
||**y**|Double|Y coord\. \(default from bottom left\. Might change with [YAxisGrowsDown](YAxisGrowsDown.md) value\)|


## See also

* [TPdfWriter](../TPdfWriter/index.md)

# TPdfWriter\.DrawString\(string, TUIFont, TUITextDecoration, TUIPen, TUIBrush, Double, Double\)
Writes a string to the current page\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TPdfWriter/index.md">TPdfWriter</a>.DrawString(const s: string; const aFont: <a href="../../FlexCel.Core/TUIFont/index.md">TUIFont</a>; const aTextDecoration: <a href="../../FlexCel.Core/TUITextDecoration/index.md">TUITextDecoration</a>; const aPen: <a href="../../FlexCel.Core/TUIPen/index.md">TUIPen</a>; const aBrush: <a href="../../FlexCel.Core/TUIBrush/index.md">TUIBrush</a>; const x: Double; y: Double); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**s**|string|String to write\.|
|const|**aFont**|[TUIFont](../../FlexCel.Core/TUIFont/index.md)|Font to draw the text\.|
|const|**aTextDecoration**|[TUITextDecoration](../../FlexCel.Core/TUITextDecoration/index.md)|Underlines and strikeouts of the text\.|
|const|**aPen**|[TUIPen](../../FlexCel.Core/TUIPen/index.md)|Pen to draw the text outline\. If null, no outline will be drawn\.|
|const|**aBrush**|[TUIBrush](../../FlexCel.Core/TUIBrush/index.md)|Brush used for Color\. If null, only the outline will be drawn\.|
|const|**x**|Double|X coord\. \(default from bottom left\)|
||**y**|Double|Y coord\. \(default from bottom left\. Might change with [YAxisGrowsDown](YAxisGrowsDown.md) value\)|


## See also

* [TPdfWriter](../TPdfWriter/index.md)

