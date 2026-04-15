---
uid: TExcelFile.ScrollWindow
description: TExcelFile.ScrollWindow
---

# TExcelFile\.ScrollWindow Method

## Overloads

* [TExcelFile\.ScrollWindow\(Integer, Integer\)](#texcelfilescrollwindowinteger-integer)
* [TExcelFile\.ScrollWindow\(TPanePosition, Integer, Integer\)](#texcelfilescrollwindowtpaneposition-integer-integer)

# TExcelFile\.ScrollWindow\(Integer, Integer\)
Scrolls the window to a specified place\. If the window is split, it will move the left and top panels\.
This property can work in different windows depending on the value of [ActiveWindow](ActiveWindow.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.ScrollWindow(const row: Integer; const col: Integer); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|First visible row\.|
|const|**col**|Integer|First visible column\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.ScrollWindow\(TPanePosition, Integer, Integer\)
Scrolls the window to a specified place\.
This property can work in different windows depending on the value of [ActiveWindow](ActiveWindow.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.ScrollWindow(const panePosition: <a href="../TPanePosition.md">TPanePosition</a>; const row: Integer; const col: Integer); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**panePosition**|[TPanePosition](../TPanePosition.md)|Pane to move\. Note that if you move for example the left column of the upper left pane, you will also move the left column of the lower left pane\.|
|const|**row**|Integer|First visible row\.|
|const|**col**|Integer|First visible column\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

