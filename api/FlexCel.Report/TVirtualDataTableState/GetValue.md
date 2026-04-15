---
uid: TVirtualDataTableState.GetValue
description: TVirtualDataTableState.GetValue
---

# TVirtualDataTableState\.GetValue Method

## Overloads

* [TVirtualDataTableState\.GetValue\(Integer\)](#tvirtualdatatablestategetvalueinteger)
* [TVirtualDataTableState\.GetValue\(Integer, Integer\)](#tvirtualdatatablestategetvalueinteger-integer)

# TVirtualDataTableState\.GetValue\(Integer\)
Returns the value for row [Position](Position.md), at the column "column"

## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TVirtualDataTableState/index.md">TVirtualDataTableState</a>.GetValue(const column: Integer): <a href="../TReportValue/index.md">TReportValue</a>; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**column**|Integer|Column identifier returned by [TVirtualDataTable.GetColumn](../TVirtualDataTable/GetColumn.md)|


## See also

* [TVirtualDataTableState](../TVirtualDataTableState/index.md)

# TVirtualDataTableState\.GetValue\(Integer, Integer\)
Returns the value for row "row", at the column "column"\. You need to overload this method only if you want to support DBValue tag\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TVirtualDataTableState/index.md">TVirtualDataTableState</a>.GetValue(const row: Integer; const column: Integer): <a href="../TReportValue/index.md">TReportValue</a>; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row identifier \(0 based\)|
|const|**column**|Integer|Column identifier returned by [TVirtualDataTable.GetColumn](../TVirtualDataTable/GetColumn.md)|


## See also

* [TVirtualDataTableState](../TVirtualDataTableState/index.md)

