---
uid: IXmlMap
description: IXmlMap
---

# IXmlMap Interface

Encapsulates the XML Maps in a file\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">IXmlMap = interface(IInterface);</code></pre>

## Methods

|Name|Description|
|---|---|
|[AddSchema](AddSchema.md)|Adds a new schema to the xml map, and returns it so you can fill the data of the new schema\.<br />The returned schema is owned by this class and modifying it will modify the schema in the class\.<br />|
|[AddMap](AddMap.md)|Adds a new map to the xml map, and returns it so you can fill the data of the new map\.<br />The returned map is owned by this class and modifying it will modify the map in the class\.<br />|
|[GetSchema](GetSchema.md)|Gets the schema at position index\. \(0 based\)\. The schema returned is not a copy but the actual schema in the class, so modifying it will modify the schema in the class\.<br />|
|[GetMap](GetMap.md)|Gets the map at position index\. \(0 based\)\. The map returned is not a copy but the actual map in the class, so modifying it will modify the map in the class\.<br />|
|[ClearSchemas](ClearSchemas.md)|Erases all schemas in the class\.<br />|
|[ClearMap](ClearMap.md)|Erases all maps in the class\.<br />|
|[Assign](Assign.md)|Copies a different xml map to this instance, clearing any existing data in this instance\. If map is null, then this method will clear everything\.<br />|
|[Clone](Clone.md)|Returns a deep copy of this object\.<br />|


## Properties

|Name|Description|
|---|---|
|[SelectionNamespaces](SelectionNamespaces.md)|Ties the prefix to the actual namespace\. This is used when writing xpath expressions at runtime against the XML instance structures, because the xpath expressions use namespace prefixes instead of the fully spelled out namespace\.<br />|
|[SchemaCount](SchemaCount.md)|Count of schemas in the class\.<br />|
|[MapCount](MapCount.md)|Count of maps in the class\.<br />|
|[IsEmpty](IsEmpty.md)|Returns true if this class has no schemas or maps\.<br />|


