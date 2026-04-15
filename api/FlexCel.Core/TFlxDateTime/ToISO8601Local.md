---
uid: TFlxDateTime.ToISO8601Local
description: TFlxDateTime.ToISO8601Local
---

# TFlxDateTime\.ToISO8601Local Method

Returns a date formatted as ISO8601 from an OLE Automation Date\. It won't convert to UTC time, but use local times instead\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TFlxDateTime/index.md">TFlxDateTime</a>.ToISO8601Local(const OADate: Double; const Dates1904: Boolean): string; static;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**OADate**|Double|Serial number for the date\.|
|const|**Dates1904**|Boolean|True if using 1904 as start date\. Excel for windows normally uses 1900\.|


## See also

* [TFlxDateTime](../TFlxDateTime/index.md)

