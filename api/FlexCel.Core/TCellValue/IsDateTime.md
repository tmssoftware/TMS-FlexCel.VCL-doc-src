---
uid: TCellValue.IsDateTime
description: TCellValue.IsDateTime
---

# TCellValue\.IsDateTime Method

Returns true if the value is a DateTime\.
**Note:**:This value will never be true when reading cells from a file\.
When reading a file, dates are stored as number so they will be returned as numbers\.
This property only will return true if you manually created a TCellValue from a TDateTime\.

To know if a cell has a date, you need to look at its format, not its value\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TCellValue/index.md">TCellValue</a>.IsDateTime: Boolean;</code></pre>

## See also

* [TCellValue](../TCellValue/index.md)

