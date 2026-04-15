---
uid: TRTFRun
description: TRTFRun
---

# TRTFRun Record

One RTF run for the text in a cell\. FirstChar is the first \(base 0\) character to apply the format, and Font is the font definition for the text

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TRTFRun = record;</code></pre>

## Fields

|Name|Description|
|---|---|
|[RTFFirstChar&#8203;Comparer&#8203;Method](RTFFirstCharComparerMethod.md)|A comparer which will compare only the first character of each run\.<br />|
|[FirstChar](FirstChar.md)|First character on the string where we will apply the font\. \(0 based\)|
|[Font](Font.md)|Font for this string part\.<br />|


## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|Creates an RTFRun with the given values\.<br />|
|[ToByteArray](ToByteArray.md)|Converts a TRTFRun array into a byte array for serialization\.<br />|
|[Equals](Equals.md)|Determines whether two TRTFRun instances are equal\.<br />|
|[GetHashCode](GetHashCode.md)|Gets a hashcode for the TRTFRun instance\.<br />|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


