---
uid: TXlsFile.SetCommentProperties
description: TXlsFile.SetCommentProperties
---

# TXlsFile\.SetCommentProperties Method

Sets the popup placement for an existing comment\. If there is not a comment on cell \(row,col\), this will create an empty one\.


## Remarks

Note that you can change the size but not the placement of the popup\.
This placement you set here is the one you see when you right click the cell and choose "Show comment"\.
The yellow popup box is placed automatically by excel\.

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetCommentProperties(const row: Integer; const col: Integer; commentProperties: <a href="../../FlexCel.Core/IImageProperties/index.md">IImageProperties</a>); override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row index \(1 based\)|
|const|**col**|Integer|Column index \(1 based\)|
||**commentProperties**|[IImageProperties](../../FlexCel.Core/IImageProperties/index.md)|Placement and properties of the comment popup\. Null if there is no comment on the cell\. This parameter can be a TImageProperties, or the more complete derived class TCommentProperties, if you need to set extra information like the text alignment\.|


## See also

* [TXlsFile](../TXlsFile/index.md)
* [TExcelFile.CommentRowCount](../../FlexCel.Core/TExcelFile/CommentRowCount.md)
* [TExcelFile.CommentCountRow](../../FlexCel.Core/TExcelFile/CommentCountRow.md)
* [TExcelFile.GetCommentRow](../../FlexCel.Core/TExcelFile/GetCommentRow.md)
* [TExcelFile.GetCommentRowCol](../../FlexCel.Core/TExcelFile/GetCommentRowCol.md)
* [TExcelFile.GetComment](../../FlexCel.Core/TExcelFile/GetComment.md)
* [TExcelFile.SetCommentRow\(Integer, Integer, string, IImageProperties, Boolean\)](../../FlexCel.Core/TExcelFile/SetCommentRow.md#texcelfilesetcommentrowinteger-integer-string-iimageproperties-boolean)
* [TExcelFile.SetComment\(Integer, Integer, TRichString\)](../../FlexCel.Core/TExcelFile/SetComment.md#texcelfilesetcommentinteger-integer-trichstring)
* [TExcelFile.GetCommentPropertiesRow](../../FlexCel.Core/TExcelFile/GetCommentPropertiesRow.md)
* [TExcelFile.GetCommentProperties](../../FlexCel.Core/TExcelFile/GetCommentProperties.md)
* [TExcelFile.SetCommentPropertiesRow](../../FlexCel.Core/TExcelFile/SetCommentPropertiesRow.md)

