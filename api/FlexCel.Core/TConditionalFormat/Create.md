---
uid: TConditionalFormat.Create
description: TConditionalFormat.Create
---

# TConditionalFormat\.Create Method

Creates a new conditional format\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TConditionalFormat/index.md">TConditionalFormat</a>.Create(const aRanges: <a href="../TXlsCellRange/index.md">TArray&lt;TXlsCellRange></a>; const aRules: <a href="../IConditionalFormatRule/index.md">TArray&lt;IConditionalFormatRule></a>; const aIsPivot: Boolean): <a href="../TConditionalFormat/index.md">TConditionalFormat</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aRanges**|[TArray\<&#8203;TXls&#8203;Cell&#8203;Range>](../TXlsCellRange/index.md)|List of ranges where this format will apply\.|
|const|**aRules**|[TArray\<&#8203;IConditional&#8203;Format&#8203;Rule>](../IConditionalFormatRule/index.md)|List of rules to apply to the cells\.|
|const|**aIsPivot**|Boolean|If true, then this is a conditional format for a pivot table\.|


## See also

* [TConditionalFormat](../TConditionalFormat/index.md)

