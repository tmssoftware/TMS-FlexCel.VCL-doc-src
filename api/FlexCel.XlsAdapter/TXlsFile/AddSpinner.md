---
uid: TXlsFile.AddSpinner
description: TXlsFile.AddSpinner
---

# TXlsFile\.AddSpinner Method

Adds a Spinner to the active sheet\.


## Remarks

Excel supports 2 types of spinners: ActiveX and internal \(In Excel you would add them from the "ActiveX" and "Forms" toolbars respectively\)
The spinners added by this method are of type internal\. ActiveX spinners are not supported\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.AddSpinner(const anchor: <a href="../../FlexCel.Core/TClientAnchor/index.md">TClientAnchor</a>; const name: string; const linkedCell: <a href="../../FlexCel.Core/TCellAddress/index.md">TCellAddress</a>; const spinProps: <a href="../../FlexCel.Core/TSpinProperties/index.md">TSpinProperties</a>): Integer; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**anchor**|[TClientAnchor](../../FlexCel.Core/TClientAnchor/index.md)|Position for the spinner\.|
|const|**name**|string|Name of the inserted spinner\.|
|const|**linkedCell**|[TCellAddress](../../FlexCel.Core/TCellAddress/index.md)|Cell that will be linked to the spinner\. Set this to null to not link any cell\.|
|const|**spinProps**|[TSpinProperties](../../FlexCel.Core/TSpinProperties/index.md)|Properties for the spinner\.|


## Returns

Object Index of the inserted spinner \(1 based\)\.

## See also

* [TXlsFile](../TXlsFile/index.md)

