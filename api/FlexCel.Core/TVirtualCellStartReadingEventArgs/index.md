---
uid: TVirtualCellStartReadingEventArgs
description: TVirtualCellStartReadingEventArgs
---

# TVirtualCellStartReadingEventArgs Class

Arguments passed in the event\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TVirtualCellStartReadingEventArgs = class(EventArgs);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new instance\.<br />|


## Properties

|Name|Description|
|---|---|
|[SheetNames](SheetNames.md)|A list with all the sheets available in the file\.<br />|
|[NextSheet](NextSheet.md)|This is the next sheet that will be read by FlexCel\. You can change it to start reading the file by a different sheet, or set it to empty or null to finish reading the file\.<br />|


