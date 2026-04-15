---
uid: TExcelFile.VirtualCellStartReading
description: TExcelFile.VirtualCellStartReading
---

# TExcelFile.VirtualCellStartReading Event

When in virtual mode \([VirtualCellRead](VirtualCellRead.md) is assigned\) this event will be called after the sheet names have been read, but before starting to read the cells\. You can use  this event to know how many sheets you are reading\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TExcelFile/index.md">TExcelFile</a>.VirtualCellStartReading: TVirtualCellStartReadingEventHandler</code></pre>

## See also

* [TExcelFile](../TExcelFile/index.md)

