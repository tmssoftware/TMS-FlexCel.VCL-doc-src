---
uid: IShapeOptionList.AsLong
description: IShapeOptionList.AsLong
---

# IShapeOptionList\.AsLong Method

Returns a long property if it exists, otherwise the default value\. Note: This method will always assume a positive number\.
To get a signed int, use [AsSignedLong](AsSignedLong.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../IShapeOptionList/index.md">IShapeOptionList</a>.AsLong(const key: <a href="../TShapeOption.md">TShapeOption</a>; const Default: Int64): Int64; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**key**|[TShapeOption](../TShapeOption.md)|Property Name\.|
|const|**Default**|Int64|What to return if the property does not exist\.|


## See also

* [IShapeOptionList](../IShapeOptionList/index.md)

