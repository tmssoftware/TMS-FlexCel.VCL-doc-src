---
uid: TExcelFile.GetCommentRow
description: TExcelFile.GetCommentRow
---

# TExcelFile\.GetCommentRow Method

Returns the comment at position commentIndex on the specified row\.


## Remarks

This method is used together with [CommentCountRow](CommentCountRow.md)\. See the reference on it for an example\.

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetCommentRow(const row: Integer; const commentIndex: Integer): <a href="../TRichString/index.md">TRichString</a>; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row index \(1 based\)|
|const|**commentIndex**|Integer|Comment index \(1 based\)\. See [CommentCountRow](CommentCountRow.md)|


## Returns

Comment at the specified position\.

## See also

* [TExcelFile](../TExcelFile/index.md)
* [CommentRowCount](CommentRowCount.md)
* [CommentCountRow](CommentCountRow.md)
* [GetCommentRowCol](GetCommentRowCol.md)
* [GetComment](GetComment.md)
* [SetCommentRow\(Integer, Integer, string, IImageProperties, Boolean\)](SetCommentRow.md#texcelfilesetcommentrowinteger-integer-string-iimageproperties-boolean)
* [SetComment\(Integer, Integer, TRichString\)](SetComment.md#texcelfilesetcommentinteger-integer-trichstring)
* [GetCommentPropertiesRow](GetCommentPropertiesRow.md)
* [SetCommentPropertiesRow](SetCommentPropertiesRow.md)
* [SetCommentProperties](SetCommentProperties.md)

