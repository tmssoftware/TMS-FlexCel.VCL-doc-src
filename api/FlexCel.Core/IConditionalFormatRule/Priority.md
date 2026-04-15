---
uid: IConditionalFormatRule.Priority
description: IConditionalFormatRule.Priority
---

# IConditionalFormatRule.Priority Property

Priority for the rule\. 1 means the highest priority and higher number mean that the rule will be evaluated later\.
Note that priorities of all conditional rules **must be unique on the sheet**\. If you specify a duplicated priority, all other priorities might be shifted when you save the file so they keep being unique\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../IConditionalFormatRule/index.md">IConditionalFormatRule</a>.Priority: Integer</code></pre>

## See also

* [IConditionalFormatRule](../IConditionalFormatRule/index.md)

