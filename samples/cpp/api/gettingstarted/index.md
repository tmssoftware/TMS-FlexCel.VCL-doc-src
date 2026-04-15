---
uid: GettingStarted-CPlusPlus
description: GettingStarted-CPlusPlus
---


# Getting started (C++)

> [!Note]
> This demo is available in your FlexCel installation at ***&lt;FlexCel Install Folder>*\\Demo\\Cpp\\Modules\\10\.API\\10\.GettingStarted** and also at [https:&#8203;//&#8203;github.&#8203;com/&#8203;tmssoftware/&#8203;TMS-&#8203;FlexCel.&#8203;VCL-&#8203;demos/&#8203;tree/&#8203;master/&#8203;Cpp/&#8203;Modules/&#8203;10.&#8203;API/&#8203;10.&#8203;Getting&#8203;Started](https://github\.com/tmssoftware/TMS\-FlexCel\.VCL\-demos/tree/master/Cpp/Modules/10\.API/10\.GettingStarted)


## Overview


A simple demo showing how to create an Excel file with the API from scratch.

## Concepts


- Before using FlexCel, you have to add
  \"**uses FlexCel.VCLSupport**\", \"**uses FlexCel.Core**\" and \"**uses FlexCel.XlsAdapter**\" to
  your uses statements. 
  For a FireMonkey app, you would add \"**uses FlexCel.FMXSupport**\"
  instead of \"**uses FlexCel.VCLSupport**\"
 You need to use FMXSupport/VCLSupport units once in your app, so FlexCel can initialize the correct graphics engine. There is no need to add them more than once.

- The most important class here is the [TXlsFile](~/api/FlexCel.XlsAdapter/TXlsFile/index.md) class, from where
  you can read and write to any Excel 2 or newer file.

- To set the value for a cell, use [TXlsFile.SetCellValue](~/api/FlexCel.XlsAdapter/TXlsFile/SetCellValue.md). You can
  set any kind of object here, not just text. If you set it to
  a [TFormula](~/api/FlexCel.Core/TFormula/index.md) object, you will enter a formula.

- As explained in the [FlexCel API Developer Guide](~/guides/api-developer-guide.md), formats in Excel are indexes to an XF (e**X**tended **F**ormat list) 
  To modify the format on a cell, you have to assign an XF index to
  that cell. To create new XF formats, use [TXlsFile.AddFormat](~/api/FlexCel.XlsAdapter/TXlsFile/AddFormat.md)

## Files

### GettingStarted.cpp

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#008000;--shiki-dark:#6A9955">//---------------------------------------------------------------------------</span></span>
<span class="line"></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#include</span><span style="color:#A31515;--shiki-dark:#CE9178"> &#x3C;vcl.h></span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#pragma</span><span style="color:#E50000;--shiki-dark:#9CDCFE"> hdrstop</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#include</span><span style="color:#A31515;--shiki-dark:#CE9178"> &#x3C;tchar.h></span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">//---------------------------------------------------------------------------</span></span>
<span class="line"></span>
<span class="line"><span style="color:#795E26;--shiki-dark:#DCDCAA">USEFORM</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#A31515;--shiki-dark:#CE9178">"UGettingStarted.cpp"</span><span style="color:#000000;--shiki-dark:#D4D4D4">, FGettingStarted);</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">//---------------------------------------------------------------------------</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">int</span><span style="color:#000000;--shiki-dark:#D4D4D4"> WINAPI </span><span style="color:#795E26;--shiki-dark:#DCDCAA">_tWinMain</span><span style="color:#000000;--shiki-dark:#D4D4D4">(HINSTANCE, HINSTANCE, LPTSTR, </span><span style="color:#0000FF;--shiki-dark:#569CD6">int</span><span style="color:#000000;--shiki-dark:#D4D4D4">)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">{</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">	try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	{</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">		Application</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">Initialize</span><span style="color:#000000;--shiki-dark:#D4D4D4">();</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">		Application</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#001080;--shiki-dark:#9CDCFE">MainFormOnTaskBar</span><span style="color:#000000;--shiki-dark:#D4D4D4"> = </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">		Application</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">CreateForm</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#795E26;--shiki-dark:#DCDCAA">__classid</span><span style="color:#000000;--shiki-dark:#D4D4D4">(TFGettingStarted), &#x26;FGettingStarted);</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">		Application</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">Run</span><span style="color:#000000;--shiki-dark:#D4D4D4">();</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	}</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">	catch</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (Exception &#x26;exception)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	{</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">		Application</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">ShowException</span><span style="color:#000000;--shiki-dark:#D4D4D4">(&#x26;exception);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	}</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">	catch</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (...)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	{</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">		try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">		{</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">			throw</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Exception</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#A31515;--shiki-dark:#CE9178">""</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">		}</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">		catch</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (Exception &#x26;exception)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">		{</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">			Application</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">ShowException</span><span style="color:#000000;--shiki-dark:#D4D4D4">(&#x26;exception);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">		}</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	}</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">	return</span><span style="color:#098658;--shiki-dark:#B5CEA8"> 0</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">}</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">//---------------------------------------------------------------------------</span></span>
<span class="line"></span>
<span class="line"></span></code></pre>


### UGettingStarted.cpp

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#008000;--shiki-dark:#6A9955">// ---------------------------------------------------------------------------</span></span>
<span class="line"></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#include</span><span style="color:#A31515;--shiki-dark:#CE9178"> &#x3C;vcl.h></span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#pragma</span><span style="color:#E50000;--shiki-dark:#9CDCFE"> hdrstop</span></span>
<span class="line"></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#include</span><span style="color:#A31515;--shiki-dark:#CE9178"> "UGettingStarted.h"</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">// ---------------------------------------------------------------------------</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#pragma</span><span style="color:#E50000;--shiki-dark:#9CDCFE"> package</span><span style="color:#0000FF;--shiki-dark:#569CD6">(</span><span style="color:#E50000;--shiki-dark:#9CDCFE">smart_init</span><span style="color:#0000FF;--shiki-dark:#569CD6">)</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#pragma</span><span style="color:#E50000;--shiki-dark:#9CDCFE"> resource</span><span style="color:#A31515;--shiki-dark:#CE9178"> "*.dfm"</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">TFGettingStarted *FGettingStarted;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">// ---------------------------------------------------------------------------</span></span>
<span class="line"><span style="color:#267F99;--shiki-dark:#4EC9B0">__fastcall</span><span style="color:#267F99;--shiki-dark:#4EC9B0"> TFGettingStarted</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">TFGettingStarted</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#267F99;--shiki-dark:#4EC9B0">TComponent</span><span style="color:#0000FF;--shiki-dark:#569CD6">*</span><span style="color:#001080;--shiki-dark:#9CDCFE"> Owner</span><span style="color:#000000;--shiki-dark:#D4D4D4">) : </span><span style="color:#795E26;--shiki-dark:#DCDCAA">TForm</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Owner)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">{</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">}</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">// ---------------------------------------------------------------------------</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">void</span><span style="color:#0000FF;--shiki-dark:#569CD6"> __fastcall</span><span style="color:#267F99;--shiki-dark:#4EC9B0"> TFGettingStarted</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">btnCreateFileClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#267F99;--shiki-dark:#4EC9B0">TObject</span><span style="color:#0000FF;--shiki-dark:#569CD6"> *</span><span style="color:#001080;--shiki-dark:#9CDCFE">Sender</span><span style="color:#000000;--shiki-dark:#D4D4D4">) {</span></span>
<span class="line"><span style="color:#795E26;--shiki-dark:#DCDCAA">	CreateFile</span><span style="color:#000000;--shiki-dark:#D4D4D4">();</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">}</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">// ---------------------------------------------------------------------------</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">void</span><span style="color:#0000FF;--shiki-dark:#569CD6"> __fastcall</span><span style="color:#267F99;--shiki-dark:#4EC9B0"> TFGettingStarted</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">CreateFile</span><span style="color:#000000;--shiki-dark:#D4D4D4">() {</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	TExcelFile *Xls = </span><span style="color:#AF00DB;--shiki-dark:#C586C0">new</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TXlsFile</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	__try {</span></span>
<span class="line"><span style="color:#795E26;--shiki-dark:#DCDCAA">		AddData</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Xls);</span></span>
<span class="line"><span style="color:#795E26;--shiki-dark:#DCDCAA">		ShowOpenDialog</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Xls);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	}</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	__finally {</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">		delete</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Xls;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	}</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">}</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">void</span><span style="color:#0000FF;--shiki-dark:#569CD6"> __fastcall</span><span style="color:#267F99;--shiki-dark:#4EC9B0"> TFGettingStarted</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">ShowOpenDialog</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#267F99;--shiki-dark:#4EC9B0">TExcelFile</span><span style="color:#0000FF;--shiki-dark:#569CD6"> *</span><span style="color:#001080;--shiki-dark:#9CDCFE">Xls</span><span style="color:#000000;--shiki-dark:#D4D4D4">) {</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">	if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (!</span><span style="color:#001080;--shiki-dark:#9CDCFE">SaveDialog</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">Execute</span><span style="color:#000000;--shiki-dark:#D4D4D4">())</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">		return</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">	Xls</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">Save</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#001080;--shiki-dark:#9CDCFE">SaveDialog</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#001080;--shiki-dark:#9CDCFE">FileName</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">	// No need to delete the file first, since AllowOverWriteFiles is true in XlsAdapter.</span></span>
<span class="line"></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">	if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (</span><span style="color:#795E26;--shiki-dark:#DCDCAA">MessageDlg</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#A31515;--shiki-dark:#CE9178">L"Do you want to open the generated file?"</span><span style="color:#000000;--shiki-dark:#D4D4D4">, mtConfirmation,</span></span>
<span class="line"><span style="color:#795E26;--shiki-dark:#DCDCAA">		 TMsgDlgButtons</span><span style="color:#000000;--shiki-dark:#D4D4D4">() &#x3C;&#x3C; mbYes &#x3C;&#x3C; mbNo, </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">) == mrYes) {</span></span>
<span class="line"><span style="color:#795E26;--shiki-dark:#DCDCAA">		ShellExecute</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">L"open"</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#001080;--shiki-dark:#9CDCFE">SaveDialog</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#001080;--shiki-dark:#9CDCFE">FileName</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span><span style="color:#795E26;--shiki-dark:#DCDCAA">c_str</span><span style="color:#000000;--shiki-dark:#D4D4D4">(), </span><span style="color:#0000FF;--shiki-dark:#569CD6">NULL</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">NULL</span><span style="color:#000000;--shiki-dark:#D4D4D4">,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">			SW_SHOWNORMAL);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	}</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">}</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">// ---------------------------------------------------------------------------</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">void</span><span style="color:#0000FF;--shiki-dark:#569CD6"> __fastcall</span><span style="color:#267F99;--shiki-dark:#4EC9B0"> TFGettingStarted</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">AddData</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#267F99;--shiki-dark:#4EC9B0">TExcelFile</span><span style="color:#0000FF;--shiki-dark:#569CD6"> *</span><span style="color:#001080;--shiki-dark:#9CDCFE">Xls</span><span style="color:#000000;--shiki-dark:#D4D4D4">) {</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">	// Create a new file. We could also open an existing file with Xls.Open</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">	Xls</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">NewFile</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#267F99;--shiki-dark:#4EC9B0">TExcelFileFormat</span><span style="color:#000000;--shiki-dark:#D4D4D4">::v2019);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">	// Set some cell values.</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">	Xls</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">SetCellValue</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#267F99;--shiki-dark:#4EC9B0">TCellValue</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">Create</span><span style="color:#000000;--shiki-dark:#D4D4D4">((String)</span><span style="color:#A31515;--shiki-dark:#CE9178">L"Hello to the world"</span><span style="color:#000000;--shiki-dark:#D4D4D4">));</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">	Xls</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">SetCellValue</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#098658;--shiki-dark:#B5CEA8">2</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#267F99;--shiki-dark:#4EC9B0">TCellValue</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">Create</span><span style="color:#000000;--shiki-dark:#D4D4D4">((</span><span style="color:#0000FF;--shiki-dark:#569CD6">double</span><span style="color:#000000;--shiki-dark:#D4D4D4">)</span><span style="color:#098658;--shiki-dark:#B5CEA8">3</span><span style="color:#000000;--shiki-dark:#D4D4D4">));</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">	Xls</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">SetCellValue</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#098658;--shiki-dark:#B5CEA8">3</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#267F99;--shiki-dark:#4EC9B0">TCellValue</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">Create</span><span style="color:#000000;--shiki-dark:#D4D4D4">((</span><span style="color:#0000FF;--shiki-dark:#569CD6">double</span><span style="color:#000000;--shiki-dark:#D4D4D4">)</span><span style="color:#098658;--shiki-dark:#B5CEA8">2.1</span><span style="color:#000000;--shiki-dark:#D4D4D4">));</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">	Xls</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">SetCellValue</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#098658;--shiki-dark:#B5CEA8">4</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#267F99;--shiki-dark:#4EC9B0">TCellValue</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">Create</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#267F99;--shiki-dark:#4EC9B0">TFormula</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">Create</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#A31515;--shiki-dark:#CE9178">L"=Sum(A2, A3)"</span><span style="color:#000000;--shiki-dark:#D4D4D4">)));</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">	// Note that formulas always are in English. This means use "," to separate arguments, not ";".</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">	// Get path for images from disk.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	UnicodeString PathToImage = </span><span style="color:#795E26;--shiki-dark:#DCDCAA">IncludeTrailingPathDelimiter</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#795E26;--shiki-dark:#DCDCAA">ExtractFilePath</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#795E26;--shiki-dark:#DCDCAA">ParamStr</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">))) +</span></span>
<span class="line"><span style="color:#A31515;--shiki-dark:#CE9178">		L"..</span><span style="color:#EE0000;--shiki-dark:#D7BA7D">\\</span><span style="color:#A31515;--shiki-dark:#CE9178">..</span><span style="color:#EE0000;--shiki-dark:#D7BA7D">\\</span><span style="color:#A31515;--shiki-dark:#CE9178">poweredbyflexcel.png"</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">	//Add a new image on cell F2</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">	Xls</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">AddImage</span><span style="color:#000000;--shiki-dark:#D4D4D4">(PathToImage,</span></span>
<span class="line"><span style="color:#795E26;--shiki-dark:#DCDCAA">		TImageProperties_Create</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#267F99;--shiki-dark:#4EC9B0">TClientAnchor</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">Create</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#267F99;--shiki-dark:#4EC9B0">TFlxAnchorType</span><span style="color:#000000;--shiki-dark:#D4D4D4">::MoveAndResize,</span></span>
<span class="line"><span style="color:#098658;--shiki-dark:#B5CEA8">		2</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">6</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">5</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">8</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">), PathToImage, PathToImage));</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">	// Add a comment on cell a2</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">	Xls</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">SetComment</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#098658;--shiki-dark:#B5CEA8">2</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">L"This is a comment"</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">	// Custom Format cells a2 and a3</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	TFlxFormat fmt = </span><span style="color:#001080;--shiki-dark:#9CDCFE">Xls</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#001080;--shiki-dark:#9CDCFE">GetDefaultFormat</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">	// Always initialize the record with an existing format.</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">	fmt</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span><span style="color:#001080;--shiki-dark:#9CDCFE">Font</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span><span style="color:#001080;--shiki-dark:#9CDCFE">Name</span><span style="color:#000000;--shiki-dark:#D4D4D4"> = </span><span style="color:#A31515;--shiki-dark:#CE9178">L"Times New Roman"</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">	fmt</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span><span style="color:#001080;--shiki-dark:#9CDCFE">Font</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span><span style="color:#001080;--shiki-dark:#9CDCFE">Color</span><span style="color:#000000;--shiki-dark:#D4D4D4"> = </span><span style="color:#267F99;--shiki-dark:#4EC9B0">TExcelColor</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">_op_Implicit</span><span style="color:#000000;--shiki-dark:#D4D4D4">(clRed);</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">	fmt</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span><span style="color:#001080;--shiki-dark:#9CDCFE">FillPattern</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span><span style="color:#001080;--shiki-dark:#9CDCFE">Pattern</span><span style="color:#000000;--shiki-dark:#D4D4D4"> = </span><span style="color:#267F99;--shiki-dark:#4EC9B0">TFlxPatternStyle</span><span style="color:#000000;--shiki-dark:#D4D4D4">::LightDown;</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">	fmt</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span><span style="color:#001080;--shiki-dark:#9CDCFE">FillPattern</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span><span style="color:#001080;--shiki-dark:#9CDCFE">FgColor</span><span style="color:#000000;--shiki-dark:#D4D4D4"> = </span><span style="color:#267F99;--shiki-dark:#4EC9B0">TExcelColor</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">_op_Implicit</span><span style="color:#000000;--shiki-dark:#D4D4D4">(clBlue);</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">	fmt</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span><span style="color:#001080;--shiki-dark:#9CDCFE">FillPattern</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span><span style="color:#001080;--shiki-dark:#9CDCFE">BgColor</span><span style="color:#000000;--shiki-dark:#D4D4D4"> = </span><span style="color:#267F99;--shiki-dark:#4EC9B0">TExcelColor</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">_op_Implicit</span><span style="color:#000000;--shiki-dark:#D4D4D4">(clWhite);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">	// You can call AddFormat as many times as you want, it will never add a format twice.</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">	// But if you know the format you are going to use, you can get some extra CPU cycles by</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">	// calling addformat once and saving the result into a variable.</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">	int</span><span style="color:#000000;--shiki-dark:#D4D4D4"> XF = </span><span style="color:#001080;--shiki-dark:#9CDCFE">Xls</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">AddFormat</span><span style="color:#000000;--shiki-dark:#D4D4D4">(fmt);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">	Xls</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">SetCellFormat</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#098658;--shiki-dark:#B5CEA8">2</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, XF);</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">	Xls</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">SetCellFormat</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#098658;--shiki-dark:#B5CEA8">3</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, XF);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">	fmt</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span><span style="color:#001080;--shiki-dark:#9CDCFE">Rotation</span><span style="color:#000000;--shiki-dark:#D4D4D4"> = </span><span style="color:#098658;--shiki-dark:#B5CEA8">45</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">	fmt</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span><span style="color:#001080;--shiki-dark:#9CDCFE">Font</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span><span style="color:#001080;--shiki-dark:#9CDCFE">Size20</span><span style="color:#000000;--shiki-dark:#D4D4D4"> = </span><span style="color:#098658;--shiki-dark:#B5CEA8">400</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">	fmt</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span><span style="color:#001080;--shiki-dark:#9CDCFE">FillPattern</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span><span style="color:#001080;--shiki-dark:#9CDCFE">Pattern</span><span style="color:#000000;--shiki-dark:#D4D4D4"> = </span><span style="color:#267F99;--shiki-dark:#4EC9B0">TFlxPatternStyle</span><span style="color:#000000;--shiki-dark:#D4D4D4">::Solid;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">	int</span><span style="color:#000000;--shiki-dark:#D4D4D4"> XF2 = </span><span style="color:#001080;--shiki-dark:#9CDCFE">Xls</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">AddFormat</span><span style="color:#000000;--shiki-dark:#D4D4D4">(fmt);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">	// Apply a custom format to all the row.</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">	Xls</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">SetRowFormat</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, XF2);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">	// Merge cells</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">	Xls</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">MergeCells</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#098658;--shiki-dark:#B5CEA8">5</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">10</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">6</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">	// Note how this one merges with the previous range, creating a final range (5,1,15,6)</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">	Xls</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">MergeCells</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#098658;--shiki-dark:#B5CEA8">10</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">6</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">15</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">6</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">	// Make the page print in landscape or portrait mode</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">	Xls</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#001080;--shiki-dark:#9CDCFE">PrintLandscape</span><span style="color:#000000;--shiki-dark:#D4D4D4"> = </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">}</span></span>
<span class="line"></span>
<span class="line"></span></code></pre>


