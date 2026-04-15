---
uid: TCellAddress.TryParseSheet
description: TCellAddress.TryParseSheet
---

# TCellAddress\.TryParseSheet Method

Parses a string like Sheet1\!A1 into a sheet component and the rest\. If the sheet is quoted \('sheet 1'\) it will be unquoted\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TCellAddress/index.md">TCellAddress</a>.TryParseSheet(const value: string; out sheet: string; out rest: string): Boolean; static;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**value**|string|String to parse|
|out|**sheet**|string|Part of the string that is the sheet\.|
|out|**rest**|string|Part of the string that is not the sheet\.|


## See also

* [TCellAddress](../TCellAddress/index.md)

