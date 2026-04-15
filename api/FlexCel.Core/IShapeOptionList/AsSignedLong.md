---
uid: IShapeOptionList.AsSignedLong
description: IShapeOptionList.AsSignedLong
---

# IShapeOptionList\.AsSignedLong Method

Returns a long property if it exists, otherwise the default value\. Note: This method will return negative numbers if the number is bigger than 65536\.
To get an unsigned int, use [AsLong](AsLong.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../IShapeOptionList/index.md">IShapeOptionList</a>.AsSignedLong(const key: <a href="../TShapeOption.md">TShapeOption</a>; const Default: Int64): Int64; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**key**|[TShapeOption](../TShapeOption.md)|Property Name\.|
|const|**Default**|Int64|What to return if the property does not exist\.|


## See also

* [IShapeOptionList](../IShapeOptionList/index.md)

