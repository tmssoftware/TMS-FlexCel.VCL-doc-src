---
uid: IShapeOptionList.AsInt32
description: IShapeOptionList.AsInt32
---

# IShapeOptionList\.AsInt32 Method

Returns a long property if it exists, otherwise the default value\. Note: This method will return negative numbers if the number is bigger than 65536\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../IShapeOptionList/index.md">IShapeOptionList</a>.AsInt32(const key: <a href="../TShapeOption.md">TShapeOption</a>; const Default: Integer): Integer; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**key**|[TShapeOption](../TShapeOption.md)|Property Name\.|
|const|**Default**|Integer|What to return if the property does not exist\.|


## See also

* [IShapeOptionList](../IShapeOptionList/index.md)

