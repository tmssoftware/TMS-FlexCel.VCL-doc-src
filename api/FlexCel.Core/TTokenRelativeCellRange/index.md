---
uid: TTokenRelativeCellRange
description: TTokenRelativeCellRange
---

# TTokenRelativeCellRange Class

A range of cells with relative references\. This is used mostly in named ranges\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TTokenRelativeCellRange = class(<a href="../TToken/index.md">TToken</a>);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new relative cell range token\.<br />|


## Properties

|Name|Description|
|---|---|
|[ExternalBookName](ExternalBookName.md)|File where the reference points to, when this is a reference to other file\. Empty or null if the reference is to the same file\.<br />|
|[Sheet1](Sheet1.md)|First sheet where the reference points to\. Empty or null if the reference points to the same sheet\.<br />|
|[Sheet2](Sheet2.md)|Second sheet where the reference points to\. Empty or null if the reference points to the same sheet\.<br />|
|[RowOffset1](RowOffset1.md)|First row of the range \(1 based\)\.<br />|
|[ColOffset1](ColOffset1.md)|First column of the range \(1 based\)\.<br />|
|[RowOffset2](RowOffset2.md)|Last row of the range \(1 based\)\.<br />|
|[ColOffset2](ColOffset2.md)|Last column of the range \(1 based\)\.<br />|


