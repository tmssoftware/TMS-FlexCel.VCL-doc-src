---
uid: TUIFont.GetTTFTable
description: TUIFont.GetTTFTable
---

# TUIFont\.GetTTFTable Method

Returns a True Type table for the font, if the platform gives the functionality\. Currently supported in OSX only\.
To see if the platform supports returning tables, see [SupportsTTFTables](SupportsTTFTables.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TUIFont/index.md">TUIFont</a>.GetTTFTable(const tableName: Int64): TBytes; virtual;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**tableName**|Int64||


## See also

* [TUIFont](../TUIFont/index.md)

