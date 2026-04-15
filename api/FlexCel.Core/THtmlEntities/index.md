---
uid: THtmlEntities
description: THtmlEntities
---

# THtmlEntities Record

Contains a list of HTML entities and their values

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">THtmlEntities = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[TryNameToCode](TryNameToCode.md)|Converts an Html entity like "amp" into the unicode code for the character\. The input string can also  be a \# code, in decimal or hexadecimal\. \(for example &amp;\#64\)\.<br />|
|[GetTag](GetTag.md)|Returns the identifier of a tag\.<br />|
|[EncodeAsHtml](EncodeAsHtml.md)|**Overloaded<br />**  [EncodeAsHtml\(string, THtmlVersion, TEncoding\)](EncodeAsHtml.md#thtmlentitiesencodeashtmlstring-thtmlversion-tencoding)<br />  [EncodeAsHtml\(string, THtmlVersion, TEncoding, TEnterStyle\)](EncodeAsHtml.md#thtmlentitiesencodeashtmlstring-thtmlversion-tencoding-tenterstyle)<br />|


## Properties

|Name|Description|
|---|---|
|[MaxNameLength](MaxNameLength.md)|Returns the maximum length for a name\. This includes decimal entities, that can have up to 7 numbers\.<br />|


