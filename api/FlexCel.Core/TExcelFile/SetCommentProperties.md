---
uid: TExcelFile.SetCommentProperties
description: TExcelFile.SetCommentProperties
---

# TExcelFile\.SetCommentProperties Method

Sets the popup placement for an existing comment\. If there is not a comment on cell \(row,col\), this will create an empty one\.


## Remarks

Note that you can change the size but not the placement of the popup\.
This placement you set here is the one you see when you right click the cell and choose "Show comment"\.
The yellow popup box is placed automatically by excel\.

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetCommentProperties(const row: Integer; const col: Integer; commentProperties: <a href="../IImageProperties/index.md">IImageProperties</a>); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row index \(1 based\)|
|const|**col**|Integer|Column index \(1 based\)|
||**commentProperties**|[IImageProperties](../IImageProperties/index.md)|Placement and properties of the comment popup\. Null if there is no comment on the cell\. This parameter can be a TImageProperties, or the more complete derived class TCommentProperties, if you need to set extra information like the text alignment\.|


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
* [SetCommentPropertiesRow](SetCommentPropertiesRow.md)

