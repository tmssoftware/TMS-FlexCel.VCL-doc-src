---
uid: TTokenStructuredReference.Create
description: TTokenStructuredReference.Create
---

# TTokenStructuredReference\.Create Constructor

Creates a new Structured Reference argument token\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TTokenStructuredReference/index.md">TTokenStructuredReference</a>.Create(const aWorkbookName: string; const aTableName: string; const aSections: <a href="../TStructRefSection.md">Set of TStructRefSection</a>; const aFirstColumn: string; const aLastColumn: string; const aSpaceAfterComma: Boolean; const aSpaceAfterBrackets: Boolean);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aWorkbookName**|string|Name of the file where the referenced table is\. If this value is empty, then the table  is in the same file as the reference\.|
|const|**aTableName**|string|Name of the table where this reference applies\.|
|const|**aSections**|[Set of TStructRefSection](../TStructRefSection.md)|Sections of the table where the reference applies\.|
|const|**aFirstColumn**|string|First column where the reference applies\. Set it to empty if the reference applies to the whole table\.|
|const|**aLastColumn**|string|Last column where the reference applies\.<br />If empty and FirstColumn is empty too, then the reference applies to the whole table\.<br />If empty but FirstColumn is not empty, then this reference applies only to FirstColumn\.|
|const|**aSpaceAfterComma**|Boolean|If true, the text of the structured reference arguments will include a space after every comma separating arguments\.|
|const|**aSpaceAfterBrackets**|Boolean|If true, the text of the structure reference will include a space after the brackets which define the arguments\.|


## See also

* [TTokenStructuredReference](../TTokenStructuredReference/index.md)

