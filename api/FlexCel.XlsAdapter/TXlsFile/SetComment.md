---
uid: TXlsFile.SetComment
description: TXlsFile.SetComment
---

# TXlsFile\.SetComment Method

Sets or deletes a comment at the specified cell\.


## Remarks

To delete a comment, set its value to String\.Empty\.

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetComment(const row: Integer; const col: Integer; const value: <a href="../../FlexCel.Core/TRichString/index.md">TRichString</a>; const author: string; commentProperties: <a href="../../FlexCel.Core/IImageProperties/index.md">IImageProperties</a>; const removeEmpty: Boolean = True); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row index \(1 based\)|
|const|**col**|Integer|Column index \(1 based\)|
|const|**value**|[TRichString](../../FlexCel.Core/TRichString/index.md)|Text of the comment\. Set it to String\.Empty to delete the comment\.|
|const|**author**|string|Author of the comment\.|
||**commentProperties**|[IImageProperties](../../FlexCel.Core/IImageProperties/index.md)|Properties of the popup\.|
|const|**removeEmpty**|Boolean|**Optional**: Default value is True<br /><br />|


## See also

* [TXlsFile](../TXlsFile/index.md)
* [TExcelFile.CommentRowCount](../../FlexCel.Core/TExcelFile/CommentRowCount.md)
* [TExcelFile.CommentCountRow](../../FlexCel.Core/TExcelFile/CommentCountRow.md)
* [TExcelFile.GetCommentRow](../../FlexCel.Core/TExcelFile/GetCommentRow.md)
* [TExcelFile.GetCommentRowCol](../../FlexCel.Core/TExcelFile/GetCommentRowCol.md)
* [TExcelFile.GetComment](../../FlexCel.Core/TExcelFile/GetComment.md)
* [TExcelFile.SetCommentRow\(Integer, Integer, string, IImageProperties, Boolean\)](../../FlexCel.Core/TExcelFile/SetCommentRow.md#texcelfilesetcommentrowinteger-integer-string-iimageproperties-boolean)
* [TExcelFile.GetCommentPropertiesRow](../../FlexCel.Core/TExcelFile/GetCommentPropertiesRow.md)
* [TExcelFile.SetCommentPropertiesRow](../../FlexCel.Core/TExcelFile/SetCommentPropertiesRow.md)
* [TExcelFile.SetCommentProperties](../../FlexCel.Core/TExcelFile/SetCommentProperties.md)

