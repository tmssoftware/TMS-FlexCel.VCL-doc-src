---
uid: TFlxPartialFormat
description: TFlxPartialFormat
---

# TFlxPartialFormat Record

This structure holds together the format definition for a cell, and which parts of that format definition should be applied\. With this you can apply only parts of the format to a cell\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TFlxPartialFormat = record;</code></pre>

## Fields

|Name|Description|
|---|---|
|[Format](Format.md)|Format to apply to the cell\.<br />|
|[Apply](Apply.md)|Which properties to apply to the cell\. For example you might apply only the numeric format defined by [Format](Format.md), but not the cell color\.<br />|
|[ExternalBorders](ExternalBorders.md)|If true and applying the format to a range of cells, only the borders on the outside of the range will be drawn\.<br />|


## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new TFlxPartialFormat\.<br />|


