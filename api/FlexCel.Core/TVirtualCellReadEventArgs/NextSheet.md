---
uid: TVirtualCellReadEventArgs.NextSheet
description: TVirtualCellReadEventArgs.NextSheet
---

# TVirtualCellReadEventArgs.NextSheet Property

Sheet where the next cell will be\. By default, this value is set automatically, but you can change to other value to skip some sheets, or set it to null or empty to end reading the file\.

If for example you are at sheet "Sheet1" and set NextSheet to be "Sheet5", then the next time this event is called it will be with the first cell of Sheet5\. To stop reading this sheet and move to the next, set "NextSheet" to be [SheetNames](SheetNames.md)\[[Cell](Cell.md)\.Sheet\]

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TVirtualCellReadEventArgs/index.md">TVirtualCellReadEventArgs</a>.NextSheet: string</code></pre>

## See also

* [TVirtualCellReadEventArgs](../TVirtualCellReadEventArgs/index.md)

