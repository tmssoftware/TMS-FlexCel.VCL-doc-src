---
uid: TDrawingRichString.ToRichString
description: TDrawingRichString.ToRichString
---

# TDrawingRichString\.ToRichString Method

## Overloads

* [TDrawingRichString\.ToRichString\(TCoreExcelFile, IShapeFont\)](#tdrawingrichstringtorichstringtcoreexcelfile-ishapefont)
* [TDrawingRichString\.ToRichString\(TCoreExcelFile, IShapeFont, TFlxFont\)](#tdrawingrichstringtorichstringtcoreexcelfile-ishapefont-tflxfont)
* [TDrawingRichString\.ToRichString\(TCoreExcelFile, IShapeFont, TFlxFont, TFunc\<string, TRichString>\)](#tdrawingrichstringtorichstringtcoreexcelfile-ishapefont-tflxfont-tfuncstring-trichstring)
* [TDrawingRichString\.ToRichString\(TCoreExcelFile, IShapeFont, TFlxFont, TFunc\<string, TRichString>, Boolean\)](#tdrawingrichstringtorichstringtcoreexcelfile-ishapefont-tflxfont-tfuncstring-trichstring-boolean)

# TDrawingRichString\.ToRichString\(TCoreExcelFile, IShapeFont\)
Converts this TDrawingRichString into a [TRichString](../TRichString/index.md)\. Note that the conversion is not perfect  as a TDrawingRichString has different information from a TRichString\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TDrawingRichString/index.md">TDrawingRichString</a>.ToRichString(const xls: TCoreExcelFile; ShapeThemeFont: <a href="../IShapeFont/index.md">IShapeFont</a>): <a href="../TRichString/index.md">TRichString</a>; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**xls**|TCoreExcelFile|Excel file with the fonts\.|
||**ShapeThemeFont**|[IShapeFont](../IShapeFont/index.md)|Theme font used by default when no formatting is specified\. Set it to null to use the default\.|


## See also

* [TDrawingRichString](../TDrawingRichString/index.md)

# TDrawingRichString\.ToRichString\(TCoreExcelFile, IShapeFont, TFlxFont\)
Converts this TDrawingRichString into a [TRichString](../TRichString/index.md)\. Note that the conversion is not perfect  as a TDrawingRichString has different information from a TRichString\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TDrawingRichString/index.md">TDrawingRichString</a>.ToRichString(const xls: TCoreExcelFile; ShapeThemeFont: <a href="../IShapeFont/index.md">IShapeFont</a>; const DefaultFont: <a href="../TFlxFont/index.md">TFlxFont</a>): <a href="../TRichString/index.md">TRichString</a>; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**xls**|TCoreExcelFile|Excel file with the fonts\.|
||**ShapeThemeFont**|[IShapeFont](../IShapeFont/index.md)|Theme font used by default when no formatting is specified\. Set it to null to use the default\.|
|const|**DefaultFont**|[TFlxFont](../TFlxFont/index.md)|Font to be used by default\. If left null, the default font for the workbook will be used\.|


## See also

* [TDrawingRichString](../TDrawingRichString/index.md)

# TDrawingRichString\.ToRichString\(TCoreExcelFile, IShapeFont, TFlxFont, TFunc\<string, TRichString>\)
Converts this TDrawingRichString into a [TRichString](../TRichString/index.md)\. Note that the conversion is not perfect  as a TDrawingRichString has different information from a TRichString\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TDrawingRichString/index.md">TDrawingRichString</a>.ToRichString(const xls: TCoreExcelFile; ShapeThemeFont: <a href="../IShapeFont/index.md">IShapeFont</a>; const DefaultFont: <a href="../TFlxFont/index.md">TFlxFont</a>; const FieldReplacer: TFunc&lt;string, <a href="../TRichString/index.md">TRichString</a>&gt;): <a href="../TRichString/index.md">TRichString</a>; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**xls**|TCoreExcelFile|Excel file with the fonts\.|
||**ShapeThemeFont**|[IShapeFont](../IShapeFont/index.md)|Theme font used by default when no formatting is specified\. Set it to null to use the default\.|
|const|**DefaultFont**|[TFlxFont](../TFlxFont/index.md)|Font to be used by default\. If left null, the default font for the workbook will be used\.|
|const|**FieldReplacer**|TFunc\<string, [TRichString](../TRichString/index.md)>|Use this lambda function to replace text in fields\. It will take the field name as a parameter, and you need to return the field value in the result\. Set it to null if you don't want to replace fields\.|


## See also

* [TDrawingRichString](../TDrawingRichString/index.md)

# TDrawingRichString\.ToRichString\(TCoreExcelFile, IShapeFont, TFlxFont, TFunc\<string, TRichString>, Boolean\)
Converts this TDrawingRichString into a [TRichString](../TRichString/index.md)\. Note that the conversion is not perfect  as a TDrawingRichString has different information from a TRichString\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TDrawingRichString/index.md">TDrawingRichString</a>.ToRichString(const xls: TCoreExcelFile; ShapeThemeFont: <a href="../IShapeFont/index.md">IShapeFont</a>; const DefaultFont: <a href="../TFlxFont/index.md">TFlxFont</a>; const FieldReplacer: TFunc&lt;string, <a href="../TRichString/index.md">TRichString</a>&gt;; const UppercaseIfAllCaps: Boolean): <a href="../TRichString/index.md">TRichString</a>; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**xls**|TCoreExcelFile|Excel file with the fonts\.|
||**ShapeThemeFont**|[IShapeFont](../IShapeFont/index.md)|Theme font used by default when no formatting is specified\. Set it to null to use the default\.|
|const|**DefaultFont**|[TFlxFont](../TFlxFont/index.md)|Font to be used by default\. If left null, the default font for the workbook will be used\.|
|const|**FieldReplacer**|TFunc\<string, [TRichString](../TRichString/index.md)>|Use this lambda function to replace text in fields\. It will take the field name as a parameter, and you need to return the field value in the result\. Set it to null if you don't want to replace fields\.|
|const|**UppercaseIfAllCaps**|Boolean|If true and the style of the TDrawingRichString is all\-caps, this will return the string converted to uppercase\. Because a RichString doesn't have information about all\-caps\.|


## See also

* [TDrawingRichString](../TDrawingRichString/index.md)

