---
uid: TVirtualDataTable
description: TVirtualDataTable
---

# TVirtualDataTable Class

Base class for a table used on FlexCelReport\.
Inherit from this class and [TVirtualDataTableState](../TVirtualDataTableState/index.md) to create your custom sources of data\.
Make sure you read **['Appendix virtual datasets' in the Reports Developer Guide](xref:ReportsDeveloperGuide#appendix-virtual-datasets)** for more information\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">TVirtualDataTable = class(TFlexCelObject);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new virtual datatable instance and assigns a name to it\.<br />|


## Methods

|Name|Description|
|---|---|
|[CreateState](CreateState.md)|Creates a VirtualDataSetState to be used in a report\. Make sure you override this method on your derived classes and point it to the correct VirtualDataSet descendant\.<br />|
|[FullDataSetColumn&#8203;Count](FullDataSetColumnCount.md)|Returns the columns in the table for a full dataset\. Normally this is the same as [ColumnCount](ColumnCount.md) but your implementation might choose to hide some of the fields available in the full ColumnCount when dumping all fields\.<br />If you change this method, you need also to review [GetFullDataSetColumn](GetFullDataSetColumn.md) so it returns the correct column for the dataset\.<br />|
|[GetFullDataSetColumn](GetFullDataSetColumn.md)|Maps a normal column to a Full Dataset column, in case you aren't outputting the same fields for full datasets as the fields available for a report\. If you are outputting all the fields, then this returns Column\.<br />|
|[GetFullDataSetMapId](GetFullDataSetMapId.md)|Returns an id you can use to map a column name \+ \* to something you can use in [GetFullDataSetColumn](GetFullDataSetColumn.md)|
|[GetColumn](GetColumn.md)|Returns a column identifier that you can later use on [TVirtualData&#8203;Table&#8203;State.&#8203;Get&#8203;Value\(&#8203;&#8203;Integer\)](../TVirtualDataTableState/GetValue.md#tvirtualdatatablestategetvalueinteger)\.<br />Return \-1 if the column does not exist, and make sure this search is case insensitive\.<br />|
|[GetColumnName](GetColumnName.md)|Returns the column name for a column identifier\. This method is the reverse of [GetColumn](GetColumn.md)|
|[GetColumnCaption](GetColumnCaption.md)|Returns the column caption for a column identifier\. This method is used on generic dataset to write the header column\.<br />For most uses, [GetColumnName](GetColumnName.md) will be used\.<br />|
|[FilterData](FilterData.md)|This method should return a new VirtualDataTable instance with the data filtered\. If RowFilter is null, this method should return a copy of the dataset with a different name\.<br />Note that you might have the same data with different states, so this method might be called more than once\.<br />|
|[GetDistinct](GetDistinct.md)|Override this method to return a new VirtualDataSet with unique values\.<br />Note that the returned dataset will not have all the columns this one has, only the ones defined on "filterFields"|
|[GetDetail](GetDetail.md)|Override this method if the table has linked tables that you can use for master detail relationships instead of normal relationships\. This is the case for example in Entity Framework\.<br />|
|[GetRelationWith](GetRelationWith.md)|Override this method if the datatable has intrinsic relationships that you want to use\.<br />For example DataSets have DataRelationships, or Entity Framework tables are related as properties from the  master to the detail\. All those relationships that are not explicitly defined in the report should be returned here\.<br />|
|[Lookup](Lookup.md)|Looks for a key on this dataset and returns the corresponding value\.<br />Note: Remember that VirtualDataSet is stateless, so if you use any caching here, make sure you appropiately lock\(\) this method so there is no possibility of one thread reading the cache when the other is updating it\.<br />|
|[SupportingTable](SupportingTable.md)|This method should return the underlying table used to access the data if there is one\.<br />This will normally return the same instance, but in TOPN and ATLEAST datasets it returns the table used to calculate them\.<br />|


## Properties

|Name|Description|
|---|---|
|[TableName](TableName.md)|Name for the virtual data table\. Note that this name is \*not\* used anywhere in FlexCel code, except to report errors\.<br />The Table names that are used on reports are the ones in [TVirtualData&#8203;Table&#8203;State](../TVirtualDataTableState/index.md)|
|[Locale](Locale.md)|Locale for this dataset\. This might be needed to create datatables with data and the same locale\.<br />|
|[ColumnCount](ColumnCount.md)|Returns the number of columns of the table\.<br />|
|[CreatedBy](CreatedBy.md)|Returns the table that created this one \(by a filter, distinct, etc\), or null if this table  was not created from another VirtualDataTable\.<br />|
|[TempTable](TempTable.md)|If true, this table must be destroyed by the framework\.<br />|


