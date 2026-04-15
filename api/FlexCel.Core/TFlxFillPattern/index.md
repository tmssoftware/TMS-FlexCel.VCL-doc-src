---
uid: TFlxFillPattern
description: TFlxFillPattern
---

# TFlxFillPattern Record

Fill pattern and color for the background of a cell\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TFlxFillPattern = record;</code></pre>

## Fields

|Name|Description|
|---|---|
|[Pattern](Pattern.md)|Fill style\.<br />|
|[FgColor](FgColor.md)|Color for the foreground of the pattern\. It is used when the pattern is solid, but not when it is automatic\.<br />**Important:** This color is what you need, in the most common case where the pattern is solid\. [BgColor](BgColor.md) is ignored for solid patterns\.<br /><br /><br />This can look counterintuitive, but both FgColor and BgColor are colors for the background of the cell \(the fill pattern\)\.<br />To change the "foreground color" of a cell, you change the font color, not FgColor\.<br />So why are there 2 colors for the background? This is because Excel accepts fill patterns, where for example you might have a fill with a red background and black horizontal lines over it\.<br />Fot that case, BgColor would be red and FgColor will be black\.[...[more]](FgColor.md)|
|[BgColor](BgColor.md)|Color for the background of the pattern\.  If the pattern is solid it has no effect, but it is used when pattern is automatic\.<br />**Important:** THIS COLOR IS IGNORED FOR SOLID PATTERNS, which are the most common case\. If a pattern is solid you need to use [FgColor](FgColor.md)\.<br />Please read the documentation in [FgColor](FgColor.md) for a more complete explanation on why BgColor is ignored\.<br />|


## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|Creates an empty fill pattern\.<br />|
|[Clone](Clone.md)|Creates a deep copy of this object\.<br />|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


## Properties

|Name|Description|
|---|---|
|[Gradient](Gradient.md)|Gradient definition\. This is only valid if [Pattern](Pattern.md) is TFlxPatternStyle\.&#8203;Gradient\.&#8203;<br />|


