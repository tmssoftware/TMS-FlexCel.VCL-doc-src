---
uid: TTokenCellRange.Create
description: TTokenCellRange.Create
---

# TTokenCellRange\.Create Constructor

Creates a new Cell range token\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TTokenCellRange/index.md">TTokenCellRange</a>.Create(const aExternalBookName: string; const aSheet1: string; const aSheet2: string; const aRow1: Integer; const aCol1: Integer; const aRow2: Integer; const aCol2: Integer; const aRow1Abs: Boolean; const aCol1Abs: Boolean; const aRow2Abs: Boolean; const aCol2Abs: Boolean);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aExternalBookName**|string|File where the reference points to, when this is a reference to other file\. Empty or null if the reference is to the same file\.|
|const|**aSheet1**|string|First sheet where the reference points to\. Empty or null if the reference points to the same sheet\.|
|const|**aSheet2**|string|Second where the reference points to\. Empty or null if the reference points to the same sheet\.|
|const|**aRow1**|Integer|First row \(1 based\)\.|
|const|**aCol1**|Integer|First column \(1 based\)\.|
|const|**aRow2**|Integer|Last row \(1 based\)\.|
|const|**aCol2**|Integer|Last column \(1 based\)\.|
|const|**aRow1Abs**|Boolean|True if the first row is an absolute reference \(like in A$1\)|
|const|**aCol1Abs**|Boolean|True if the first column is an absolute reference \(like in $A1\)|
|const|**aRow2Abs**|Boolean|True if the last row is an absolute reference \(like in A$1\)|
|const|**aCol2Abs**|Boolean|True if the last column is an absolute reference \(like in $A1\)|


## See also

* [TTokenCellRange](../TTokenCellRange/index.md)

