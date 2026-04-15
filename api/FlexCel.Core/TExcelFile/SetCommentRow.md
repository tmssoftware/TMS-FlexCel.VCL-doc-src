---
uid: TExcelFile.SetCommentRow
description: TExcelFile.SetCommentRow
---

# TExcelFile\.SetCommentRow Method

## Overloads

* [TExcelFile\.SetCommentRow\(Integer, Integer, TRichString, IImageProperties, Boolean\)](#texcelfilesetcommentrowinteger-integer-trichstring-iimageproperties-boolean)
* [TExcelFile\.SetCommentRow\(Integer, Integer, string, IImageProperties, Boolean\)](#texcelfilesetcommentrowinteger-integer-string-iimageproperties-boolean)

# TExcelFile\.SetCommentRow\(Integer, Integer, TRichString, IImageProperties, Boolean\)
Changes the properties \(text and position of the popup\) for an existing comment at commentIndex\.
To delete a comment, set a "new TRichString\(\)" as the "value" param\. To add a new comment, use [SetComment\(Integer, Integer, TRichString\)](SetComment.md#texcelfilesetcommentinteger-integer-trichstring)\.


## Remarks

This method is used together with [CommentCountRow](CommentCountRow.md)\. See the reference on it for an example\.

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetCommentRow(const row: Integer; const commentIndex: Integer; const value: <a href="../TRichString/index.md">TRichString</a>; commentProperties: <a href="../IImageProperties/index.md">IImageProperties</a>; const removeEmpty: Boolean = True); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row Index \(1 based\)|
|const|**commentIndex**|Integer|Comment index \(1 based\)|
|const|**value**|[TRichString](../TRichString/index.md)|Text of the comment\. Set it to "new TRichString\(\)" to remove the comment\.|
||**commentProperties**|[IImageProperties](../IImageProperties/index.md)|Properties of the popup\.|
|const|**removeEmpty**|Boolean|**Optional**: Default value is True<br /><br />If true, comments of length 0 will be removed\.|


## See also

* [TExcelFile](../TExcelFile/index.md)
* [CommentRowCount](CommentRowCount.md)
* [CommentCountRow](CommentCountRow.md)
* [GetCommentRow](GetCommentRow.md)
* [GetCommentRowCol](GetCommentRowCol.md)
* [GetComment](GetComment.md)
* [SetComment\(Integer, Integer, TRichString\)](SetComment.md#texcelfilesetcommentinteger-integer-trichstring)
* [GetCommentPropertiesRow](GetCommentPropertiesRow.md)
* [SetCommentPropertiesRow](SetCommentPropertiesRow.md)
* [SetCommentProperties](SetCommentProperties.md)

# TExcelFile\.SetCommentRow\(Integer, Integer, string, IImageProperties, Boolean\)
Changes the properties \(text and position of the popup\) for an existing comment at commentIndex\.
To delete a comment, set a String\.Empty as the "value" param\. To add a new comment, use [SetComment\(Integer, Integer, TRichString\)](SetComment.md#texcelfilesetcommentinteger-integer-trichstring)\.


## Remarks

This method is used together with [CommentCountRow](CommentCountRow.md)\. See the reference on it for an example\.

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetCommentRow(const row: Integer; const commentIndex: Integer; const value: string; commentProperties: <a href="../IImageProperties/index.md">IImageProperties</a>; const removeEmpty: Boolean = True); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row Index \(1 based\)|
|const|**commentIndex**|Integer|Comment index \(1 based\)|
|const|**value**|string|Text of the comment\. Set it to String\.Empty to remove the comment\.|
||**commentProperties**|[IImageProperties](../IImageProperties/index.md)|Properties of the popup\.|
|const|**removeEmpty**|Boolean|**Optional**: Default value is True<br /><br />If true, comments of length 0 will be removed\.|


## See also

* [TExcelFile](../TExcelFile/index.md)
* [CommentRowCount](CommentRowCount.md)
* [CommentCountRow](CommentCountRow.md)
* [GetCommentRow](GetCommentRow.md)
* [GetCommentRowCol](GetCommentRowCol.md)
* [GetComment](GetComment.md)
* [SetComment\(Integer, Integer, TRichString\)](SetComment.md#texcelfilesetcommentinteger-integer-trichstring)
* [GetCommentPropertiesRow](GetCommentPropertiesRow.md)
* [SetCommentPropertiesRow](SetCommentPropertiesRow.md)
* [SetCommentProperties](SetCommentProperties.md)

