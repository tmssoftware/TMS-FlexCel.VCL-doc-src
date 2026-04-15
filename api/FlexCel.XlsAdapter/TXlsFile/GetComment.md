---
uid: TXlsFile.GetComment
description: TXlsFile.GetComment
---

# TXlsFile\.GetComment Method

Returns the comment at the specified row and column, or an empty string if there is no comment on that cell\.


## Remarks

Use this method when you are searching for a comment on a fixed position\. To loop along all comments on a sheet, see [TExcelFile.CommentRowCount](../../FlexCel.Core/TExcelFile/CommentRowCount.md)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetComment(const row: Integer; const col: Integer): <a href="../../FlexCel.Core/TRichString/index.md">TRichString</a>; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row index \(1 based\)|
|const|**col**|Integer|Column index \(1 based\)|


## Returns

The comment on the specified cell, String\.Empty if there is no comment on it\.

## See also

* [TXlsFile](../TXlsFile/index.md)
* [TExcelFile.CommentRowCount](../../FlexCel.Core/TExcelFile/CommentRowCount.md)
* [TExcelFile.CommentCountRow](../../FlexCel.Core/TExcelFile/CommentCountRow.md)
* [TExcelFile.GetCommentRow](../../FlexCel.Core/TExcelFile/GetCommentRow.md)
* [TExcelFile.GetCommentRowCol](../../FlexCel.Core/TExcelFile/GetCommentRowCol.md)
* [TExcelFile.SetCommentRow\(Integer, Integer, string, IImageProperties, Boolean\)](../../FlexCel.Core/TExcelFile/SetCommentRow.md#texcelfilesetcommentrowinteger-integer-string-iimageproperties-boolean)
* [TExcelFile.SetComment\(Integer, Integer, TRichString\)](../../FlexCel.Core/TExcelFile/SetComment.md#texcelfilesetcommentinteger-integer-trichstring)
* [TExcelFile.GetCommentPropertiesRow](../../FlexCel.Core/TExcelFile/GetCommentPropertiesRow.md)
* [TExcelFile.SetCommentPropertiesRow](../../FlexCel.Core/TExcelFile/SetCommentPropertiesRow.md)
* [TExcelFile.SetCommentProperties](../../FlexCel.Core/TExcelFile/SetCommentProperties.md)

