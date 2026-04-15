---
uid: TPdfAttachmentWriter.Write
description: TPdfAttachmentWriter.Write
---

# TPdfAttachmentWriter\.Write Method

## Overloads

* [TPdfAttachmentWriter\.Write\(TBytes\)](#tpdfattachmentwriterwritetbytes)
* [TPdfAttachmentWriter\.Write\(TStream\)](#tpdfattachmentwriterwritetstream)
* [TPdfAttachmentWriter\.Write\(TBytes, Integer, Integer\)](#tpdfattachmentwriterwritetbytes-integer-integer)

# TPdfAttachmentWriter\.Write\(TBytes\)
Writes a byte array into the file\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TPdfAttachmentWriter/index.md">TPdfAttachmentWriter</a>.Write(const data: TBytes); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**data**|TBytes|Data to be written\.|


## See also

* [TPdfAttachmentWriter](../TPdfAttachmentWriter/index.md)

# TPdfAttachmentWriter\.Write\(TStream\)
Writes an stream into the file\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TPdfAttachmentWriter/index.md">TPdfAttachmentWriter</a>.Write(const data: TStream); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**data**|TStream|Stream with the data that will be written\. Make sure it is at the correct position\.|


## See also

* [TPdfAttachmentWriter](../TPdfAttachmentWriter/index.md)

# TPdfAttachmentWriter\.Write\(TBytes, Integer, Integer\)
Writes part of a byte array into the file\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TPdfAttachmentWriter/index.md">TPdfAttachmentWriter</a>.Write(const data: TBytes; const offset: Integer; const count: Integer); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**data**|TBytes|Data to be written\.|
|const|**offset**|Integer|Offset in Data of the first byte to be written\.|
|const|**count**|Integer|Numbers of bytes to be written\.|


## See also

* [TPdfAttachmentWriter](../TPdfAttachmentWriter/index.md)

