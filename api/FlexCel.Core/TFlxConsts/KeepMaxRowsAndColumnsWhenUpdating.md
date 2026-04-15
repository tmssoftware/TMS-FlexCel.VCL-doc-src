---
uid: TFlxConsts.KeepMaxRowsAndColumnsWhenUpdating
description: TFlxConsts.KeepMaxRowsAndColumnsWhenUpdating
---

# TFlxConsts.KeepMaxRowsAndColumnsWhenUpdating Field

Defines what FlexCel will do when it finds a reference to the last row or column in an Excel 97\-2003 spreadsheet, and it is upgrading to Excel 2007\.
If false \(the default\) row 65536 will be updated to row 1048576, and column 256 to column 16384\.
If true, references will stay the same\. **Note:** This is a global property, so it affects all threads running\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs"><a href="../TFlxConsts/index.md">TFlxConsts</a>.KeepMaxRowsAndColumnsWhenUpdating: Boolean;</code></pre>

## See also

* [TFlxConsts](../TFlxConsts/index.md)

