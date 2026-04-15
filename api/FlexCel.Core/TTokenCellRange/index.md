---
uid: TTokenCellRange
description: TTokenCellRange
---

# TTokenCellRange Class

A range of cells\. See TTokenCellAddress for single cell references\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TTokenCellRange = class(<a href="../TToken/index.md">TToken</a>);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new Cell range token\.<br />|


## Properties

|Name|Description|
|---|---|
|[ExternalBookName](ExternalBookName.md)|File where the reference points to, when this is a reference to other file\. Empty or null if the reference is to the same file\.<br />|
|[Sheet1](Sheet1.md)|First sheet where the reference points to\. Empty or null if the reference points to the same sheet\.<br />|
|[Sheet2](Sheet2.md)|Second sheet where the reference points to\. Empty or null if the reference points to the same sheet\.<br />|
|[Row1](Row1.md)|First row of the range \(1 based\)\.<br />|
|[Col1](Col1.md)|First column of the range \(1 based\)\.<br />|
|[Row2](Row2.md)|Last row of the range \(1 based\)\.<br />|
|[Col2](Col2.md)|Last column of the range \(1 based\)\.<br />|
|[Row1Absolute](Row1Absolute.md)|True if the reference is absolute \(as in $A$1\)\.<br />|
|[Col1Absolute](Col1Absolute.md)|True if the reference is absolute \(as in $A$1\)\.<br />|
|[Row2Absolute](Row2Absolute.md)|True if the reference is absolute \(as in $A$1\)\.<br />|
|[Col2Absolute](Col2Absolute.md)|True if the reference is absolute \(as in $A$1\)\.<br />|


