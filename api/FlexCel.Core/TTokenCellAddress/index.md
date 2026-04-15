---
uid: TTokenCellAddress
description: TTokenCellAddress
---

# TTokenCellAddress Class

A single cell address in the same sheet or to other sheet\. See also TTokenCellRange, TTokenRelativeCellAddress, TTokenRelativeCellRange for other tokens that can contain addresses\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TTokenCellAddress = class(<a href="../TToken/index.md">TToken</a>);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new Cell address token\.<br />|


## Properties

|Name|Description|
|---|---|
|[Address](Address.md)|Cell address where this reference points to\.<br />|
|[ExternalBookName](ExternalBookName.md)|File where the reference points to, when this is a reference to other file\. Empty or null if the reference is to the same file\.<br />|


