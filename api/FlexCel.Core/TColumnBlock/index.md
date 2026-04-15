---
uid: TColumnBlock
description: TColumnBlock
---

# TColumnBlock Record

This class represents a block of columns with the same formatting, options and width\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TColumnBlock = record;</code></pre>

## Fields

|Name|Description|
|---|---|
|[FirstCol](FirstCol.md)|First column of the range \(1 based\)\.<br />|
|[LastCol](LastCol.md)|Last column of the range \(1 based\)\.<br />|
|[Width](Width.md)|Width of the columns\.<br />|
|[Options](Options.md)|Options of the columns\.<br />|
|[XF](XF.md)|Format of the columns\.<br />|


## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new TColumnBlock\.<br />|
|[Equals](Equals.md)|returns true if both objects have the same values\.<br />|
|[GetHashCode](GetHashCode.md)|returns the hashcode\.<br />|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


## Properties

|Name|Description|
|---|---|
|[Hidden](Hidden.md)|Returns true if the columns are hidden|


