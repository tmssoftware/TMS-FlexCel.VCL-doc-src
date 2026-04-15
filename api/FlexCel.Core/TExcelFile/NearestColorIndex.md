---
uid: TExcelFile.NearestColorIndex
description: TExcelFile.NearestColorIndex
---

# TExcelFile\.NearestColorIndex Method

## Overloads

* [TExcelFile\.NearestColorIndex\(TUIColor\)](#texcelfilenearestcolorindextuicolor)
* [TExcelFile\.NearestColorIndex\(TUIColor, BooleanArray\)](#texcelfilenearestcolorindextuicolor-booleanarray)

# TExcelFile\.NearestColorIndex\(TUIColor\)
Returns the most similar entry on the excel palette for a given color\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.NearestColorIndex(const value: <a href="../TUIColor/index.md">TUIColor</a>): Integer; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**value**|[TUIColor](../TUIColor/index.md)|Color we want to use\.|


## Returns

Most similar color on the Excel palette\.

## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.NearestColorIndex\(TUIColor, BooleanArray\)
**IMPORTANT:** Since FlexCel 5\.1, using [OptimizeColorPalette](OptimizeColorPalette.md) before saving should normally be used instead of this method to get an optimized palette\. Just enter the true colors in FlexCel, and call [OptimizeColorPalette](OptimizeColorPalette.md) before saving\.

Returns the most similar entry on the excel palette for a given color\.
If UsedColors is not null, it will try to modify the Excel color palette to get a better match on the color, modifying among the not used colors\.
Note that modifying the standard palette might result on a file that is not easy to edit on Excel later, since it does not have the standard Excel colors\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.NearestColorIndex(const value: <a href="../TUIColor/index.md">TUIColor</a>; const UsedColors: TArray&lt;Boolean>): Integer; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**value**|[TUIColor](../TUIColor/index.md)|Color we want to use\.|
|const|**UsedColors**|TArray\<Boolean>|If null, this behaves like the standard NearestColorIndex\.<br />To get a list of used colors for the first call, use [GetUsedPaletteColors](GetUsedPaletteColors.md)\.<br />After the first call, keep using the same UsedColors structure and do not call GetUsedPaletteColors again, to avoid overwriting colors that are not yet inserted into the xls file with new ones\. You can call GetUsedPaletteColors only after you added the format with [AddFormat](AddFormat.md)|


## Returns

Most similar color on the Excel palette\.

## See also

* [TExcelFile](../TExcelFile/index.md)

