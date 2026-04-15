---
uid: TAdaptativeFormats
description: TAdaptativeFormats
---

# TAdaptativeFormats Record

Information about characters in a numeric format that need to be adapted when rendering\. For example, if the cell A1 has value 1 and format "\*\_0" it will print as "\_\_\_\_\_\_1" when the cell is wide, and as "\_1" when the cell is shorter\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TAdaptativeFormats = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[ApplySeparators](ApplySeparators.md)|Returns the string with the characters at the positions in Separator changed by the characters specified in Separators\.<br />|
|[AddSeparator](AddSeparator.md)|**Overloaded<br />**  [AddSeparator\(string, Integer\)](AddSeparator.md#tadaptativeformatsaddseparatorstring-integer)<br />  [AddSeparator\(string, Integer, Integer\)](AddSeparator.md#tadaptativeformatsaddseparatorstring-integer-integer)<br />|
|[Mix](Mix.md)|This assumes separators in New are all sorted and after separators in old\.<br />|
|[IsNull](IsNull.md)|Returns true if the record doesn't have a defined value\.<br />|
|[HasValue](HasValue.md)|Returns true if the record has a defined value\. This is the inverse of [IsNull](IsNull.md)|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


## Properties

|Name|Description|
|---|---|
|[WildcardPos](WildcardPos.md)|Position of the last wildcard \("\*"\) character in the format \(0 based\)\. If a wildcard is present in the format, the string has to be expanded with the character at position until it fits the width of the cell\.<br />A negative value means there is no wildcard in the format\.<br />|
|[Separators](Separators.md)|An array of positions and characters that must be used to pad the string\. In this field you have the the "\_" and "?" numeric format delimiters from Excel\.<br />The spaces at the positions in the position array should have the width of the character specified in this field\.<br />If null, there are no separators in this class\.<br />|
|[IsEmpty](IsEmpty.md)|Returns true if this class has no adaptative formats\.<br />|


