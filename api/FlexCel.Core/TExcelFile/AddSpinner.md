---
uid: TExcelFile.AddSpinner
description: TExcelFile.AddSpinner
---

# TExcelFile\.AddSpinner Method

Adds a Spinner to the active sheet\.


## Remarks

Excel supports 2 types of spinners: ActiveX and internal \(In Excel you would add them from the "ActiveX" and "Forms" toolbars respectively\)
The spinners added by this method are of type internal\. ActiveX spinners are not supported\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.AddSpinner(const anchor: <a href="../TClientAnchor/index.md">TClientAnchor</a>; const name: string; const linkedCell: <a href="../TCellAddress/index.md">TCellAddress</a>; const spinProps: <a href="../TSpinProperties/index.md">TSpinProperties</a>): Integer; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**anchor**|[TClientAnchor](../TClientAnchor/index.md)|Position for the spinner\.|
|const|**name**|string|Name of the inserted spinner\.|
|const|**linkedCell**|[TCellAddress](../TCellAddress/index.md)|Cell that will be linked to the spinner\. Set this to null to not link any cell\.|
|const|**spinProps**|[TSpinProperties](../TSpinProperties/index.md)|Properties for the spinner\.|


## Returns

Object Index of the inserted spinner \(1 based\)\.

## See also

* [TExcelFile](../TExcelFile/index.md)

