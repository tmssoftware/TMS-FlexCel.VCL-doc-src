---
uid: TExcelColor.ToColor
description: TExcelColor.ToColor
---

# TExcelColor\.ToColor Method

## Overloads

* [TExcelColor\.ToColor\(TCoreExcelFile\)](#texcelcolortocolortcoreexcelfile)
* [TExcelColor\.ToColor\(TCoreExcelFile, TUIColor\)](#texcelcolortocolortcoreexcelfile-tuicolor)

# TExcelColor\.ToColor\(TCoreExcelFile\)
Returns the value of this class as a system color\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelColor/index.md">TExcelColor</a>.ToColor(const Xls: TCoreExcelFile): <a href="../TUIColor/index.md">TUIColor</a>; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**Xls**|TCoreExcelFile|Excel file containing the themes and palettes for the color indexes\.|


## See also

* [TExcelColor](../TExcelColor/index.md)

# TExcelColor\.ToColor\(TCoreExcelFile, TUIColor\)
Returns the value of this class as a system color\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelColor/index.md">TExcelColor</a>.ToColor(xls: TCoreExcelFile; const automaticColor: <a href="../TUIColor/index.md">TUIColor</a>): <a href="../TUIColor/index.md">TUIColor</a>; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
||**xls**|TCoreExcelFile|Excel file containing the themes and palettes for the color indexes\.|
|const|**automaticColor**|[TUIColor](../TUIColor/index.md)|Color to be returned if this structure has an automatic color\.|


## See also

* [TExcelColor](../TExcelColor/index.md)

