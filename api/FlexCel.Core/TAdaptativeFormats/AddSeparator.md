---
uid: TAdaptativeFormats.AddSeparator
description: TAdaptativeFormats.AddSeparator
---

# TAdaptativeFormats\.AddSeparator Method

## Overloads

* [TAdaptativeFormats\.AddSeparator\(string, Integer\)](#tadaptativeformatsaddseparatorstring-integer)
* [TAdaptativeFormats\.AddSeparator\(string, Integer, Integer\)](#tadaptativeformatsaddseparatorstring-integer-integer)

# TAdaptativeFormats\.AddSeparator\(string, Integer\)
Adds a char separator at a given position\. Separator array will be kept in order when you add a value\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TAdaptativeFormats/index.md">TAdaptativeFormats</a>.AddSeparator(const sep: string; const sp: Integer); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sep**|string|Character that will be used to calculat the width of the string\.|
|const|**sp**|Integer|Position in the final string\. \(0 based\)|


## See also

* [TAdaptativeFormats](../TAdaptativeFormats/index.md)

# TAdaptativeFormats\.AddSeparator\(string, Integer, Integer\)
Adds a separator at a given position\. Separator array will be kept in order when you add a value\. This routine considers utf32 characters\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TAdaptativeFormats/index.md">TAdaptativeFormats</a>.AddSeparator(const Format: string; const fp: Integer; const sp: Integer); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**Format**|string|String with the characters\.|
|const|**fp**|Integer|Position in the format string\. \(0 based\)|
|const|**sp**|Integer|Position in the final string\. \(0 based\)|


## See also

* [TAdaptativeFormats](../TAdaptativeFormats/index.md)

