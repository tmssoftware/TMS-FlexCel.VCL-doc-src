---
uid: TExcelFile.AddComboBox
description: TExcelFile.AddComboBox
---

# TExcelFile\.AddComboBox Method

Adds a ComboBox to the active sheet\.


## Remarks

Excel supports 2 types of comboboxes: ActiveX and internal \(In Excel you would add them from the "ActiveX" and "Forms" toolbars respectively\)
The comboboxes added by this method are of type internal\. ActiveX comboboxes are not supported\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.AddComboBox(const anchor: <a href="../TClientAnchor/index.md">TClientAnchor</a>; const name: string; const linkedCell: <a href="../TCellAddress/index.md">TCellAddress</a>; const inputRange: <a href="../TCellAddressRange/index.md">TCellAddressRange</a>; const selectedItem: Integer): Integer; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**anchor**|[TClientAnchor](../TClientAnchor/index.md)|Position for the combobox\.|
|const|**name**|string|Name of the inserted combobox\.|
|const|**linkedCell**|[TCellAddress](../TCellAddress/index.md)|Cell that will be linked to the combobox\. Set this to null to not link any cell\.|
|const|**inputRange**|[TCellAddressRange](../TCellAddressRange/index.md)|Range of cells with the values that the combobox will display\.|
|const|**selectedItem**|Integer|Item that will be selected, starting at 1\. 0 means no selected item\.|


## Returns

Object Index of the inserted combobox \(1 based\)\.

## See also

* [TExcelFile](../TExcelFile/index.md)

