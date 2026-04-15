---
uid: TXlsFile.AddScrollBar
description: TXlsFile.AddScrollBar
---

# TXlsFile\.AddScrollBar Method

Adds a ScrollBar to the active sheet\.


## Remarks

Excel supports 2 types of ScrollBars: ActiveX and internal \(In Excel you would add them from the "ActiveX" and "Forms" toolbars respectively\)
The ScrollBars added by this method are of type internal\. ActiveX ScrollBars are not supported\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.AddScrollBar(const anchor: <a href="../../FlexCel.Core/TClientAnchor/index.md">TClientAnchor</a>; const name: string; const linkedCell: <a href="../../FlexCel.Core/TCellAddress/index.md">TCellAddress</a>; const spinProps: <a href="../../FlexCel.Core/TSpinProperties/index.md">TSpinProperties</a>): Integer; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**anchor**|[TClientAnchor](../../FlexCel.Core/TClientAnchor/index.md)|Position for the ScrollBar\.|
|const|**name**|string|Name of the inserted ScrollBar\.|
|const|**linkedCell**|[TCellAddress](../../FlexCel.Core/TCellAddress/index.md)|Cell that will be linked to the ScrollBar\. Set this to null to not link any cell\.|
|const|**spinProps**|[TSpinProperties](../../FlexCel.Core/TSpinProperties/index.md)|Properties for the ScrollBar\.|


## Returns

Object Index of the inserted ScrollBar \(1 based\)\.

## See also

* [TXlsFile](../TXlsFile/index.md)

