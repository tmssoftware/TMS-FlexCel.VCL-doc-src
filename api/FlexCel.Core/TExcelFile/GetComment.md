---
uid: TExcelFile.GetComment
description: TExcelFile.GetComment
---

# TExcelFile\.GetComment Method

Returns the comment at the specified row and column, or an empty string if there is no comment on that cell\.


## Remarks

Use this method when you are searching for a comment on a fixed position\. To loop along all comments on a sheet, see [CommentRowCount](CommentRowCount.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetComment(const row: Integer; const col: Integer): <a href="../TRichString/index.md">TRichString</a>; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row index \(1 based\)|
|const|**col**|Integer|Column index \(1 based\)|


## Returns

The comment on the specified cell, String\.Empty if there is no comment on it\.

## See also

* [TExcelFile](../TExcelFile/index.md)
* [CommentRowCount](CommentRowCount.md)
* [CommentCountRow](CommentCountRow.md)
* [GetCommentRow](GetCommentRow.md)
* [GetCommentRowCol](GetCommentRowCol.md)
* [SetCommentRow\(Integer, Integer, string, IImageProperties, Boolean\)](SetCommentRow.md#texcelfilesetcommentrowinteger-integer-string-iimageproperties-boolean)
* [SetComment\(Integer, Integer, TRichString\)](SetComment.md#texcelfilesetcommentinteger-integer-trichstring)
* [GetCommentPropertiesRow](GetCommentPropertiesRow.md)
* [SetCommentPropertiesRow](SetCommentPropertiesRow.md)
* [SetCommentProperties](SetCommentProperties.md)

