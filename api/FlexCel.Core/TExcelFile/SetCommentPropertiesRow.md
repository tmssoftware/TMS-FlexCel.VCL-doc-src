---
uid: TExcelFile.SetCommentPropertiesRow
description: TExcelFile.SetCommentPropertiesRow
---

# TExcelFile\.SetCommentPropertiesRow Method

Sets the comment properties at the specified index\.


## Remarks

This method is used together with [CommentCountRow](CommentCountRow.md)\. See the reference on it for an example\.

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetCommentPropertiesRow(const row: Integer; const commentIndex: Integer; commentProperties: <a href="../IImageProperties/index.md">IImageProperties</a>); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row index \(1 based\)|
|const|**commentIndex**|Integer|Comment index \(1 based\)|
||**commentProperties**|[IImageProperties](../IImageProperties/index.md)|Comment properties\. This parameter can be a TImageProperties, or the more complete derived class TCommentProperties, if you need to set extra information like the text alignment\.|


## See also

* [TExcelFile](../TExcelFile/index.md)
* [CommentRowCount](CommentRowCount.md)
* [CommentCountRow](CommentCountRow.md)
* [GetCommentRow](GetCommentRow.md)
* [GetCommentRowCol](GetCommentRowCol.md)
* [GetComment](GetComment.md)
* [SetCommentRow\(Integer, Integer, string, IImageProperties, Boolean\)](SetCommentRow.md#texcelfilesetcommentrowinteger-integer-string-iimageproperties-boolean)
* [SetComment\(Integer, Integer, TRichString\)](SetComment.md#texcelfilesetcommentinteger-integer-trichstring)
* [GetCommentPropertiesRow](GetCommentPropertiesRow.md)
* [GetCommentProperties](GetCommentProperties.md)
* [SetCommentProperties](SetCommentProperties.md)

