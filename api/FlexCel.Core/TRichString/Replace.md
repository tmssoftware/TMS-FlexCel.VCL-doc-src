---
uid: TRichString.Replace
description: TRichString.Replace
---

# TRichString\.Replace Method

## Overloads

* [TRichString\.Replace\(string, string\)](#trichstringreplacestring-string)
* [TRichString\.Replace\(string, string, Boolean\)](#trichstringreplacestring-string-boolean)

# TRichString\.Replace\(string, string\)
Replaces all oldValue strings with newValue strings inside the RichString\. \(case sensitive\)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TRichString/index.md">TRichString</a>.Replace(const oldValue: string; const newValue: string): <a href="../TRichString/index.md">TRichString</a>; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**oldValue**|string|String to replace\.|
|const|**newValue**|string|String that will replace oldValue|


## Returns

A new TRichString with all oldValues replaced with newValues\.

## See also

* [TRichString](../TRichString/index.md)

# TRichString\.Replace\(string, string, Boolean\)
Replaces all oldValue strings with newValue strings inside the RichString\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TRichString/index.md">TRichString</a>.Replace(oldValue: string; newValue: string; const CaseInsensitive: Boolean): <a href="../TRichString/index.md">TRichString</a>; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
||**oldValue**|string|String to replace\.|
||**newValue**|string|String that will replace oldValue|
|const|**CaseInsensitive**|Boolean|If true, it will not take care of case for the search\.|


## Returns

A new TRichString with all oldValues replaced with newValues\.

## See also

* [TRichString](../TRichString/index.md)

