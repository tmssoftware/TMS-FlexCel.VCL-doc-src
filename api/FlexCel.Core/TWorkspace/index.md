---
uid: TWorkspace
description: TWorkspace
---

# TWorkspace Class

This class links together a group of spreadsheets, so you can recalculate among linked spreadsheets\.
In order to use it, just define an object of this class and add all the files you need for the linked recalculation\.
If you don't know in advance which files you will need, you can use the [LoadLinkedFile](LoadLinkedFile.md) event\.

Note that whenever you recalculate any file in the workspace, all files will be recalculated, so you don't need to calculate them twice\.


## Remarks

Files are case\-insensitive, even if running in Linux\. "a\.xls" is the same as "A\.XLS"

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TWorkspace = class(TFlexCelObject);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new workspace\.<br />|


## Methods

|Name|Description|
|---|---|
|[OnLoadLinkedFile](OnLoadLinkedFile.md)|Replace this event when creating a custom descendant of TWorkspace\. See also [LoadLinkedFile](LoadLinkedFile.md)|
|[Add](Add.md)|Adds a file to the workspace\. Whenever you recalculate any file in this workspace, all linked files will be recalculated too\.<br />**Note that you can't add two files with the same name or same reference twice to this collection\.**|
|[GetFile](GetFile.md)|Returns the file at index\.<br />|
|[Clear](Clear.md)|Removes all files from the workspace\.<br />|
|[Recalc](Recalc.md)|Use this method to force a recalculation of all the spreadsheets in the workspace\. This is the same as calling Recalc\(\) in any of the files in the workspace\.<br />|
|[RecalcAndVerify](RecalcAndVerify.md)|This method will do the same as [TExcelFile.&#8203;Recalc&#8203;AndVerify](../TExcelFile/RecalcAndVerify.md), but for a workspace of files\.<br />|
|[GetEnumerator](GetEnumerator.md)|Returns an enumerator with all the files in the Workspace\.<br />|


## Properties

|Name|Description|
|---|---|
|[CellStackTrace&#8203;MaxSize](CellStackTraceMaxSize.md)|Defines what is the maximum number of entries returned in the stack trace when calling [RecalcAndVerify](RecalcAndVerify.md)\.<br />In order to keep the stack trace not too big, this number is limited, but if you need a bigger stack trace to see the full loop of cells, you can increase this number\.<br />|
|[Count](Count.md)|Number of linked files in this workspace\.<br />|
|[Item\[const fileName\]](Itemconst-fileName.md)|Returns the Excel file with the given name\. To get the file at a given position, use [GetFile](GetFile.md)|


## Events

|Name|Description|
|---|---|
|[LoadLinkedFile](LoadLinkedFile.md)|Use this event to load files to recalculate on demand, if you don't know a priori which linked files you need\.<br />Note that this event will add the new file to the workspace\.<br />It will only be called once for each file, even if the file is used many times\.<br />|


## Examples

If you have 3 files, xls1, xls2 and xls3, you can recalculate them together with the following code:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  work: TWorkspace;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //The Workspace will own the TXlsFile objects,</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //so we won't need to free them.</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //If we set the parameter to false,</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //we would have to manually free the TXlsFile objects.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  work := TWorkspace.Create(</span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    work.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Add</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#A31515;--shiki-dark:#CE9178">'xls1'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TXlsFile.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'File1.xlsx'</span><span style="color:#000000;--shiki-dark:#D4D4D4">));</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    work.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Add</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#A31515;--shiki-dark:#CE9178">'xls2'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TXlsFile.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'File2.xlsx'</span><span style="color:#000000;--shiki-dark:#D4D4D4">));</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    work.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Add</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#A31515;--shiki-dark:#CE9178">'xls3'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TXlsFile.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'File3.xlsx'</span><span style="color:#000000;--shiki-dark:#D4D4D4">));</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">   //Either work.Recalc, xls1.Recalc, xls2.Recalc or xls3.Recalc will recalculate all the files in the workspace.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    work.Recalc(</span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    work.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>



