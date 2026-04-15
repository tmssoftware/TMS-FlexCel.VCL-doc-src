---
uid: TFlxDateTime.TryFromOADate
description: TFlxDateTime.TryFromOADate
---

# TFlxDateTime\.TryFromOADate Method

Converts a Double on Excel format for dates \(Ole Automation Format\) into a DateTime\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TFlxDateTime/index.md">TFlxDateTime</a>.TryFromOADate(value: Double; const Dates1904: Boolean; out ResultDate: TDateTime): Boolean; static;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
||**value**|Double|Double you want to convert\.|
|const|**Dates1904**|Boolean|When true dates start at 1904 \(pre\-OSX macs\) instead of 1900 \(Windows\)|
|out|**ResultDate**|TDateTime|Returns the value as DateTime\.|


## Returns

True if conversion was successful, false otherwise\.

## See also

* [TFlxDateTime](../TFlxDateTime/index.md)

