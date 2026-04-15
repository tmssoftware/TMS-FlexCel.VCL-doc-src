---
uid: TFlexCelReport.AddTable
description: TFlexCelReport.AddTable
---

# TFlexCelReport\.AddTable Method

## Overloads

* [TFlexCelReport\.AddTable\(string, TArray\<T>\)](#tflexcelreportaddtablestring-tarrayt)
* [TFlexCelReport\.AddTable\(string, TVirtualDataTable\)](#tflexcelreportaddtablestring-tvirtualdatatable)
* [TFlexCelReport\.AddTable\(string, TList\<T>, TDisposeMode\)](#tflexcelreportaddtablestring-tlistt-tdisposemode)
* [TFlexCelReport\.AddTable\(TDataModule, TRecordCountMode, TDisposeMode\)](#tflexcelreportaddtabletdatamodule-trecordcountmode-tdisposemode)
* [TFlexCelReport\.AddTable\(string, TVirtualDataTable, TDisposeMode\)](#tflexcelreportaddtablestring-tvirtualdatatable-tdisposemode)
* [TFlexCelReport\.AddTable\(string, TDataSet, TRecordCountMode, TDisposeMode\)](#tflexcelreportaddtablestring-tdataset-trecordcountmode-tdisposemode)

# TFlexCelReport\.AddTable\(string, TArray\<T>\)
Use this method to tell FlexCel which DataTables are available for the report\. **Note:** If you don't know the tables before running the report \(and you are not using User Tables or Direct SQL\) you can use the [LoadTable](LoadTable.md) event to load them in demand instead of using AddTable\.
This way you will only load the tables you need\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelReport/index.md">TFlexCelReport</a>.AddTable(const tableName: string; const table: TArray&lt;T&gt;); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**tableName**|string|Name that the table will have on the report\.|
|const|**table**|TArray\<T>|Array with data that we want to put into the report\.|


## Examples

To allow a report to use an Array of TCustomer objects you can use the code:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">type</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TCustomer = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  private</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FName: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FBirthday: TDateTime;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  public</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Name</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#0000FF;--shiki-dark:#569CD6"> read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FName;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    Property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Birthday</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TDateTime </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FBirthday;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>


<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Customers: TArray&#x3C;TCustomer>;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">...</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  flexCelReport.AddTable&#x3C;TCustomer>(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Customers'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, Customers);</span></span>
<span class="line"></span></code></pre>



## See also

* [TFlexCelReport](../TFlexCelReport/index.md)

# TFlexCelReport\.AddTable\(string, TVirtualDataTable\)
Use this method to add any custom object as a datasource for FlexCel\. Make sure to read ['Appendix virtual datasets' in the Reports Developer Guide](xref:ReportsDeveloperGuide#appendix-virtual-datasets)\.
Use [AddTable\(string, TDataSet, TRecordCountMode, TDisposeMode\)](AddTable.md#tflexcelreportaddtablestring-tdataset-trecordcountmode-tdisposemode) to add datasets\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelReport/index.md">TFlexCelReport</a>.AddTable(const tableName: string; const table: <a href="../TVirtualDataTable/index.md">TVirtualDataTable</a>); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**tableName**|string|Name that the table will have on the report\.|
|const|**table**|[TVirtualDataTable](../TVirtualDataTable/index.md)|Table that will be available in the report\.|


## See also

* [TFlexCelReport](../TFlexCelReport/index.md)

# TFlexCelReport\.AddTable\(string, TList\<T>, TDisposeMode\)
Use this method to tell FlexCel which DataTables are available for the report\. **Note:** If you don't know the tables before running the report \(and you are not using User Tables or Direct SQL\) you can use the [LoadTable](LoadTable.md) event to load them in demand instead of using AddTable\.
This way you will only load the tables you need\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelReport/index.md">TFlexCelReport</a>.AddTable(const tableName: string; const table: TList&lt;T&gt;; const disposeMode: <a href="../TDisposeMode.md">TDisposeMode</a> = TDisposeMode.DoNotDispose); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**tableName**|string|Name that the table will have on the report\.|
|const|**table**|TList\<T>|TList with data that we want to put into the report\.|
|const|**disposeMode**|[TDisposeMode](../TDisposeMode.md)|**Optional**: Default value is TDisposeMode.DoNotDispose<br /><br />When disposeMode is TDisposeMode\.DisposeTable, FlexCel will take care of disposing this TList after running the report\. Use it when adding tables created on the fly, so you do not have to dispose them yourself\.<br />|


## Examples

To allow a report to use a TList of TCustomer objects you can use the code:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">type</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TCustomer = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  private</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FName: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FBirthday: TDateTime;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  public</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Name</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#0000FF;--shiki-dark:#569CD6"> read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FName;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    Property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Birthday</span><span style="color:#000000;--shiki-dark:#D4D4D4">: TDateTime </span><span style="color:#0000FF;--shiki-dark:#569CD6">read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FBirthday;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>


<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  CustomerList: TObjectList&#x3C;TCustomer>;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">...</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  flexCelReport.AddTable&#x3C;TCustomer>(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Customers'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, CustomerList);</span></span>
<span class="line"></span></code></pre>



## See also

* [TFlexCelReport](../TFlexCelReport/index.md)

# TFlexCelReport\.AddTable\(TDataModule, TRecordCountMode, TDisposeMode\)
Use this method to load all tables on a datamodule at once\. When disposeMode is DoNotDispose, this is equivalent to calling [AddTable\(string, TDataSet, TRecordCountMode, TDisposeMode\)](AddTable.md#tflexcelreportaddtablestring-tdataset-trecordcountmode-tdisposemode) for each of the tables on the dataset\. If disposeMode is DisposeTable, this will make the same as calling AddTable\(\) with disposeTable equal to false for each table on the dataset\. And when finished, all the datamodule will be disposed\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelReport/index.md">TFlexCelReport</a>.AddTable(const tables: TDataModule; const recordCountMode: <a href="../TRecordCountMode.md">TRecordCountMode</a> = TRecordCountMode.Normal; const disposeMode: <a href="../TDisposeMode.md">TDisposeMode</a> = TDisposeMode.DoNotDispose); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**tables**|TDataModule|Datamodule containing the tables to add\.|
|const|**recordCountMode**|[TRecordCountMode](../TRecordCountMode.md)|**Optional**: Default value is TRecordCountMode.Normal<br /><br />|
|const|**disposeMode**|[TDisposeMode](../TDisposeMode.md)|**Optional**: Default value is TDisposeMode.DoNotDispose<br /><br />When disposeMode is TDisposeMode\.DisposeTable, FlexCel will take care of freeing this datamodule after running the report\. Use it when adding datamodules created on the fly, so you do not have to free them yourself\.|


## See also

* [TFlexCelReport](../TFlexCelReport/index.md)

# TFlexCelReport\.AddTable\(string, TVirtualDataTable, TDisposeMode\)
Use this method to add any custom object as a datasource for FlexCel\. Make sure to read ['Appendix virtual datasets' in the Reports Developer Guide](xref:ReportsDeveloperGuide#appendix-virtual-datasets)\.
Use [AddTable\(string, TDataSet, TRecordCountMode, TDisposeMode\)](AddTable.md#tflexcelreportaddtablestring-tdataset-trecordcountmode-tdisposemode) to add datasets\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelReport/index.md">TFlexCelReport</a>.AddTable(const tableName: string; const table: <a href="../TVirtualDataTable/index.md">TVirtualDataTable</a>; const disposeMode: <a href="../TDisposeMode.md">TDisposeMode</a>); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**tableName**|string|Name that the table will have on the report\.|
|const|**table**|[TVirtualDataTable](../TVirtualDataTable/index.md)|Table that will be available in the report\.|
|const|**disposeMode**|[TDisposeMode](../TDisposeMode.md)|When disposeMode is TDisposeMode\.DisposeTable, FlexCel will take care of freeing this table after running the report\. Use it when adding tables created on the fly, so you do not have to free them yourself\.|


## See also

* [TFlexCelReport](../TFlexCelReport/index.md)

# TFlexCelReport\.AddTable\(string, TDataSet, TRecordCountMode, TDisposeMode\)
Use this method to tell FlexCel which DataTables are available for the report\. **Note:** If you don't know the tables before running the report \(and you are not using User Tables or Direct SQL\) you can use the [LoadTable](LoadTable.md) event to load them in demand instead of using AddTable\.
This way you will only load the tables you need\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelReport/index.md">TFlexCelReport</a>.AddTable(const tableName: string; const table: TDataSet; const recordCountMode: <a href="../TRecordCountMode.md">TRecordCountMode</a> = TRecordCountMode.Normal; const disposeMode: <a href="../TDisposeMode.md">TDisposeMode</a> = TDisposeMode.DoNotDispose); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**tableName**|string|Name that the table will have on the report\.|
|const|**table**|TDataSet|Table that will be available to the report\.|
|const|**recordCountMode**|[TRecordCountMode](../TRecordCountMode.md)|**Optional**: Default value is TRecordCountMode.Normal<br /><br />When this property is SlowCount, FlexCel will loop over the records twice: once to get the number of rows to insert, and later to fill the values\. Look at the section "About RecordCount in DataSets" in the reports developer guide\.<br />|
|const|**disposeMode**|[TDisposeMode](../TDisposeMode.md)|**Optional**: Default value is TDisposeMode.DoNotDispose<br /><br />When disposeMode is TDisposeMode\.DisposeTable, FlexCel will take care of disposing this table after running the report\. Use it when adding tables created on the fly, so you do not have to dispose them yourself\.<br />|


## Examples

To allow a report to use Customers and Orders tables, you can use the code:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  flexCelReport.AddTable(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Customers'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, CustomersDataTable);  </span><span style="color:#008000;--shiki-dark:#6A9955">//Add dataset Customers to the report.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  flexCelReport.AddTable(MyDataModule);  </span><span style="color:#008000;--shiki-dark:#6A9955">//Add all the tables on MyDataModule to the report.</span></span>
<span class="line"></span></code></pre>



## See also

* [TFlexCelReport](../TFlexCelReport/index.md)

