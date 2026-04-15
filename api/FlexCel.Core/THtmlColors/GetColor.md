---
uid: THtmlColors.GetColor
description: THtmlColors.GetColor
---

# THtmlColors\.GetColor Method

## Overloads

* [THtmlColors\.GetColor\(string\)](#thtmlcolorsgetcolorstring)
* [THtmlColors\.GetColor\(TUIColor\)](#thtmlcolorsgetcolortuicolor)

# THtmlColors\.GetColor\(string\)
Returns a Color struct from an HTML string

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../THtmlColors/index.md">THtmlColors</a>.GetColor(const Value: string): <a href="../TUIColor/index.md">TUIColor</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**Value**|string|String with color on HTML format\. \(one of the 16 named colors or \#notation\)|


## Returns

The corresponding Color\.

## See also

* [THtmlColors](../THtmlColors/index.md)

# THtmlColors\.GetColor\(TUIColor\)
Returns an HTML color string from a Color struct\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../THtmlColors/index.md">THtmlColors</a>.GetColor(const Value: <a href="../TUIColor/index.md">TUIColor</a>): string; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**Value**|[TUIColor](../TUIColor/index.md)|The color we want to convert\.|


## Returns

String with color on HTML format\. \(one of the 16 named colors or \#notation\)\.

## See also

* [THtmlColors](../THtmlColors/index.md)

