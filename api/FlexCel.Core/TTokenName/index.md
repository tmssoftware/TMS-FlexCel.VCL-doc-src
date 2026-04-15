---
uid: TTokenName
description: TTokenName
---

# TTokenName Class

A named range\. Might refer to a name in a different file\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TTokenName = class(<a href="../TToken/index.md">TToken</a>);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new name token\.<br />|


## Properties

|Name|Description|
|---|---|
|[Name](Name.md)|Named range represented by this token\.<br />|
|[Sheet](Sheet.md)|Sheet where the name is stored\. Make it null or empty if the name is a global name\.<br />|
|[WorkbookName](WorkbookName.md)|Workbook where the name is, if this is an external name\. If then name is in the same file as the reference, this value will be null or empty\.<br />|


