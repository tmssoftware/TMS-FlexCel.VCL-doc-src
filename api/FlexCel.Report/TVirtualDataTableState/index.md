---
uid: TVirtualDataTableState
description: TVirtualDataTableState
---

# TVirtualDataTableState Class

A table that corresponds to a band on the report\.
Make sure you read **['Appendix virtual datasets' in the Reports Developer Guide](xref:ReportsDeveloperGuide#appendix-virtual-datasets)** for more information\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">TVirtualDataTableState = class(TFlexCelObject);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Constructs a new VirtualDataTable&#8203;State with the specified name\. Note that you will not call this constructor directly, new VirtualDataTable&#8203;State instances will be created only by [TVirtualData&#8203;Table.&#8203;Create&#8203;State](../TVirtualDataTable/CreateState.md)|


## Methods

|Name|Description|
|---|---|
|[TryAggregate](TryAggregate.md)|This method is used by the "AGGREGATE" tag in a FlexCel report to calculate the maximum/&#8203;minimum/&#8203;average/&#8203;etc of the values in the table\. If you don't implement this method, FlexCel will still calculate those values by looping through the dataset, but if you have a faster way to do it \(like with a "select max\(field\) from table"\) then implement this method and return true\.<br />|
|[Eof](Eof.md)|This method returns if we have reached the last record in the table\. The default implementation just sees if [Position](Position.md) = [RowCount](RowCount.md)\. If RowCount is slow and you have a  faster way to know if you are at the end, override this method\.<br />|
|[GetValue](GetValue.md)|**Overloaded<br />**  [GetValue\(Integer\)](GetValue.md#tvirtualdatatablestategetvalueinteger)<br />  [GetValue\(Integer, Integer\)](GetValue.md#tvirtualdatatablestategetvalueinteger-integer)<br />|
|[MoveFirst](MoveFirst.md)|This method is called when we want to move to the first record\.<br />You can always know the current record with [Position](Position.md)|
|[MoveNext](MoveNext.md)|This method is called when we want to move to the next record\.<br />You can always know the current record with [Position](Position.md)|
|[MoveMasterRecord](MoveMasterRecord.md)|This method will be called each time that the master datasource moves its position\. Use it to filter the data returned if this is used on a master\-detail relationship\.<br />|
|[GetValueAndResync](GetValueAndResync.md)|This method will be called when you need to ensure the position of the datasource is correct\.<br />Normally there is no need to do anything here, but for example TDataSet must ensure that the position of the TDataSet is the correct one, since a child might be using the same DataSet instance and have moved it\.<br />|
|[PushPhysicalPosition](PushPhysicalPosition.md)|This method is called when we need to ensure the position in the dataset is correct\. If the data is stateless \(like an array\), then this method can be empty\. For data with state \(like a TDataSet\) you need to save the position of the physical dataset here and restore it in \<\#see PopPhysicalPosition>&#8203;\.&#8203;<br />|
|[PopPhysicalPosition](PopPhysicalPosition.md)|This method is called when we need to ensure the position in the dataset is correct\. If the data is stateless \(like an array\), then this method can be empty\. For data with state \(like a TDataSet\) you need to save the position of the physical dataset in\<\#see PushPhysical&#8203;Position> and restore it here\.<br />|
|[CheckDuplicates](CheckDuplicates.md)|This method will be called to let you find out if master datasources share the same internal data\.<br />There is normally no need to do anything here, but TDataSet needs to check if there are repeated instances\.<br />|
|[FilteredRowCount](FilteredRowCount.md)|This method will be called when a Split master wants to know how many records its detail has\. For example, if the detail has 30 records and the split is at 10, the Split master will call this method to find out that it has to return 3 on its own record count\.<br />You need to filter the data here depending on the master detail relationships, but not on the splitLink\.<br />|


## Properties

|Name|Description|
|---|---|
|[TableData](TableData.md)|The VirtualDataTable that created this instance\.<br />|
|[Position](Position.md)|Returns the active row on the table\. \(0 based\)  You should use this value to return the values on [GetValue\(&#8203;&#8203;Integer\)](GetValue.md#tvirtualdatatablestategetvalueinteger)|
|[TableName](TableName.md)|Returns the table name assigned on the template to this dataset\. Note that this name is the one on the bands in the template\.<br />|
|[RowCount](RowCount.md)|Returns the number of rows available on the dataset, for the current state\. Note that this method can be called many times, so it should be fast\.<br />Use a cache if necessary\. Do \*not\* use something like "return select count\(\*\) from table" here, it would be too slow\.<br />|


