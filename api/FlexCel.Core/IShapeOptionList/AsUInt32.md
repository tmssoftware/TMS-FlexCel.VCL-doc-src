---
uid: IShapeOptionList.AsUInt32
description: IShapeOptionList.AsUInt32
---

# IShapeOptionList\.AsUInt32 Method

Returns a long property if it exists, otherwise the default value\. Note: This method will always return positive numbers\.
To get an signed int, use [AsInt32](AsInt32.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../IShapeOptionList/index.md">IShapeOptionList</a>.AsUInt32(const key: <a href="../TShapeOption.md">TShapeOption</a>; const Default: Cardinal): Cardinal; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**key**|[TShapeOption](../TShapeOption.md)|Property Name\.|
|const|**Default**|Cardinal|What to return if the property does not exist\.|


## See also

* [IShapeOptionList](../IShapeOptionList/index.md)

