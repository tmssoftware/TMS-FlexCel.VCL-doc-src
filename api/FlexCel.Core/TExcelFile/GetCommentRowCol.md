---
uid: TExcelFile.GetCommentRowCol
description: TExcelFile.GetCommentRowCol
---

# TExcelFile\.GetCommentRowCol Method

Returns the column for comment at position commentIndex

## Remarks

This method is used together with [CommentCountRow](CommentCountRow.md)\. See the reference on it for an example\.

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetCommentRowCol(const row: Integer; const commentIndex: Integer): Integer; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row with the comment\. \(1 based\)|
|const|**commentIndex**|Integer|Index of the comment \(1 based\)|


## Returns

The column index corresponding to the comment\.

## See also

* [TExcelFile](../TExcelFile/index.md)
* [CommentRowCount](CommentRowCount.md)
* [CommentCountRow](CommentCountRow.md)
* [GetCommentRow](GetCommentRow.md)
* [GetComment](GetComment.md)
* [SetCommentRow\(Integer, Integer, string, IImageProperties, Boolean\)](SetCommentRow.md#texcelfilesetcommentrowinteger-integer-string-iimageproperties-boolean)
* [SetComment\(Integer, Integer, TRichString\)](SetComment.md#texcelfilesetcommentinteger-integer-trichstring)
* [GetCommentPropertiesRow](GetCommentPropertiesRow.md)
* [SetCommentPropertiesRow](SetCommentPropertiesRow.md)
* [SetCommentProperties](SetCommentProperties.md)

