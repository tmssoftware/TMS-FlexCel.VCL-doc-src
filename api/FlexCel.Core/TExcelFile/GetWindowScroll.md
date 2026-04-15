---
uid: TExcelFile.GetWindowScroll
description: TExcelFile.GetWindowScroll
---

# TExcelFile\.GetWindowScroll Method

## Overloads

* [TExcelFile\.GetWindowScroll](#texcelfilegetwindowscroll)
* [TExcelFile\.GetWindowScroll\(TPanePosition\)](#texcelfilegetwindowscrolltpaneposition)

# TExcelFile\.GetWindowScroll
Returns the window scroll for the main pane\.
This property can work in different windows depending on the value of [ActiveWindow](ActiveWindow.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetWindowScroll: <a href="../TCellAddress/index.md">TCellAddress</a>; overload;</code></pre>

## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.GetWindowScroll\(TPanePosition\)
Returns the window scroll for a specified pane\.
This property can work in different windows depending on the value of [ActiveWindow](ActiveWindow.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetWindowScroll(const panePosition: <a href="../TPanePosition.md">TPanePosition</a>): <a href="../TCellAddress/index.md">TCellAddress</a>; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**panePosition**|[TPanePosition](../TPanePosition.md)|Pane to return\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

