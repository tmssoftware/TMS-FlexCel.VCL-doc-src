---
uid: TVirtualCellStartReadingEventArgs.Create
description: TVirtualCellStartReadingEventArgs.Create
---

# TVirtualCellStartReadingEventArgs\.Create Constructor

Creates a new instance\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TVirtualCellStartReadingEventArgs/index.md">TVirtualCellStartReadingEventArgs</a>.Create(const aSheetNames: TArray&lt;string&gt;; const aNextSheet: string);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aSheetNames**|TArray\<string>|Array with all the sheet names available in the file\.|
|const|**aNextSheet**|string|This is the next sheet that will be read by FlexCel\. You can change it to start reading the file by a different sheet, or set it to empty or null to finish reading the file\.|


## See also

* [TVirtualCellStartReadingEventArgs](../TVirtualCellStartReadingEventArgs/index.md)

