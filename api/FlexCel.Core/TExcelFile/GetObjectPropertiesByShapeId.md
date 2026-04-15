---
uid: TExcelFile.GetObjectPropertiesByShapeId
description: TExcelFile.GetObjectPropertiesByShapeId
---

# TExcelFile\.GetObjectPropertiesByShapeId Method

Returns information on an object and all of its children and parents\.

**Note:** This method always returns a top level object\. If you ask for a shape id of a shape that is contained inside other group, this method will return the first level group containing other groups that contain the shape\.


**Note 2:**This method is mostly for internal use\. Shape ids are not guaranteed to be preserved when  saving and reloading a file, so this method should only be used while editing the file with shape ids retrieved from the XlsFile object, not hardcoded shape ids\. To get the object properties for a known shape in a file, give it a name and call [GetObjectProperties\(Integer, string, Boolean\)](GetObjectProperties.md#texcelfilegetobjectpropertiesinteger-string-boolean) with an objectPath of "@name\-of\-the\-shape"\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetObjectPropertiesByShapeId(const shapeId: Int64; const getShapeOptions: Boolean): <a href="../IShapeProperties/index.md">IShapeProperties</a>; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**shapeId**|Int64|Identifier of the shape\.|
|const|**getShapeOptions**|Boolean|When true, shape options will be retrieved\. As this can be a slow operation, only specify true when you really need those options\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

