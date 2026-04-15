---
uid: TCharAndPos
description: TCharAndPos
---

# TCharAndPos Record

A simple structure containing a position and a character\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TCharAndPos = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Equals](Equals.md)|True if both structs are the same\.<br />|
|[GetHashCode](GetHashCode.md)|Returns the hashcode for the object\.<br />|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


## Properties

|Name|Description|
|---|---|
|[Pos](Pos.md)|Position of the character in the string \(0 based\)\.<br />|
|[Char](Char.md)|Character that should go at position\. Note that if this is a surrogate pair \(UTF32\) the string might have 2 UTF16 characters\.<br />|


