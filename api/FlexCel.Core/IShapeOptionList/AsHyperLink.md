---
uid: IShapeOptionList.AsHyperLink
description: IShapeOptionList.AsHyperLink
---

# IShapeOptionList\.AsHyperLink Method

## Overloads

* [IShapeOptionList\.AsHyperLink\(TShapeOption, TDrawingHyperlink\)](#ishapeoptionlistashyperlinktshapeoption-tdrawinghyperlink)
* [IShapeOptionList\.AsHyperLink\(TCoreExcelFile, TShapeOption, TDrawingHyperlink\)](#ishapeoptionlistashyperlinktcoreexcelfile-tshapeoption-tdrawinghyperlink)

# IShapeOptionList\.AsHyperLink\(TShapeOption, TDrawingHyperlink\)
Returns an hyperlink property if it exists, otherwise the default value\.
You will normally want to use this property with [TShapeOption.pihlShape](../TShapeOption.md) since that is the property that holds the link for the objects\. Note that this  overload won't return a LinkBase, you need to call the overload taking an ExcelFile for that\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../IShapeOptionList/index.md">IShapeOptionList</a>.AsHyperLink(const key: <a href="../TShapeOption.md">TShapeOption</a>; const Default: <a href="../TDrawingHyperlink/index.md">TDrawingHyperlink</a>): <a href="../TDrawingHyperlink/index.md">TDrawingHyperlink</a>; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**key**|[TShapeOption](../TShapeOption.md)|Property Name\.|
|const|**Default**|[TDrawingHyperlink](../TDrawingHyperlink/index.md)|What to return if the property does not exist\.|


## See also

* [IShapeOptionList](../IShapeOptionList/index.md)

# IShapeOptionList\.AsHyperLink\(TCoreExcelFile, TShapeOption, TDrawingHyperlink\)
Returns an hyperlink property if it exists, otherwise the default value\.
You will normally want to use this property with [TShapeOption.pihlShape](../TShapeOption.md) since that is the property that holds the link for the objects\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../IShapeOptionList/index.md">IShapeOptionList</a>.AsHyperLink(const xls: TCoreExcelFile; const key: <a href="../TShapeOption.md">TShapeOption</a>; const Default: <a href="../TDrawingHyperlink/index.md">TDrawingHyperlink</a>): <a href="../TDrawingHyperlink/index.md">TDrawingHyperlink</a>; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**xls**|TCoreExcelFile|Excel file containing the hyperlink\. Might be null\. If not null, it is used to search for a hyperlink base\.|
|const|**key**|[TShapeOption](../TShapeOption.md)|Property Name\.|
|const|**Default**|[TDrawingHyperlink](../TDrawingHyperlink/index.md)|What to return if the property does not exist\.|


## See also

* [IShapeOptionList](../IShapeOptionList/index.md)

