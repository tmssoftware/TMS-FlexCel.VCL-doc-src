---
uid: TFlxApplyFormat.Apply
description: TFlxApplyFormat.Apply
---

# TFlxApplyFormat\.Apply Method

This method will modify existingFormat with the properties from newFormat that are specified on this class

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TFlxApplyFormat/index.md">TFlxApplyFormat</a>.Apply(var existingFormat: <a href="../TFlxFormat/index.md">TFlxFormat</a>; const newFormat: <a href="../TFlxFormat/index.md">TFlxFormat</a>): Boolean;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|var|**existingFormat**|[TFlxFormat](../TFlxFormat/index.md)|Existing format that will be updated with the properties of newFormat specified\.|
|const|**newFormat**|[TFlxFormat](../TFlxFormat/index.md)|New format to apply|


## Returns

True if there was any change on existingFormat, false otherwise\.

## See also

* [TFlxApplyFormat](../TFlxApplyFormat/index.md)