### UGettingStarted.h

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#008000;--shiki-dark:#6A9955">//---------------------------------------------------------------------------</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#ifndef</span><span style="color:#0000FF;--shiki-dark:#569CD6"> UGettingStartedH</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#define</span><span style="color:#0000FF;--shiki-dark:#569CD6"> UGettingStartedH</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">//---------------------------------------------------------------------------</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#include</span><span style="color:#A31515;--shiki-dark:#CE9178"> &#x3C;Classes.hpp></span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#include</span><span style="color:#A31515;--shiki-dark:#CE9178"> &#x3C;Controls.hpp></span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#include</span><span style="color:#A31515;--shiki-dark:#CE9178"> &#x3C;StdCtrls.hpp></span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#include</span><span style="color:#A31515;--shiki-dark:#CE9178"> &#x3C;Forms.hpp></span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#include</span><span style="color:#A31515;--shiki-dark:#CE9178"> &#x3C;Dialogs.hpp></span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#include</span><span style="color:#A31515;--shiki-dark:#CE9178"> &#x3C;FlexCel.VCLSupport.hpp></span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#include</span><span style="color:#A31515;--shiki-dark:#CE9178"> &#x3C;FlexCel.Core.hpp></span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#include</span><span style="color:#A31515;--shiki-dark:#CE9178"> &#x3C;FlexCel.XlsAdapter.hpp></span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">//---------------------------------------------------------------------------</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">class</span><span style="color:#267F99;--shiki-dark:#4EC9B0"> TFGettingStarted</span><span style="color:#000000;--shiki-dark:#D4D4D4"> : </span><span style="color:#0000FF;--shiki-dark:#569CD6">public</span><span style="color:#267F99;--shiki-dark:#4EC9B0"> TForm</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">{</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">__published:</span><span style="color:#008000;--shiki-dark:#6A9955">	// IDE-managed Components</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	TButton *btnCreateFile;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	TSaveDialog *SaveDialog;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	TMemo* Memo1;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">	void</span><span style="color:#0000FF;--shiki-dark:#569CD6"> __fastcall</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> btnCreateFileClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#267F99;--shiki-dark:#4EC9B0">TObject</span><span style="color:#0000FF;--shiki-dark:#569CD6"> *</span><span style="color:#001080;--shiki-dark:#9CDCFE">Sender</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">private:</span><span style="color:#008000;--shiki-dark:#6A9955">	// User declarations</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">	void</span><span style="color:#0000FF;--shiki-dark:#569CD6"> __fastcall</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> CreateFile</span><span style="color:#000000;--shiki-dark:#D4D4D4">();</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">	void</span><span style="color:#0000FF;--shiki-dark:#569CD6"> __fastcall</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ShowOpenDialog</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#267F99;--shiki-dark:#4EC9B0">TExcelFile</span><span style="color:#0000FF;--shiki-dark:#569CD6"> *</span><span style="color:#001080;--shiki-dark:#9CDCFE">Xls</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">	void</span><span style="color:#0000FF;--shiki-dark:#569CD6"> __fastcall</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> AddData</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#267F99;--shiki-dark:#4EC9B0">TExcelFile</span><span style="color:#0000FF;--shiki-dark:#569CD6"> *</span><span style="color:#001080;--shiki-dark:#9CDCFE">Xls</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">public:</span><span style="color:#008000;--shiki-dark:#6A9955">		// User declarations</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">	__fastcall</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFGettingStarted</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#267F99;--shiki-dark:#4EC9B0">TComponent</span><span style="color:#0000FF;--shiki-dark:#569CD6">*</span><span style="color:#001080;--shiki-dark:#9CDCFE"> Owner</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">};</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">//---------------------------------------------------------------------------</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">extern</span><span style="color:#000000;--shiki-dark:#D4D4D4"> PACKAGE TFGettingStarted *FGettingStarted;</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">//---------------------------------------------------------------------------</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#endif</span></span>
<span class="line"></span>
<span class="line"></span></code></pre>


