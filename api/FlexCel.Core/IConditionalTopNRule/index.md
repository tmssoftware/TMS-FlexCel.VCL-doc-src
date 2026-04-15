---
uid: IConditionalTopNRule
description: IConditionalTopNRule
---

# IConditionalTopNRule Interface

A conditional format rule specified by the top\-N or bottom\-N values\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">IConditionalTopNRule = interface(<a href="../IConditionalFormatStandardDefRule/index.md">IConditionalFormatStandardDefRule</a>);</code></pre>

## Properties

|Name|Description|
|---|---|
|[Rank](Rank.md)|The value of N in Top\-N|
|[IsBottom](IsBottom.md)|If true then this rule targets the bottom\-n values instead of the top\-n\.<br />|
|[IsPercent](IsPercent.md)|If true, then this rule targets top n%% instead of top n values\.<br />|


