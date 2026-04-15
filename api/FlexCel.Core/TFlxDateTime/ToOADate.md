---
uid: TFlxDateTime.ToOADate
description: TFlxDateTime.ToOADate
---

# TFlxDateTime\.ToOADate Method

## Overloads

* [TFlxDateTime\.ToOADate\(TDateTime, Boolean\)](#tflxdatetimetooadatetdatetime-boolean)
* [TFlxDateTime\.ToOADate\(TDateTime, Boolean, Boolean\)](#tflxdatetimetooadatetdatetime-boolean-boolean)

# TFlxDateTime\.ToOADate\(TDateTime, Boolean\)
Converts a DateTime into a Double on Excel format for dates \(Ole Automation Format\)\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TFlxDateTime/index.md">TFlxDateTime</a>.ToOADate(const value: TDateTime; const Dates1904: Boolean): Double; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**value**|TDateTime|DateTime you want to convert\.|
|const|**Dates1904**|Boolean|When true dates start at 1904 \(pre\-OSX macs\) instead of 1900 \(Windows\)|


## Returns

The value as a double on Excel format\.

## See also

* [TFlxDateTime](../TFlxDateTime/index.md)

# TFlxDateTime\.ToOADate\(TDateTime, Boolean, Boolean\)
Converts a DateTime into a Double on Excel format for dates \(Ole Automation Format\)\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TFlxDateTime/index.md">TFlxDateTime</a>.ToOADate(const value: TDateTime; const Dates1904: Boolean; const FirstIsDec1899: Boolean): Double; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**value**|TDateTime|DateTime you want to convert\.|
|const|**Dates1904**|Boolean|When true dates start at 1904 \(pre\-OSX macs\) instead of 1900 \(Windows\)|
|const|**FirstIsDec1899**|Boolean|If true, the minimum date returned will be Dec 31, 1899\. If false, the minimum is Jan 1, 1900\.<br />Note that none of them is valid of a date of 0\. Excel shows 1900\-01\-00 in that case\.|


## Returns

The value as a double on Excel format\.

## See also

* [TFlxDateTime](../TFlxDateTime/index.md)

