---
uid: TTokenRelativeCellAddress
description: TTokenRelativeCellAddress
---

# TTokenRelativeCellAddress Class

A single cell address in the same sheet or to other sheet\. It handles a reference relative to the current cell\. So a reference in Cell A4 of RowOffset = \-1 and ColOffset = 3 would mean the cell D3\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TTokenRelativeCellAddress = class(<a href="../TToken/index.md">TToken</a>);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new relative cell address token\.<br />|


## Properties

|Name|Description|
|---|---|
|[RowOffset](RowOffset.md)|The number of rows after or before the current row\. It might be negative\.<br />|
|[ColOffset](ColOffset.md)|The number of columns after or before the current column\. It might be negative\.<br />|
|[ExternalBookName](ExternalBookName.md)|File where the reference points to, when this is a reference to other file\. Empty or null if the reference is to the same file\.<br />|
|[Sheet](Sheet.md)|Sheet where the reference points to\. Empty or null if the reference points to the same sheet\.<br />|


