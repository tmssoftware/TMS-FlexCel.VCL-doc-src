---
uid: TRichString
description: TRichString
---

# TRichString Record

A string cell value with its rich text information\.
RTFRuns is an array of TRTFRun structures, where each struct identifies a font style for a portion of text\.
For example, if you have: Value = "Hello" RTFRuns = \{FirstChar:1 Font:Font1, FirstChar:3, Font:Font2\}
"H" \(char 0\) will be formatted with the specific cell format\.

"el" \(chars 1 and 2\) will have Font1
"lo" \(chars 3 and 4\) will have Font2


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TRichString = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[GetRuns](GetRuns.md)|Internal as it doesn't clone the struct\.<br />|
|[SetFromHtml](SetFromHtml.md)|**Overloaded<br />**  [SetFromHtml\(string, TFlxFormat, TCoreExcelFile\)](SetFromHtml.md#trichstringsetfromhtmlstring-tflxformat-tcoreexcelfile)<br />  [SetFromHtml\(string, TFlxFormat, TCoreExcelFile, Boolean\)](SetFromHtml.md#trichstringsetfromhtmlstring-tflxformat-tcoreexcelfile-boolean)<br />|
|[Create](Create.md)|**Overloaded<br />**  [Create](Create.md#trichstringcreate)<br />  [Create\(string\)](Create.md#trichstringcreatestring)<br />  [Create\(string, TRTFRunArray\)](Create.md#trichstringcreatestring-trtfrunarray)<br />  [Create\(string, TFList\<TRTFRun>\)](Create.md#trichstringcreatestring-tflisttrtfrun)<br />  [Create\(string, TBytes, TCoreExcelFile\)](Create.md#trichstringcreatestring-tbytes-tcoreexcelfile)<br />  [Create\(string, TRichString, Integer\)](Create.md#trichstringcreatestring-trichstring-integer)<br />|
|[CreateWithoutCopy](CreateWithoutCopy.md)|This won't copy the values\. Make sure the values are not reused\.<br />|
|[FromHtml](FromHtml.md)|Returns a new TRichString from an HTML text\. Note that only some tags from HTML are converted, the ones that do not have correspondence on Excel rich text will be discarded\.**Note: This method is for advanced uses only\. Normally you would just use [TExcelFile.&#8203;Set&#8203;Cell&#8203;From&#8203;Html\(&#8203;&#8203;Integer, Integer, string, Integer\)](../TExcelFile/SetCellFromHtml.md#texcelfilesetcellfromhtmlinteger-integer-string-integer)**|
|[RTFRun](RTFRun.md)|A run of RTF\.<br />|
|[SetRTFRun](SetRTFRun.md)|Sets one RTF run\.<br />|
|[GetFontForChar](GetFontForChar.md)|Returns the index of the run for the character charIndex in the string\. If there is no font for the character, it will return \-1\.<br />|
|[ToString](ToString.md)|Returns the string without Rich text info\.<br />|
|[Substring](Substring.md)|**Overloaded<br />**  [Substring\(Integer\)](Substring.md#trichstringsubstringinteger)<br />  [Substring\(Integer, Integer\)](Substring.md#trichstringsubstringinteger-integer)<br />|
|[Add](Add.md)|Adds two richstrings together\. You can just use the overloaded "\+" operator to contatenate rich strings\.<br />|
|[Trim](Trim.md)|Trims all the whitespace at the beginning and end of the string\.<br />|
|[RightTrim](RightTrim.md)|Trims all the whitespace at the end of the string\.<br />|
|[Replace](Replace.md)|**Overloaded<br />**  [Replace\(string, string\)](Replace.md#trichstringreplacestring-string)<br />  [Replace\(string, string, Boolean\)](Replace.md#trichstringreplacestring-string-boolean)<br />|
|[ToHtml](ToHtml.md)|**Overloaded<br />**  [ToHtml\(TCoreExcelFile, TFlxFormat, THtmlVersion, THtmlStyle, TEncoding\)](ToHtml.md#trichstringtohtmltcoreexcelfile-tflxformat-thtmlversion-thtmlstyle-tencoding)<br />  [ToHtml\(TCoreExcelFile, TFlxFormat, THtmlVersion, THtmlStyle, TEncoding, IHtmlFontEvent\)](ToHtml.md#trichstringtohtmltcoreexcelfile-tflxformat-thtmlversion-thtmlstyle-tencoding-ihtmlfontevent)<br />|
|[Clone](Clone.md)|Returns a Deep copy of the Rich string\.<br />|
|[Equals](Equals.md)|Returns true when both richstrings are equal\.<br />|
|[GetHashCode](GetHashCode.md)|Hashcode for this richstring\.<br />|
|[IsEmpty](IsEmpty.md)|Returns true if the string doesn't have text or rich text runs\.<br />|


## Operators

|Name|Description|
|---|---|
|[Addition](op_Addition.md)|Adapts the \+ operator so it can add two instances of this record\.|
|[Implicit Conversion](op_Implicit.md)|**Overloaded<br />**  [Implicit conversion from string to TRichString](op_Implicit.md#implicit-conversion-from-string-to-trichstring)<br />  [Implicit conversion from TRichString to string](op_Implicit.md#implicit-conversion-from-trichstring-to-string)<br />|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


## Properties

|Name|Description|
|---|---|
|[Value](Value.md)|Text of the string without formatting\. Might be null\.<br />|
|[RTFRunCount](RTFRunCount.md)|Number of RTF runs\.<br />|
|[Length](Length.md)|Length of the RichString\.<br />|
|[Item\[const index\]](Itemconst-index.md)|Returns the character at position index\.<br />|


