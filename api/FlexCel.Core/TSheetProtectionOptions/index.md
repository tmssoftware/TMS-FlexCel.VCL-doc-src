---
uid: TSheetProtectionOptions
description: TSheetProtectionOptions
---

# TSheetProtectionOptions Record

Options for protecting a sheet\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TSheetProtectionOptions = record;</code></pre>

## Fields

|Name|Description|
|---|---|
|[Contents](Contents.md)|Sheet contents are protected|
|[Objects](Objects.md)|If TRUE, objects on the sheet are protected\. Note that this setting behaves like [Scenarios](Scenarios.md) and opposite from all the rest\.<br />In the other settings, FALSE means that the setting is protected, TRUE that the setting can be changed\.<br />|
|[Scenarios](Scenarios.md)|If TRUE, scenarios on the sheet are protected\. Note that this setting behaves like [Objects](Objects.md) and opposite from all the rest\.<br />In the other settings, FALSE means that the setting is protected, TRUE that the setting can be changed\.<br />|
|[CellFormatting](CellFormatting.md)|If TRUE, users are allowed to change this setting\. Set it to FALSE to disable this property\. Only on Excel >= XP\.|
|[ColumnFormatting](ColumnFormatting.md)|If TRUE, users are allowed to change this setting\. Set it to FALSE to disable this property\. Only on Excel >= XP\.|
|[RowFormatting](RowFormatting.md)|If TRUE, users are allowed to change this setting\. Set it to FALSE to disable this property\. Only on Excel >= XP\.|
|[InsertColumns](InsertColumns.md)|If TRUE, users are allowed to change this setting\. Set it to FALSE to disable this property\. Only on Excel >= XP\.|
|[InsertRows](InsertRows.md)|If TRUE, users are allowed to change this setting\. Set it to FALSE to disable this property\. Only on Excel >= XP\.|
|[InsertHyperlinks](InsertHyperlinks.md)|If TRUE, users are allowed to change this setting\. Set it to FALSE to disable this property\. Only on Excel >= XP\.|
|[DeleteColumns](DeleteColumns.md)|If TRUE, users are allowed to change this setting\. Set it to FALSE to disable this property\. Only on Excel >= XP\.|
|[DeleteRows](DeleteRows.md)|If TRUE, users are allowed to change this setting\. Set it to FALSE to disable this property\. Only on Excel >= XP\.|
|[SelectLockedCells](SelectLockedCells.md)|If TRUE, users are allowed to change this setting\. Set it to FALSE to disable this property\. Only on Excel >= XP\.|
|[SortCellRange](SortCellRange.md)|If TRUE, users are allowed to change this setting\. Set it to FALSE to disable this property\. Only on Excel >= XP\.|
|[EditAutoFilters](EditAutoFilters.md)|If TRUE, users are allowed to change this setting\. Set it to FALSE to disable this property\. Only on Excel >= XP\.|
|[EditPivotTables](EditPivotTables.md)|If TRUE, users are allowed to change this setting\. Set it to FALSE to disable this property\. Only on Excel >= XP\.|
|[SelectUnlockedCells](SelectUnlockedCells.md)|If TRUE, users are allowed to change this setting\. Set it to FALSE to disable this property\. Only on Excel >= XP\.|


## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create](Create.md#tsheetprotectionoptionscreate)<br />  [Create\(Boolean\)](Create.md#tsheetprotectionoptionscreateboolean)<br />  [Create\(TProtectionType\)](Create.md#tsheetprotectionoptionscreatetprotectiontype)<br />|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


