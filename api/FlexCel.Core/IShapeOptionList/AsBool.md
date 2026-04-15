---
uid: IShapeOptionList.AsBool
description: IShapeOptionList.AsBool
---

# IShapeOptionList\.AsBool Method

## Overloads

* [IShapeOptionList\.AsBool\(TShapeOption, Boolean\)](#ishapeoptionlistasbooltshapeoption-boolean)
* [IShapeOptionList\.AsBool\(TShapeOption, Boolean, Integer\)](#ishapeoptionlistasbooltshapeoption-boolean-integer)

# IShapeOptionList\.AsBool\(TShapeOption, Boolean\)
Returns a bool property if it exists, otherwise the default value\. This method overload automatically calculates the position in the boolean set so you don't need to specify it\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../IShapeOptionList/index.md">IShapeOptionList</a>.AsBool(const key: <a href="../TShapeOption.md">TShapeOption</a>; const Default: Boolean): Boolean; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**key**|[TShapeOption](../TShapeOption.md)|Property Name\.|
|const|**Default**|Boolean|What to return if the property does not exist\.|


## See also

* [IShapeOptionList](../IShapeOptionList/index.md)

# IShapeOptionList\.AsBool\(TShapeOption, Boolean, Integer\)
Returns a bool property if it exists, otherwise the default value\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../IShapeOptionList/index.md">IShapeOptionList</a>.AsBool(const key: <a href="../TShapeOption.md">TShapeOption</a>; const Default: Boolean; const PositionInSet: Integer): Boolean; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**key**|[TShapeOption](../TShapeOption.md)|Property Name\.|
|const|**Default**|Boolean|What to return if the property does not exist\.|
|const|**PositionInSet**|Integer|Boolean properties are grouped so all properties on one set are in only one value\. So, the last bool property on the set is the first bit, and so on\. ONLY THE LAST PROPERTY ON THE SET IS PRESENT\.|


## See also

* [IShapeOptionList](../IShapeOptionList/index.md)

