---
uid: TPdfCommentProperties.Create
description: TPdfCommentProperties.Create
---

# TPdfCommentProperties\.Create Method

## Overloads

* [TPdfCommentProperties\.Create\(TPdfCommentProperties\)](#tpdfcommentpropertiescreatetpdfcommentproperties)
* [TPdfCommentProperties\.Create\(TPdfCommentType, TPdfCommentIcon, Double, TUIColor, TUIColor\)](#tpdfcommentpropertiescreatetpdfcommenttype-tpdfcommenticon-double-tuicolor-tuicolor)

# TPdfCommentProperties\.Create\(TPdfCommentProperties\)
Creates a new TPdfCommentProperties instance based on the data from another instance\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TPdfCommentProperties/index.md">TPdfCommentProperties</a>.Create(const aProps: <a href="../TPdfCommentProperties/index.md">TPdfCommentProperties</a>): <a href="../TPdfCommentProperties/index.md">TPdfCommentProperties</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aProps**|[TPdfCommentProperties](../TPdfCommentProperties/index.md)||


## See also

* [TPdfCommentProperties](../TPdfCommentProperties/index.md)

# TPdfCommentProperties\.Create\(TPdfCommentType, TPdfCommentIcon, Double, TUIColor, TUIColor\)
Creates a new instance of a comment object\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TPdfCommentProperties/index.md">TPdfCommentProperties</a>.Create(const aCommentType: <a href="../TPdfCommentType.md">TPdfCommentType</a>; const aIcon: <a href="../TPdfCommentIcon.md">TPdfCommentIcon</a>; const aOpacity: Double; const aBackgroundColor: <a href="../../FlexCel.Core/TUIColor/index.md">TUIColor</a>; const aLineColor: <a href="../../FlexCel.Core/TUIColor/index.md">TUIColor</a>): <a href="../TPdfCommentProperties/index.md">TPdfCommentProperties</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aCommentType**|[TPdfCommentType](../TPdfCommentType.md)||
|const|**aIcon**|[TPdfCommentIcon](../TPdfCommentIcon.md)||
|const|**aOpacity**|Double||
|const|**aBackgroundColor**|[TUIColor](../../FlexCel.Core/TUIColor/index.md)||
|const|**aLineColor**|[TUIColor](../../FlexCel.Core/TUIColor/index.md)||


## See also

* [TPdfCommentProperties](../TPdfCommentProperties/index.md)

