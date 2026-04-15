---
uid: TXlsFile.SetCommentRow
description: TXlsFile.SetCommentRow
---

# TXlsFile\.SetCommentRow Method

Changes the properties \(text and position of the popup\) for an existing comment at commentIndex\.
To delete a comment, set a "new TRichString\(\)" as the "value" param\. To add a new comment, use [TExcelFile.SetComment\(Integer, Integer, TRichString\)](../../FlexCel.Core/TExcelFile/SetComment.md#texcelfilesetcommentinteger-integer-trichstring)\.


## Remarks

This method is used together with [TExcelFile.CommentCountRow](../../FlexCel.Core/TExcelFile/CommentCountRow.md)\. See the reference on it for an example\.

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetCommentRow(const row: Integer; const commentIndex: Integer; const value: <a href="../../FlexCel.Core/TRichString/index.md">TRichString</a>; commentProperties: <a href="../../FlexCel.Core/IImageProperties/index.md">IImageProperties</a>; const removeEmpty: Boolean = True); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row Index \(1 based\)|
|const|**commentIndex**|Integer|Comment index \(1 based\)|
|const|**value**|[TRichString](../../FlexCel.Core/TRichString/index.md)|Text of the comment\. Set it to "new TRichString\(\)" to remove the comment\.|
||**commentProperties**|[IImageProperties](../../FlexCel.Core/IImageProperties/index.md)|Properties of the popup\.|
|const|**removeEmpty**|Boolean|**Optional**: Default value is True<br /><br />If true, comments of length 0 will be removed\.|


## See also

* [TXlsFile](../TXlsFile/index.md)
* [TExcelFile.CommentRowCount](../../FlexCel.Core/TExcelFile/CommentRowCount.md)
* [TExcelFile.CommentCountRow](../../FlexCel.Core/TExcelFile/CommentCountRow.md)
* [TExcelFile.GetCommentRow](../../FlexCel.Core/TExcelFile/GetCommentRow.md)
* [TExcelFile.GetCommentRowCol](../../FlexCel.Core/TExcelFile/GetCommentRowCol.md)
* [TExcelFile.GetComment](../../FlexCel.Core/TExcelFile/GetComment.md)
* [TExcelFile.SetComment\(Integer, Integer, TRichString\)](../../FlexCel.Core/TExcelFile/SetComment.md#texcelfilesetcommentinteger-integer-trichstring)
* [TExcelFile.GetCommentPropertiesRow](../../FlexCel.Core/TExcelFile/GetCommentPropertiesRow.md)
* [TExcelFile.SetCommentPropertiesRow](../../FlexCel.Core/TExcelFile/SetCommentPropertiesRow.md)
* [TExcelFile.SetCommentProperties](../../FlexCel.Core/TExcelFile/SetCommentProperties.md)

