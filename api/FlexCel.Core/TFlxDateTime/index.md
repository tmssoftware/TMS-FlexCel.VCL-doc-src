---
uid: TFlxDateTime
description: TFlxDateTime
---

# TFlxDateTime Record

Use this class to convert between a Date expressed on Excel format \(a double\) and a TDateTime\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TFlxDateTime = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[ToOADate](ToOADate.md)|**Overloaded<br />**  [ToOADate\(TDateTime, Boolean\)](ToOADate.md#tflxdatetimetooadatetdatetime-boolean)<br />  [ToOADate\(TDateTime, Boolean, Boolean\)](ToOADate.md#tflxdatetimetooadatetdatetime-boolean-boolean)<br />|
|[TryToOADate](TryToOADate.md)|Converts a DateTime into a Double on Excel format for dates \(Ole Automation Format\)\.<br />|
|[FromOADate](FromOADate.md)|Converts a Double on Excel format for dates \(Ole Automation Format\) into a DateTime\.<br />|
|[IsValidDate](IsValidDate.md)|Returns true is the double value can be converted into and Excel date\.<br />|
|[TryFromOADate](TryFromOADate.md)|Converts a Double on Excel format for dates \(Ole Automation Format\) into a DateTime\.<br />|
|[ToISO8601](ToISO8601.md)|Returns a date formatted as ISO8601|
|[ToISO8601Local](ToISO8601Local.md)|Returns a date formatted as ISO8601 from an OLE Automation Date\. It won't convert to UTC time, but use local times instead\.<br />|


