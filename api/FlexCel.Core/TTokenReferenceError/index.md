---
uid: TTokenReferenceError
description: TTokenReferenceError
---

# TTokenReferenceError Class

This token represents an error like \#REF\!

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TTokenReferenceError = class(<a href="../TToken/index.md">TToken</a>);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new TTokenError instance with the corresponding error type\.<br />|


## Properties

|Name|Description|
|---|---|
|[IsArea](IsArea.md)|Returns true if this is a reference to an area of cells\.<br />|
|[Is3D](Is3D.md)|Returns true if this is a reference to multiple sheets\.<br />|
|[IsRelative](IsRelative.md)|If true this reference is relative to the cell where the formula is\.<br />|


