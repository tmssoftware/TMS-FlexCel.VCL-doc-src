---
uid: TExcelFile.SetComment
description: TExcelFile.SetComment
---

# TExcelFile\.SetComment Method

## Overloads

* [TExcelFile\.SetComment\(Integer, Integer, string\)](#texcelfilesetcommentinteger-integer-string)
* [TExcelFile\.SetComment\(Integer, Integer, TRichString\)](#texcelfilesetcommentinteger-integer-trichstring)
* [TExcelFile\.SetComment\(Integer, Integer, string, string, IImageProperties\)](#texcelfilesetcommentinteger-integer-string-string-iimageproperties)
* [TExcelFile\.SetComment\(Integer, Integer, TRichString, string, IImageProperties, Boolean\)](#texcelfilesetcommentinteger-integer-trichstring-string-iimageproperties-boolean)

# TExcelFile\.SetComment\(Integer, Integer, string\)
Sets or deletes a comment at the specified cell\.


## Remarks

To delete a comment, set its value to String\.Empty\.

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetComment(const row: Integer; const col: Integer; const value: string); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row index \(1 based\)|
|const|**col**|Integer|Column index \(1 based\)|
|const|**value**|string|Text of the comment\. Set it to String\.Empty to delete the comment\.|


## See also

* [TExcelFile](../TExcelFile/index.md)
* [CommentRowCount](CommentRowCount.md)
* [CommentCountRow](CommentCountRow.md)
* [GetCommentRow](GetCommentRow.md)
* [GetCommentRowCol](GetCommentRowCol.md)
* [GetComment](GetComment.md)
* [SetCommentRow\(Integer, Integer, string, IImageProperties, Boolean\)](SetCommentRow.md#texcelfilesetcommentrowinteger-integer-string-iimageproperties-boolean)
* [GetCommentPropertiesRow](GetCommentPropertiesRow.md)
* [SetCommentPropertiesRow](SetCommentPropertiesRow.md)
* [SetCommentProperties](SetCommentProperties.md)

# TExcelFile\.SetComment\(Integer, Integer, TRichString\)
Sets or deletes a comment at the specified cell\.


## Remarks

To delete a comment, set its value to String\.Empty\.

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetComment(const row: Integer; const col: Integer; const value: <a href="../TRichString/index.md">TRichString</a>); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row index \(1 based\)|
|const|**col**|Integer|Column index \(1 based\)|
|const|**value**|[TRichString](../TRichString/index.md)|Text of the comment\. Set it to String\.Empty to delete the comment\.|


## See also

* [TExcelFile](../TExcelFile/index.md)
* [CommentRowCount](CommentRowCount.md)
* [CommentCountRow](CommentCountRow.md)
* [GetCommentRow](GetCommentRow.md)
* [GetCommentRowCol](GetCommentRowCol.md)
* [GetComment](GetComment.md)
* [SetCommentRow\(Integer, Integer, string, IImageProperties, Boolean\)](SetCommentRow.md#texcelfilesetcommentrowinteger-integer-string-iimageproperties-boolean)
* [GetCommentPropertiesRow](GetCommentPropertiesRow.md)
* [SetCommentPropertiesRow](SetCommentPropertiesRow.md)
* [SetCommentProperties](SetCommentProperties.md)

# TExcelFile\.SetComment\(Integer, Integer, string, string, IImageProperties\)
Sets or deletes a comment at the specified cell\.


## Remarks

To delete a comment, set its value to String\.Empty\.

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetComment(const row: Integer; const col: Integer; const value: string; const author: string; commentProperties: <a href="../IImageProperties/index.md">IImageProperties</a>); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row index \(1 based\)|
|const|**col**|Integer|Column index \(1 based\)|
|const|**value**|string|Text of the comment\. Set it to String\.Empty to delete the comment\.|
|const|**author**|string|Author of the comment\.|
||**commentProperties**|[IImageProperties](../IImageProperties/index.md)|Properties of the popup\.|


## See also

* [TExcelFile](../TExcelFile/index.md)
* [CommentRowCount](CommentRowCount.md)
* [CommentCountRow](CommentCountRow.md)
* [GetCommentRow](GetCommentRow.md)
* [GetCommentRowCol](GetCommentRowCol.md)
* [GetComment](GetComment.md)
* [SetCommentRow\(Integer, Integer, string, IImageProperties, Boolean\)](SetCommentRow.md#texcelfilesetcommentrowinteger-integer-string-iimageproperties-boolean)
* [GetCommentPropertiesRow](GetCommentPropertiesRow.md)
* [SetCommentPropertiesRow](SetCommentPropertiesRow.md)
* [SetCommentProperties](SetCommentProperties.md)

# TExcelFile\.SetComment\(Integer, Integer, TRichString, string, IImageProperties, Boolean\)
Sets or deletes a comment at the specified cell\.


## Remarks

To delete a comment, set its value to String\.Empty\.

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetComment(const row: Integer; const col: Integer; const value: <a href="../TRichString/index.md">TRichString</a>; const author: string; commentProperties: <a href="../IImageProperties/index.md">IImageProperties</a>; const removeEmpty: Boolean = True); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row index \(1 based\)|
|const|**col**|Integer|Column index \(1 based\)|
|const|**value**|[TRichString](../TRichString/index.md)|Text of the comment\. Set it to String\.Empty to delete the comment\.|
|const|**author**|string|Author of the comment\.|
||**commentProperties**|[IImageProperties](../IImageProperties/index.md)|Properties of the popup\.|
|const|**removeEmpty**|Boolean|**Optional**: Default value is True<br /><br />|


## See also

* [TExcelFile](../TExcelFile/index.md)
* [CommentRowCount](CommentRowCount.md)
* [CommentCountRow](CommentCountRow.md)
* [GetCommentRow](GetCommentRow.md)
* [GetCommentRowCol](GetCommentRowCol.md)
* [GetComment](GetComment.md)
* [SetCommentRow\(Integer, Integer, string, IImageProperties, Boolean\)](SetCommentRow.md#texcelfilesetcommentrowinteger-integer-string-iimageproperties-boolean)
* [GetCommentPropertiesRow](GetCommentPropertiesRow.md)
* [SetCommentPropertiesRow](SetCommentPropertiesRow.md)
* [SetCommentProperties](SetCommentProperties.md)

