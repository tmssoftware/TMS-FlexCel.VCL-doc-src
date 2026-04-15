---
uid: TDrawingColor
description: TDrawingColor
---

# TDrawingColor Record

Represents a Color for a drawing or a theme\. Different from TExcelColor, this structure is defined in terms of DrawingML, not SpreadsheetML\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TDrawingColor = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[GetColorTransform](GetColorTransform.md)|Returns an array with all the color transforms in this object\.<br />|
|[CompareTo](CompareTo.md)|Returns \-1 if obj is more than color, 0 if both colors are the same, and 1 if obj is less than color\.<br />|
|[GetHashCode](GetHashCode.md)|Returns the hashcode of the object\.<br />|
|[Equals](Equals.md)|Returns true if both instances have the same color\.<br />|
|[FromPreset](FromPreset.md)|**Overloaded<br />**  [FromPreset\(TPresetColor\)](FromPreset.md#tdrawingcolorfrompresettpresetcolor)<br />  [FromPreset\(TPresetColor, TColorTransformArray\)](FromPreset.md#tdrawingcolorfrompresettpresetcolor-tcolortransformarray)<br />|
|[FromSystem](FromSystem.md)|**Overloaded<br />**  [FromSystem\(TSystemColor\)](FromSystem.md#tdrawingcolorfromsystemtsystemcolor)<br />  [FromSystem\(TSystemColor, TColorTransformArray\)](FromSystem.md#tdrawingcolorfromsystemtsystemcolor-tcolortransformarray)<br />|
|[FromColor](FromColor.md)|Returns a color class with a specified color\. There is no real need to call this method, since conversion between  [TDrawingColor](../TDrawingColor/index.md) and [TUIColor](../TUIColor/index.md) is implicit\. You can just assign Color to this class and viceversa\.<br />|
|[FromRgb](FromRgb.md)|**Overloaded<br />**  [FromRgb\(Byte, Byte, Byte\)](FromRgb.md#tdrawingcolorfromrgbbyte-byte-byte)<br />  [FromRgb\(Byte, Byte, Byte, TColorTransformArray\)](FromRgb.md#tdrawingcolorfromrgbbyte-byte-byte-tcolortransformarray)<br />|
|[FromScRgb](FromScRgb.md)|**Overloaded<br />**  [FromScRgb\(TScRGBColor\)](FromScRgb.md#tdrawingcolorfromscrgbtscrgbcolor)<br />  [FromScRgb\(TScRGBColor, TColorTransformArray\)](FromScRgb.md#tdrawingcolorfromscrgbtscrgbcolor-tcolortransformarray)<br />|
|[FromTheme](FromTheme.md)|**Overloaded<br />**  [FromTheme\(TThemeColor\)](FromTheme.md#tdrawingcolorfromthemetthemecolor)<br />  [FromTheme\(TThemeColor, TColorTransformArray\)](FromTheme.md#tdrawingcolorfromthemetthemecolor-tcolortransformarray)<br />|
|[FromHSL](FromHSL.md)|**Overloaded<br />**  [FromHSL\(THSLColor\)](FromHSL.md#tdrawingcolorfromhslthslcolor)<br />  [FromHSL\(THSLColor, TColorTransformArray\)](FromHSL.md#tdrawingcolorfromhslthslcolor-tcolortransformarray)<br />|
|[AddTransform](AddTransform.md)|Returns the DrawingColor that results of applying the transform to the existing DrawingColor\.<br />|
|[ToColor](ToColor.md)|Returns the UI Color specified by this structure\.<br />|
|[GetSystemColor](GetSystemColor.md)|Returns the color associated with a simple color\.<br />|
|[IndexedSolidPalette](IndexedSolidPalette.md)|Returns the indexed colors from 0 to 7\. Mostly for internal use\.<br />|
|[GetComponents](GetComponents.md)|Returns R, G and B components of the color\. If this is a theme or indexed color, it will be converted to RGB before getting the components\.<br />|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|
|[GreaterThan](op_GreaterThan.md)|Adapts the > operator so it returns true when the first parameter is bigger than the second\.|
|[LessThan](op_LessThan.md)|Adapts the \< operator so it returns true when the first parameter is smaller than the second\.|
|[Implicit Conversion](op_Implicit.md)|Automatically converts from TUIColor instances to TDrawingColor instances|


## Properties

|Name|Description|
|---|---|
|[ColorType](ColorType.md)|Identifies which kind of color is the one to apply in this structure\.<br />|
|[HSL](HSL.md)|Returns the color when this structure has an HSL color, as a 0xHHSSLL integer\.<br /><br /><br />If you try to read the value of this property and [ColorType](ColorType.md) is not the right kind, an Exception will be raised\.<br />|
|[RGB](RGB.md)|Returns the color when this structure has an RGB color, as a 0xRRGGBB integer\.<br /><br /><br />If you try to read the value of this property and [ColorType](ColorType.md) is not the right kind, an Exception will be raised\.<br />|
|[ScRGB](ScRGB.md)|Returns the color when this structure has an scRGB color\.<br /><br /><br />If you try to read the value of this property and [ColorType](ColorType.md) is not the right kind, an Exception will be raised\.<br />|
|[Preset](Preset.md)|Returns the color when this structure has a Preset color\.<br /><br /><br />If you try to read the value of this property and [ColorType](ColorType.md) is not the right kind, an Exception will be raised\.<br />|
|[System](System.md)|Returns the color when this structure has a System color\.<br /><br /><br />If you try to read the value of this property and [ColorType](ColorType.md) is not the right kind, an Exception will be raised\.<br />|
|[Theme](Theme.md)|Returns the color when this structure has a Themed color\.<br /><br /><br />If you try to read the value of this property and [ColorType](ColorType.md) is not the right kind, an Exception will be raised\.<br />|
|[Transparent](Transparent.md)|Returns the transparent color\.<br />|


