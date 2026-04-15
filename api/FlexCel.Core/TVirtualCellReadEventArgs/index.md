---
uid: TVirtualCellReadEventArgs
description: TVirtualCellReadEventArgs
---

# TVirtualCellReadEventArgs Class

Arguments passed in the event\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TVirtualCellReadEventArgs = class(EventArgs);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new instance\.<br />|


## Properties

|Name|Description|
|---|---|
|[Cell](Cell.md)|Value and position of a cell\.<br />|
|[NextSheet](NextSheet.md)|Sheet where the next cell will be\. By default, this value is set automatically, but you can change to other value to skip some sheets, or set it to null or empty to end reading the file\.<br /><br />If for example you are at sheet "Sheet1" and set NextSheet to be "Sheet5", then the next time this event is called it will be with the first cell of Sheet5\. To stop reading this sheet and move to the next, set "NextSheet" to be [SheetNames](SheetNames.md)\[[Cell](Cell.md)\.Sheet\]|
|[SheetNames](SheetNames.md)|Array with all the sheet names in the file\. You can use this array and [Cell](Cell.md)\.Sheet to know the current and next sheet names\.<br />|


