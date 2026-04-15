---
uid: TXlsNamedRange.IsValidRangeName
description: TXlsNamedRange.IsValidRangeName
---

# TXlsNamedRange\.IsValidRangeName Method

Returns true if the string is a valid name for a named range\. Valid names must start with a letter or an underscore

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TXlsNamedRange/index.md">TXlsNamedRange</a>.IsValidRangeName(const Name: string; out IsInternal: Boolean): Boolean; static;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**Name**|string|String we want to check\.|
|out|**IsInternal**|Boolean|Returns true if this is an internal name, like Print\_Range\. Internal names have only one character\.|


## See also

* [TXlsNamedRange](../TXlsNamedRange/index.md)

