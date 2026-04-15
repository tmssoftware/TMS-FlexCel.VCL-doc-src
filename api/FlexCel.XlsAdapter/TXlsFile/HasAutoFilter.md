---
uid: TXlsFile.HasAutoFilter
description: TXlsFile.HasAutoFilter
---

# TXlsFile\.HasAutoFilter Method

## Overloads

* [TXlsFile\.HasAutoFilter](#txlsfilehasautofilter)
* [TXlsFile\.HasAutoFilter\(Integer, Integer\)](#txlsfilehasautofilterinteger-integer)

# TXlsFile\.HasAutoFilter
Returns true if the active sheet has any AutoFilter defined\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.HasAutoFilter: Boolean; overload; override;</code></pre>

## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.HasAutoFilter\(Integer, Integer\)
Returns true if a cell has an AutoFilter\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.HasAutoFilter(const row: Integer; const col: Integer): Boolean; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row of the cell we want to find out\. \(1 based\)|
|const|**col**|Integer|Column of the cell we want to find out\. \(1 based\)|


## Returns

True if the cell has an AutoFilter, false otherwise\.

## See also

* [TXlsFile](../TXlsFile/index.md)

