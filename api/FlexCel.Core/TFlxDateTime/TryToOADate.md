---
uid: TFlxDateTime.TryToOADate
description: TFlxDateTime.TryToOADate
---

# TFlxDateTime\.TryToOADate Method

Converts a DateTime into a Double on Excel format for dates \(Ole Automation Format\)\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TFlxDateTime/index.md">TFlxDateTime</a>.TryToOADate(const value: TDateTime; const Dates1904: Boolean; out ResultDate: Double): Boolean; static;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**value**|TDateTime|DateTime you want to convert\.|
|const|**Dates1904**|Boolean|When true dates start at 1904 \(pre\-OSX macs\) instead of 1900 \(Windows\)|
|out|**ResultDate**|Double|Returns the value as double on Excel format\.|


## Returns

True if conversion was successful, false otherwise\.

## See also

* [TFlxDateTime](../TFlxDateTime/index.md)

