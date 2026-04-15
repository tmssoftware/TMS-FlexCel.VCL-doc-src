---
uid: TXlsFile.AddListBox
description: TXlsFile.AddListBox
---

# TXlsFile\.AddListBox Method

Adds a ListBox to the active sheet\.


## Remarks

Excel supports 2 types of listboxes: ActiveX and internal \(In Excel you would add them from the "ActiveX" and "Forms" toolbars respectively\)
The listboxes added by this method are of type internal\. ActiveX listboxes are not supported\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.AddListBox(const anchor: <a href="../../FlexCel.Core/TClientAnchor/index.md">TClientAnchor</a>; const name: string; const linkedCell: <a href="../../FlexCel.Core/TCellAddress/index.md">TCellAddress</a>; const inputRange: <a href="../../FlexCel.Core/TCellAddressRange/index.md">TCellAddressRange</a>; const selectionType: <a href="../../FlexCel.Core/TListBoxSelectionType.md">TListBoxSelectionType</a>; const selectedItem: Integer): Integer; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**anchor**|[TClientAnchor](../../FlexCel.Core/TClientAnchor/index.md)|Position for the listbox\.|
|const|**name**|string|Name of the inserted listbox\.|
|const|**linkedCell**|[TCellAddress](../../FlexCel.Core/TCellAddress/index.md)|Cell that will be linked to the listbox\. Set this to null to not link any cell\.|
|const|**inputRange**|[TCellAddressRange](../../FlexCel.Core/TCellAddressRange/index.md)|Range of cells with the values that the listbox will display\.|
|const|**selectionType**|[TListBoxSelection&#8203;Type](../../FlexCel.Core/TListBoxSelectionType.md)|How items are selected in the listbox\.|
|const|**selectedItem**|Integer|Item that will be selected, starting at 1\. 0 means no selected item\.|


## Returns

Object Index of the inserted listbox \(1 based\)\.

## See also

* [TXlsFile](../TXlsFile/index.md)

