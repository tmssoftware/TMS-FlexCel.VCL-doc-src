---
uid: TXlsFile.NearestColorIndex
description: TXlsFile.NearestColorIndex
---

# TXlsFile\.NearestColorIndex Method

## Overloads

* [TXlsFile\.NearestColorIndex\(TUIColor\)](#txlsfilenearestcolorindextuicolor)
* [TXlsFile\.NearestColorIndex\(TUIColor, BooleanArray\)](#txlsfilenearestcolorindextuicolor-booleanarray)

# TXlsFile\.NearestColorIndex\(TUIColor\)
Returns the most similar entry on the excel palette for a given color\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.NearestColorIndex(const value: <a href="../../FlexCel.Core/TUIColor/index.md">TUIColor</a>): Integer; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**value**|[TUIColor](../../FlexCel.Core/TUIColor/index.md)|Color we want to use\.|


## Returns

Most similar color on the Excel palette\.

## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.NearestColorIndex\(TUIColor, BooleanArray\)
**IMPORTANT:** Since FlexCel 5\.1, using [TExcelFile.OptimizeColorPalette](../../FlexCel.Core/TExcelFile/OptimizeColorPalette.md) before saving should normally be used instead of this method to get an optimized palette\. Just enter the true colors in FlexCel, and call [TExcelFile.OptimizeColorPalette](../../FlexCel.Core/TExcelFile/OptimizeColorPalette.md) before saving\.

Returns the most similar entry on the excel palette for a given color\.
If UsedColors is not null, it will try to modify the Excel color palette to get a better match on the color, modifying among the not used colors\.
Note that modifying the standard palette might result on a file that is not easy to edit on Excel later, since it does not have the standard Excel colors\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.NearestColorIndex(const value: <a href="../../FlexCel.Core/TUIColor/index.md">TUIColor</a>; const UsedColors: TArray&lt;Boolean>): Integer; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**value**|[TUIColor](../../FlexCel.Core/TUIColor/index.md)|Color we want to use\.|
|const|**UsedColors**|TArray\<Boolean>|If null, this behaves like the standard NearestColorIndex\.<br />To get a list of used colors for the first call, use [TExcelFile.GetUsedPaletteColors](../../FlexCel.Core/TExcelFile/GetUsedPaletteColors.md)\.<br />After the first call, keep using the same UsedColors structure and do not call GetUsedPaletteColors again, to avoid overwriting colors that are not yet inserted into the xls file with new ones\. You can call GetUsedPaletteColors only after you added the format with [TExcelFile.AddFormat](../../FlexCel.Core/TExcelFile/AddFormat.md)|


## Returns

Most similar color on the Excel palette\.

## See also

* [TXlsFile](../TXlsFile/index.md)

