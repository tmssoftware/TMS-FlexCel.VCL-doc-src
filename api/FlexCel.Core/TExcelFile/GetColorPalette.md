---
uid: TExcelFile.GetColorPalette
description: TExcelFile.GetColorPalette
---

# TExcelFile\.GetColorPalette Method

## Overloads

* [TExcelFile\.GetColorPalette\(Integer\)](#texcelfilegetcolorpaletteinteger)
* [TExcelFile\.GetColorPalette\(Integer, TUIColor\)](#texcelfilegetcolorpaletteinteger-tuicolor)

# TExcelFile\.GetColorPalette\(Integer\)
Returns a color from the color palette\. This method will throw an exception if its "index" parameter is bigger than [ColorPaletteCount](ColorPaletteCount.md), \(for example, for an automatic color\)\.
To get the real color, use [GetColorPalette\(Integer, TUIColor\)](GetColorPalette.md#texcelfilegetcolorpaletteinteger-tuicolor)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetColorPalette(const index: Integer): <a href="../TUIColor/index.md">TUIColor</a>; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**index**|Integer|Index of the entry to return\. Must be 1\<=index\<=[ColorPaletteCount](ColorPaletteCount.md)|


## Returns

Color at position index\.

## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.GetColorPalette\(Integer, TUIColor\)
Returns a color from the color palette\. If the index is not into the range 1\<=index\<=[ColorPaletteCount](ColorPaletteCount.md) this method will return the automaticColor\.


## Remarks

ColorIndexes returned by FlexCel might be \<=0 or >[ColorPaletteCount](ColorPaletteCount.md) if the color is set to Automatic\.

Automatic color is white for backgrounds, black for foregrounds and gray for gridlines\.



## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetColorPalette(const index: Integer; const automaticColor: <a href="../TUIColor/index.md">TUIColor</a>): <a href="../TUIColor/index.md">TUIColor</a>; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**index**|Integer||
|const|**automaticColor**|[TUIColor](../TUIColor/index.md)||


## See also

* [TExcelFile](../TExcelFile/index.md)

