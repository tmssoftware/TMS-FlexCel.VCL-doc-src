---
uid: TReplaceAction
description: TReplaceAction
---

# TReplaceAction Class

Specifies actions to do in every replacement\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TReplaceAction = class(TFlexCelObject);</code></pre>

## Properties

|Name|Description|
|---|---|
|[Row](Row.md)|Row of the replaced cell\.<br />|
|[Col](Col.md)|Column of the replaced cell\.<br />|
|[ReplacementNumber](ReplacementNumber.md)|Number of replacement being made\. This number will be 1 for the first replacement, 2 for the second and so on\.<br />|
|[SkipReplacement](SkipReplacement.md)|Set this value to true to skip the current replacement\.<br />|
|[XF](XF.md)|Format for the replaced cell\. Change it if you want to provide custom format for the cell\.<br />|
|[CellValue](CellValue.md)|Value of the replaced cell\. You can change it to something else\.<br />|


