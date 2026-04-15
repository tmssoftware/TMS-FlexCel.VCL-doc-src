---
uid: TExcelColor.Index
description: TExcelColor.Index
---

# TExcelColor.Index Property

Returns the color when this structure contains an indexed color \(1 based\)\. This property is for compatibility with xls files \(Excel 2003 or older\), but if you are not changing the color palette, even for older files, it is preferred to use [RGB](RGB.md) or [Theme](Theme.md) instead\.


If you try to read the value of this property and [ColorType](ColorType.md) is not the right kind, an Exception will be raised\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TExcelColor/index.md">TExcelColor</a>.Index: Integer</code></pre>

## See also

* [TExcelColor](../TExcelColor/index.md)

