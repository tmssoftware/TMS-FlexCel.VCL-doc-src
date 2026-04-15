---
uid: TTableApplyFill
description: TTableApplyFill
---

# TTableApplyFill Record

Determines which parts of the pattern will be applied in the table\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TTableApplyFill = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create\(Boolean\)](Create.md#ttableapplyfillcreateboolean)<br />  [Create\(Boolean, Boolean, Boolean\)](Create.md#ttableapplyfillcreateboolean-boolean-boolean)<br />|
|[Equals](Equals.md)|Returns true if both objects are the same|
|[GetHashCode](GetHashCode.md)|Returns the hashcode of the struct\.<br />|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


## Properties

|Name|Description|
|---|---|
|[Pattern](Pattern.md)|Fill style\.<br />|
|[FgColor](FgColor.md)|Color for the foreground of the pattern\.<br />|
|[BgColor](BgColor.md)|Color for the background of the pattern\.  If the pattern is solid, has no effect\.<br />|
|[IsEmpty](IsEmpty.md)|Returns true if the format does not apply any setting\.<br />|


