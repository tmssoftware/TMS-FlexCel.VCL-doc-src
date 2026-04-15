---
uid: TExcelFile.GetCommentProperties
description: TExcelFile.GetCommentProperties
---

# TExcelFile\.GetCommentProperties Method

Gets the popup placement for an existing comment\. If there is not a comment on cell \(row,col\), this will return null\.


## Remarks

Note that you can change the size but not the placement of the popup\.
This placement you set here is the one you see when you right click the cell and choose "Show comment"\.
The yellow popup box is placed automatically by excel\.

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetCommentProperties(const row: Integer; const col: Integer): <a href="../ICommentProperties/index.md">ICommentProperties</a>; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row index \(1 based\)\.|
|const|**col**|Integer|Column index \(1 based\)|


## Returns

Placement of the comment popup\.

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
* [SetCommentPropertiesRow](SetCommentPropertiesRow.md)
* [SetCommentProperties](SetCommentProperties.md)

