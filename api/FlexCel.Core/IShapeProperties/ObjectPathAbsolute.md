---
uid: IShapeProperties.ObjectPathAbsolute
description: IShapeProperties.ObjectPathAbsolute
---

# IShapeProperties.ObjectPathAbsolute Property

Use this string to identify the shape when it is not the first on the hierarchy\.
For Example, imagine you have a Group Shape A with 2 children, B and C\.
If you want to change the text on shape C, you need to call SetObjectText\(n, ObjectPath\);
The object path can be of 2 types: Absolute or relative\. Absolute object paths start with "\\" and include the parent object\. Relative paths don't include the main group shape\.

For example the absolute path "\\1\\2\\3" is the same as accessing the object 1, with object path "2\\3" **** This property returns the absolute path, you can get the relative path with [ObjectPath](ObjectPath.md)\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../IShapeProperties/index.md">IShapeProperties</a>.ObjectPathAbsolute: string</code></pre>

## See also

* [IShapeProperties](../IShapeProperties/index.md)

