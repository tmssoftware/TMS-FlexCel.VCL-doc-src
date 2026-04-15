---
uid: TXlsNamedRange.Create
description: TXlsNamedRange.Create
---

# TXlsNamedRange\.Create Method

## Overloads

* [TXlsNamedRange\.Create](#txlsnamedrangecreate)
* [TXlsNamedRange\.Create\(string, Integer, Integer, string\)](#txlsnamedrangecreatestring-integer-integer-string)
* [TXlsNamedRange\.Create\(string, Integer, Integer, Integer, Integer, Integer, Integer, string\)](#txlsnamedrangecreatestring-integer-integer-integer-integer-integer-integer-string)
* [TXlsNamedRange\.Create\(string, Integer, Integer, Integer, Integer, Integer, Integer, Integer\)](#txlsnamedrangecreatestring-integer-integer-integer-integer-integer-integer-integer)
* [TXlsNamedRange\.Create\(string, Integer, Integer, Integer, Integer, Integer, Integer, Integer, string\)](#txlsnamedrangecreatestring-integer-integer-integer-integer-integer-integer-integer-string)
* [TXlsNamedRange\.Create\(string, Integer, Integer, Integer, Integer, Integer, Integer, Integer, string, string\)](#txlsnamedrangecreatestring-integer-integer-integer-integer-integer-integer-integer-string-string)

# TXlsNamedRange\.Create
Creates an empty NamedRange\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TXlsNamedRange/index.md">TXlsNamedRange</a>.Create: <a href="../TXlsNamedRange/index.md">TXlsNamedRange</a>; static; overload;</code></pre>

## See also

* [TXlsNamedRange](../TXlsNamedRange/index.md)

# TXlsNamedRange\.Create\(string, Integer, Integer, string\)
Creates a complex Named range, with a formula\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TXlsNamedRange/index.md">TXlsNamedRange</a>.Create(const aName: string; const aNameSheetIndex: Integer; const aOptionFlags: Integer; const aRangeFormula: string): <a href="../TXlsNamedRange/index.md">TXlsNamedRange</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aName**|string|Name of the range\.|
|const|**aNameSheetIndex**|Integer|Sheet index for the sheet that holds the range\. 0 means a global range \(default on Excel\)|
|const|**aOptionFlags**|Integer|Options of this Range\.|
|const|**aRangeFormula**|string|The formula for the range, expressed as text\. For example: "A1:B2,C3:C7"<br />Note that with **relative** references, we always consider "A1" to be the cell where the name is\. This means that the formula: "=$A$1 \+ A1" when evaluated in Cell B8, will read "=$A$1 \+ B8"\. To provide a negative offset, you need to wrap the formula\.<br />For example "=A1048575" will evaluate to B7 when evaluated in B8\.<br />|


## See also

* [TXlsNamedRange](../TXlsNamedRange/index.md)

# TXlsNamedRange\.Create\(string, Integer, Integer, Integer, Integer, Integer, Integer, string\)
Creates a new Named range with the given values\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TXlsNamedRange/index.md">TXlsNamedRange</a>.Create(const aName: string; const aSheetIndex: Integer; const aFirstRow: Integer; const aFirstCol: Integer; const aLastRow: Integer; const aLastCol: Integer; const aOptionFlags: Integer; const aRangeFormula: string): <a href="../TXlsNamedRange/index.md">TXlsNamedRange</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aName**|string|Name of the range\.|
|const|**aSheetIndex**|Integer|Sheet index where the range is\. \(1\-based\)|
|const|**aFirstRow**|Integer|First row on range\.|
|const|**aFirstCol**|Integer|First column on range\.|
|const|**aLastRow**|Integer|Last row on range\.|
|const|**aLastCol**|Integer|Last column on range\.|
|const|**aOptionFlags**|Integer|Options of this Range\.|
|const|**aRangeFormula**|string|The formula for the range, expressed as text\. Use it if the range is complex and cannot be expressed with aSheetIndex, aFirstRow\.\.\. etc When you specify this parameter, all SheetIndex, aFirstRow, etc\. lose their meaning\.|


## See also

* [TXlsNamedRange](../TXlsNamedRange/index.md)

# TXlsNamedRange\.Create\(string, Integer, Integer, Integer, Integer, Integer, Integer, Integer\)
Creates a new Named range with the given values\. Use this overload to create a simple range\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TXlsNamedRange/index.md">TXlsNamedRange</a>.Create(const aName: string; const aNameSheetIndex: Integer; const aSheetIndex: Integer; const aFirstRow: Integer; const aFirstCol: Integer; const aLastRow: Integer; const aLastCol: Integer; const aOptionFlags: Integer): <a href="../TXlsNamedRange/index.md">TXlsNamedRange</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aName**|string|Name of the range\.|
|const|**aNameSheetIndex**|Integer|Sheet index for the sheet that holds the range\. 0 means a global range \(default on Excel\)|
|const|**aSheetIndex**|Integer|Sheet index where the range apply\. This is where row and col properties apply, not where the range is stored\. \(1\-based\)|
|const|**aFirstRow**|Integer|First row on range\.|
|const|**aFirstCol**|Integer|First column on range\.|
|const|**aLastRow**|Integer|Last row on range\.|
|const|**aLastCol**|Integer|Last column on range\.|
|const|**aOptionFlags**|Integer|Options of this Range\.|


## See also

* [TXlsNamedRange](../TXlsNamedRange/index.md)

# TXlsNamedRange\.Create\(string, Integer, Integer, Integer, Integer, Integer, Integer, Integer, string\)
Creates a new Named range with the given values\. Use this overload to create a simple range\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TXlsNamedRange/index.md">TXlsNamedRange</a>.Create(const aName: string; const aNameSheetIndex: Integer; const aSheetIndex: Integer; const aFirstRow: Integer; const aFirstCol: Integer; const aLastRow: Integer; const aLastCol: Integer; const aOptionFlags: Integer; const aRangeFormula: string): <a href="../TXlsNamedRange/index.md">TXlsNamedRange</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aName**|string|Name of the range\.|
|const|**aNameSheetIndex**|Integer|Sheet index for the sheet that holds the range\. 0 means a global range \(default on Excel\)|
|const|**aSheetIndex**|Integer|Sheet index where the range apply\. This is where row and col properties apply, not where the range is stored\. \(1\-based\)|
|const|**aFirstRow**|Integer|First row on range\.|
|const|**aFirstCol**|Integer|First column on range\.|
|const|**aLastRow**|Integer|Last row on range\.|
|const|**aLastCol**|Integer|Last column on range\.|
|const|**aOptionFlags**|Integer|Options of this Range\.|
|const|**aRangeFormula**|string|The formula for the range, expressed as text\. Use it if the range is complex and cannot be expressed with aSheetIndex, aFirstRow\.\.\. etc When you specify this parameter, all SheetIndex, aFirstRow, etc\. lose their meaning\.|


## See also

* [TXlsNamedRange](../TXlsNamedRange/index.md)

# TXlsNamedRange\.Create\(string, Integer, Integer, Integer, Integer, Integer, Integer, Integer, string, string\)
Creates a new Named range with the given values\. This is the most complete overload, you normally don't need to call it\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TXlsNamedRange/index.md">TXlsNamedRange</a>.Create(const aName: string; const aNameSheetIndex: Integer; const aSheetIndex: Integer; const aFirstRow: Integer; const aFirstCol: Integer; const aLastRow: Integer; const aLastCol: Integer; const aOptionFlags: Integer; const aRangeFormula: string; const aComment: string): <a href="../TXlsNamedRange/index.md">TXlsNamedRange</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aName**|string|Name of the range\.|
|const|**aNameSheetIndex**|Integer|Sheet index for the sheet that holds the range\. 0 means a global range \(default on Excel\)|
|const|**aSheetIndex**|Integer|Sheet index where the range apply\. This is where row and col properties apply, not where the range is stored\. \(1\-based\)|
|const|**aFirstRow**|Integer|First row on range\.|
|const|**aFirstCol**|Integer|First column on range\.|
|const|**aLastRow**|Integer|Last row on range\.|
|const|**aLastCol**|Integer|Last column on range\.|
|const|**aOptionFlags**|Integer|Options of this Range\.|
|const|**aRangeFormula**|string|The formula for the range, expressed as text\. Use it if the range is complex and cannot be expressed with aSheetIndex, aFirstRow\.\.\. etc When you specify this parameter, all SheetIndex, aFirstRow, etc\. lose their meaning\.<br /><br />Note that with **relative** references, we always consider "A1" to be the cell where the name is\. This means that the formula: "=$A$1 \+ A1" when evaluated in Cell B8, will read "=$A$1 \+ B8"\. To provide a negative offset, you need to wrap the formula\.<br />For example "=A1048575" will evaluate to B7 when evaluated in B8\.<br />|
|const|**aComment**|string|Comment for the named range\. Note that this will only show in Excel 2007 or newer\.|


## See also

* [TXlsNamedRange](../TXlsNamedRange/index.md)

