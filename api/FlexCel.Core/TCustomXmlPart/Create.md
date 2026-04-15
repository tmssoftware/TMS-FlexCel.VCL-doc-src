---
uid: TCustomXmlPart.Create
description: TCustomXmlPart.Create
---

# TCustomXmlPart\.Create Method

## Overloads

* [TCustomXmlPart\.Create](#tcustomxmlpartcreate)
* [TCustomXmlPart\.Create\(string, TArray\<string>\)](#tcustomxmlpartcreatestring-tarraystring)
* [TCustomXmlPart\.Create\(TGUID, string, TArray\<string>\)](#tcustomxmlpartcreatetguid-string-tarraystring)

# TCustomXmlPart\.Create
Creates a new TCustomXmlPart\. It will set the Id to a random GUID\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TCustomXmlPart/index.md">TCustomXmlPart</a>.Create: <a href="../TCustomXmlPart/index.md">TCustomXmlPart</a>; static; overload;</code></pre>

## See also

* [TCustomXmlPart](../TCustomXmlPart/index.md)

# TCustomXmlPart\.Create\(string, TArray\<string>\)
Creates a new TCustomXmlParts with a random Id and the given xml and schemas\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TCustomXmlPart/index.md">TCustomXmlPart</a>.Create(const aXml: string; const aSchemas: TArray&lt;string&gt;): <a href="../TCustomXmlPart/index.md">TCustomXmlPart</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aXml**|string|Xml of the custom part\.|
|const|**aSchemas**|TArray\<string>|List of schemas for the custom part\. Leave it null or empty if there a no schemas\.<br />Note that the array will be copied, so you can modify it after setting it and it won't change the Xml part\.|


## See also

* [TCustomXmlPart](../TCustomXmlPart/index.md)

# TCustomXmlPart\.Create\(TGUID, string, TArray\<string>\)
Creates a new TCustomXmlParts the given Id, xml and schemas\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TCustomXmlPart/index.md">TCustomXmlPart</a>.Create(const aId: TGUID; const aXml: string; const aSchemas: TArray&lt;string&gt;): <a href="../TCustomXmlPart/index.md">TCustomXmlPart</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aId**|TGUID|Guid for the part\. Make sure this is unique\.|
|const|**aXml**|string|Xml of the custom part\.|
|const|**aSchemas**|TArray\<string>|List of schemas for the custom part\. Leave it null or empty if there a no schemas\.<br />Note that the array will be copied, so you can modify it after setting it and it won't change the Xml part\.|


## See also

* [TCustomXmlPart](../TCustomXmlPart/index.md)

