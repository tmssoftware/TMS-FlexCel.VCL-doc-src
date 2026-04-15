---
uid: Getting_Started_Reports-CPlusPlus
description: Getting_Started_Reports-CPlusPlus
---


# Getting started with Reports (C++)

> [!Note]
> This demo is available in your FlexCel installation at ***&lt;FlexCel Install Folder>*\\Demo\\Cpp\\Modules\\20\.Reports\\10\.Getting Started Reports** and also at [https:&#8203;//&#8203;github.&#8203;com/&#8203;tmssoftware/&#8203;TMS-&#8203;FlexCel.&#8203;VCL-&#8203;demos/&#8203;tree/&#8203;master/&#8203;Cpp/&#8203;Modules/&#8203;20.&#8203;Reports/&#8203;10.&#8203;Getting Started Reports](https://github\.com/tmssoftware/TMS\-FlexCel\.VCL\-demos/tree/master/Cpp/Modules/20\.Reports/10\.Getting%20Started%20Reports)


## Overview


A really simple demo on how to create an Excel report. No database is
used, only report variables.

## Concepts

- A template is an Excel file with tags that will be replaced by
  report variables or fields from a dataset. Tags are always on the
  form **\<\#tag\>** If a tag has parameters, it always has the form
  **\<\#tag(param1; param2\...)\>**. You can read the [FlexCel Reports Tag Reference.](~/guides/reports-tag-reference.md)
  for more information.

- To set the value for report variable, use
  [TFlexCelReport.SetValue](~/api/FlexCel.Report/TFlexCelReport/SetValue.md). You can set any kind of object from
  here, not just text. If you set it to a [TFormula](~/api/FlexCel.Core/TFormula/index.md) object, you
  will enter a formula.

- \<\#Tags\> will be replaced inside **Cells**, **Comments**, **Sheet
  names**, **Images**, **Hyperlinks**, **AutoShapes**, **Headers**
  and **Footers.** All of this is shown here. To see the
  headers and footers, you must do a print preview.

- There are 2 special datatypes you must be aware:

   1. **Dates:** Dates in Excel are just numbers, with a special cell
   format. To enter a date in Excel, make sure the cell has a date
   format.

   2. **Multiline Text**:To be able to show carriage return on a cell,
   it must have \"Wrap text\" enabled on its cell format.

- Hyperlinks are a special case for 2 reasons: 
   1. **You can\'t enter
   \<\#** into an hyperlink, as **\#** is a reserved keyword. So, tags in
   hyperlinks are on the form \"\*.TAG.\*\" (On older FlexCelVersions
   we would use \"\<.tag\>\". This will still work, but you can\'t
   enter this text into Excel 2003 or newer) 
  
   2. If you do not begin the
   hyperlink text with \"http://\" or \"https://" while
   creating the link in Excel, it will be created as local file. As
   this is not what you would normally want, all \"local file\"
   hyperlinks will be changed to URL hyperlinks **if the replaced
   text starts with \"http:\" or \"https:\"**. So do not create links like
   \"[www.tmssoftware.com](https://www.tmssoftware.com)\", make your
   hyperlinks \"<https://www.tmssoftware.com>\"

- To create an hyperlink to a cell in the same file using tags, start
  the definition of the hyperlink with a \"**\#**\", like
  \"\*.sheetvar.\*!\*.\#cellvar.\*\"

- There are special tags, like the \<\#If( condition, iftrue,
  iffalse)\> that might contain other tags inside. You can use any
  composition of tags on any of the places where they will be
  replaced.

- **Empty comments will be removed.** This is a feature so you can
  selectively comment cells based on the comment text. If comment
  text is blank, no comment will be made.

- To **replace images**, name them as \<\#tag\>. To see or change the
  name of an image, use the combo box at the upper left corner on
  Excel.

- You can use tags as usual on sheet names. But, as the maximum sheet
  name length is 32, it is kind of limited. You can use
  [Equal](~/guides/reports-tag-reference.md#equal) tag \(**\<\#=(cell)\>**\) to solve this limitation.

- You can **define reusable variables** on the config sheet. For
  example, here we define an expression containing the name and
  \"anonymous\" if the name is null, and we use it on the sheet name
  and the print header. Then we can use this expression on many
  places. \<\#=(cell)\> is conceptually the same as report
  expressions, but report expressions are normally cleaner on what
  they mean.

- Rich text will be preserved on cells. If for example you write
  \"\<\#name\> and \<\#date\>\", the result will be \"your name and
  thedate\"

## Files

### GettingStartedReports.cpp

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#008000;--shiki-dark:#6A9955">//---------------------------------------------------------------------------</span></span>
<span class="line"></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#include</span><span style="color:#A31515;--shiki-dark:#CE9178"> &#x3C;vcl.h></span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#pragma</span><span style="color:#E50000;--shiki-dark:#9CDCFE"> hdrstop</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#include</span><span style="color:#A31515;--shiki-dark:#CE9178"> &#x3C;tchar.h></span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">//---------------------------------------------------------------------------</span></span>
<span class="line"></span>
<span class="line"><span style="color:#795E26;--shiki-dark:#DCDCAA">USEFORM</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#A31515;--shiki-dark:#CE9178">"UMainForm.cpp"</span><span style="color:#000000;--shiki-dark:#D4D4D4">, MainForm);</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">//---------------------------------------------------------------------------</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">int</span><span style="color:#000000;--shiki-dark:#D4D4D4"> WINAPI </span><span style="color:#795E26;--shiki-dark:#DCDCAA">_tWinMain</span><span style="color:#000000;--shiki-dark:#D4D4D4">(HINSTANCE, HINSTANCE, LPTSTR, </span><span style="color:#0000FF;--shiki-dark:#569CD6">int</span><span style="color:#000000;--shiki-dark:#D4D4D4">)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">{</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">	try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	{</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">		Application</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">Initialize</span><span style="color:#000000;--shiki-dark:#D4D4D4">();</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">		Application</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#001080;--shiki-dark:#9CDCFE">MainFormOnTaskBar</span><span style="color:#000000;--shiki-dark:#D4D4D4"> = </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">	   	Application</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">CreateForm</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#795E26;--shiki-dark:#DCDCAA">__classid</span><span style="color:#000000;--shiki-dark:#D4D4D4">(TMainForm), &#x26;MainForm);</span></span>
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


### UMainForm.cpp

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#008000;--shiki-dark:#6A9955">//---------------------------------------------------------------------------</span></span>
<span class="line"></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#include</span><span style="color:#A31515;--shiki-dark:#CE9178"> &#x3C;vcl.h></span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#include</span><span style="color:#A31515;--shiki-dark:#CE9178"> &#x3C;IOUtils.hpp></span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#if</span><span style="color:#0000FF;--shiki-dark:#569CD6"> __CODEGEARC__ </span><span style="color:#000000;--shiki-dark:#D4D4D4">>=</span><span style="color:#098658;--shiki-dark:#B5CEA8"> 0x0700</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#include</span><span style="color:#A31515;--shiki-dark:#CE9178"> &#x3C;System.Threading.hpp></span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#endif</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#pragma</span><span style="color:#E50000;--shiki-dark:#9CDCFE"> hdrstop</span></span>
<span class="line"></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#include</span><span style="color:#A31515;--shiki-dark:#CE9178"> "UMainForm.h"</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">//---------------------------------------------------------------------------</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#pragma</span><span style="color:#E50000;--shiki-dark:#9CDCFE"> package</span><span style="color:#0000FF;--shiki-dark:#569CD6">(</span><span style="color:#E50000;--shiki-dark:#9CDCFE">smart_init</span><span style="color:#0000FF;--shiki-dark:#569CD6">)</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#pragma</span><span style="color:#E50000;--shiki-dark:#9CDCFE"> resource</span><span style="color:#A31515;--shiki-dark:#CE9178"> "*.dfm"</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">TMainForm *MainForm;</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">//---------------------------------------------------------------------------</span></span>
<span class="line"><span style="color:#267F99;--shiki-dark:#4EC9B0">__fastcall</span><span style="color:#267F99;--shiki-dark:#4EC9B0"> TMainForm</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">TMainForm</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#267F99;--shiki-dark:#4EC9B0">TComponent</span><span style="color:#0000FF;--shiki-dark:#569CD6">*</span><span style="color:#001080;--shiki-dark:#9CDCFE"> Owner</span><span style="color:#000000;--shiki-dark:#D4D4D4">)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	: </span><span style="color:#795E26;--shiki-dark:#DCDCAA">TForm</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Owner)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">{</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">}</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">//---------------------------------------------------------------------------</span></span>
<span class="line"></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">void</span><span style="color:#0000FF;--shiki-dark:#569CD6"> __fastcall</span><span style="color:#267F99;--shiki-dark:#4EC9B0"> TMainForm</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">btnCancelClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#267F99;--shiki-dark:#4EC9B0">TObject</span><span style="color:#0000FF;--shiki-dark:#569CD6"> *</span><span style="color:#001080;--shiki-dark:#9CDCFE">Sender</span><span style="color:#000000;--shiki-dark:#D4D4D4">)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">{</span></span>
<span class="line"><span style="color:#795E26;--shiki-dark:#DCDCAA">  Close</span><span style="color:#000000;--shiki-dark:#D4D4D4">();</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">}</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">//---------------------------------------------------------------------------</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">void</span><span style="color:#0000FF;--shiki-dark:#569CD6"> __fastcall</span><span style="color:#267F99;--shiki-dark:#4EC9B0"> TMainForm</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">btnGoClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#267F99;--shiki-dark:#4EC9B0">TObject</span><span style="color:#0000FF;--shiki-dark:#569CD6"> *</span><span style="color:#001080;--shiki-dark:#9CDCFE">Sender</span><span style="color:#000000;--shiki-dark:#D4D4D4">)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">{</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (</span><span style="color:#001080;--shiki-dark:#9CDCFE">cbAutoOpen</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#001080;--shiki-dark:#9CDCFE">Checked</span><span style="color:#000000;--shiki-dark:#D4D4D4">) </span><span style="color:#795E26;--shiki-dark:#DCDCAA">AutoOpenRun</span><span style="color:#000000;--shiki-dark:#D4D4D4">(); </span><span style="color:#AF00DB;--shiki-dark:#C586C0">else</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> NormalRun</span><span style="color:#000000;--shiki-dark:#D4D4D4">();</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">}</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">//---------------------------------------------------------------------------</span></span>
<span class="line"></span>
<span class="line"><span style="color:#267F99;--shiki-dark:#4EC9B0">String</span><span style="color:#0000FF;--shiki-dark:#569CD6"> __fastcall</span><span style="color:#267F99;--shiki-dark:#4EC9B0"> TMainForm</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">GetDataPath</span><span style="color:#000000;--shiki-dark:#D4D4D4">()</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">{</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">	return</span><span style="color:#267F99;--shiki-dark:#4EC9B0"> TPath</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">Combine</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#267F99;--shiki-dark:#4EC9B0">TPath</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">GetDirectoryName</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#795E26;--shiki-dark:#DCDCAA">ParamStr</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">)), </span><span style="color:#A31515;--shiki-dark:#CE9178">"..</span><span style="color:#EE0000;--shiki-dark:#D7BA7D">\\</span><span style="color:#A31515;--shiki-dark:#CE9178">.."</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">}</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">//---------------------------------------------------------------------------</span></span>
<span class="line"></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">void</span><span style="color:#0000FF;--shiki-dark:#569CD6"> __fastcall</span><span style="color:#267F99;--shiki-dark:#4EC9B0"> TMainForm</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">Setup</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#267F99;--shiki-dark:#4EC9B0">TFlexCelReport</span><span style="color:#0000FF;--shiki-dark:#569CD6">*</span><span style="color:#001080;--shiki-dark:#9CDCFE"> ReportStart</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#267F99;--shiki-dark:#4EC9B0">String</span><span style="color:#001080;--shiki-dark:#9CDCFE"> UserName</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#267F99;--shiki-dark:#4EC9B0">String</span><span style="color:#001080;--shiki-dark:#9CDCFE"> UserUrl</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#267F99;--shiki-dark:#4EC9B0">String</span><span style="color:#001080;--shiki-dark:#9CDCFE"> DataPath</span><span style="color:#000000;--shiki-dark:#D4D4D4">)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">{</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //Set report variables, including an image.</span></span>
<span class="line"></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">  ReportStart</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">SetValue</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#A31515;--shiki-dark:#CE9178">"Date"</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#267F99;--shiki-dark:#4EC9B0">TReportValue</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">Create</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#267F99;--shiki-dark:#4EC9B0">TCellValue</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">Create</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#795E26;--shiki-dark:#DCDCAA">Now</span><span style="color:#000000;--shiki-dark:#D4D4D4">())));</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">  ReportStart</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">SetValue</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#A31515;--shiki-dark:#CE9178">"Name"</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#267F99;--shiki-dark:#4EC9B0">TReportValue</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">Create</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#267F99;--shiki-dark:#4EC9B0">TCellValue</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">Create</span><span style="color:#000000;--shiki-dark:#D4D4D4">(UserName)));</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">  ReportStart</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">SetValue</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#A31515;--shiki-dark:#CE9178">"TwoLines"</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#267F99;--shiki-dark:#4EC9B0">TReportValue</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">Create</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#267F99;--shiki-dark:#4EC9B0">TCellValue</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">Create</span><span style="color:#000000;--shiki-dark:#D4D4D4">((String)</span><span style="color:#A31515;--shiki-dark:#CE9178">L"First line</span><span style="color:#EE0000;--shiki-dark:#D7BA7D">\r\n</span><span style="color:#A31515;--shiki-dark:#CE9178">Second Line"</span><span style="color:#000000;--shiki-dark:#D4D4D4">)));</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">  ReportStart</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">SetValue</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#A31515;--shiki-dark:#CE9178">"Empty"</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#267F99;--shiki-dark:#4EC9B0">TReportValue</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">Empty</span><span style="color:#000000;--shiki-dark:#D4D4D4">());</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">  ReportStart</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">SetValue</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#A31515;--shiki-dark:#CE9178">"LinkPage"</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#267F99;--shiki-dark:#4EC9B0">TReportValue</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">Create</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#267F99;--shiki-dark:#4EC9B0">TCellValue</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">Create</span><span style="color:#000000;--shiki-dark:#D4D4D4">(UserUrl)));</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //C++ builder defines assignment to TReportValue, but not creation. So we need to do this in 2 lines:</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //TReportValue ImgData = SomeBytes; wouldn't work.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TReportValue ImgData;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ImgData = </span><span style="color:#267F99;--shiki-dark:#4EC9B0">TReportValue</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">_op_Implicit</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#267F99;--shiki-dark:#4EC9B0">TFile</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">ReadAllBytes</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#267F99;--shiki-dark:#4EC9B0">TPath</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">Combine</span><span style="color:#000000;--shiki-dark:#D4D4D4">(DataPath, </span><span style="color:#A31515;--shiki-dark:#CE9178">"img.png"</span><span style="color:#000000;--shiki-dark:#D4D4D4">)));</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">  ReportStart</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">SetValue</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#A31515;--shiki-dark:#CE9178">"Img"</span><span style="color:#000000;--shiki-dark:#D4D4D4">, ImgData);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">}</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">//---------------------------------------------------------------------------</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">void</span><span style="color:#0000FF;--shiki-dark:#569CD6"> __fastcall</span><span style="color:#267F99;--shiki-dark:#4EC9B0"> TMainForm</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">NormalRun</span><span style="color:#000000;--shiki-dark:#D4D4D4">()</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">{</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0"> if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (!</span><span style="color:#001080;--shiki-dark:#9CDCFE">SaveDialog</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">Execute</span><span style="color:#000000;--shiki-dark:#D4D4D4">()) </span><span style="color:#AF00DB;--shiki-dark:#C586C0">return</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TFlexCelReport* Report = </span><span style="color:#AF00DB;--shiki-dark:#C586C0">new</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFlexCelReport</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  __try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  {</span></span>
<span class="line"><span style="color:#795E26;--shiki-dark:#DCDCAA">	Setup</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Report, </span><span style="color:#001080;--shiki-dark:#9CDCFE">edName</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#001080;--shiki-dark:#9CDCFE">Text</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#001080;--shiki-dark:#9CDCFE">edURL</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#001080;--shiki-dark:#9CDCFE">Text</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#795E26;--shiki-dark:#DCDCAA">GetDataPath</span><span style="color:#000000;--shiki-dark:#D4D4D4">());</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    //FlexCel doesn't do a 100% accurate conversion between xls and xlsx, it isn't designed for that</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">	//So to create an xls file is it best to use an xls template, and for xlsx and xlsx template.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    String FileExt;</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">	if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (</span><span style="color:#267F99;--shiki-dark:#4EC9B0">TPath</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">GetExtension</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#001080;--shiki-dark:#9CDCFE">SaveDialog</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#001080;--shiki-dark:#9CDCFE">FileName</span><span style="color:#000000;--shiki-dark:#D4D4D4">) == </span><span style="color:#A31515;--shiki-dark:#CE9178">".xlsx"</span><span style="color:#000000;--shiki-dark:#D4D4D4">) FileExt = </span><span style="color:#A31515;--shiki-dark:#CE9178">".xlsx"</span><span style="color:#000000;--shiki-dark:#D4D4D4">; </span><span style="color:#AF00DB;--shiki-dark:#C586C0">else</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FileExt = </span><span style="color:#A31515;--shiki-dark:#CE9178">".xls"</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">	Report</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">Run</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span></span>
<span class="line"><span style="color:#267F99;--shiki-dark:#4EC9B0">	  TPath</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">Combine</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#795E26;--shiki-dark:#DCDCAA">GetDataPath</span><span style="color:#000000;--shiki-dark:#D4D4D4">(), </span><span style="color:#A31515;--shiki-dark:#CE9178">"Getting Started Reports.template"</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + FileExt),</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">	  SaveDialog</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#001080;--shiki-dark:#9CDCFE">FileName</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  }</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  __finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  {</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">	Report</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">Free</span><span style="color:#000000;--shiki-dark:#D4D4D4">();</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  }</span></span>
<span class="line"></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (</span><span style="color:#795E26;--shiki-dark:#DCDCAA">MessageDlg</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#A31515;--shiki-dark:#CE9178">L"Do you want to open the generated file?"</span><span style="color:#000000;--shiki-dark:#D4D4D4">, mtConfirmation,</span></span>
<span class="line"><span style="color:#795E26;--shiki-dark:#DCDCAA">	  TMsgDlgButtons</span><span style="color:#000000;--shiki-dark:#D4D4D4">() &#x3C;&#x3C; mbYes &#x3C;&#x3C; mbNo, </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">) == mrYes)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	  {</span></span>
<span class="line"><span style="color:#795E26;--shiki-dark:#DCDCAA">			ShellExecute</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">L"open"</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#001080;--shiki-dark:#9CDCFE">SaveDialog</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#001080;--shiki-dark:#9CDCFE">FileName</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span><span style="color:#795E26;--shiki-dark:#DCDCAA">c_str</span><span style="color:#000000;--shiki-dark:#D4D4D4">(), </span><span style="color:#0000FF;--shiki-dark:#569CD6">NULL</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">NULL</span><span style="color:#000000;--shiki-dark:#D4D4D4">,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">			SW_SHOWNORMAL);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	  }</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">}</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">//---------------------------------------------------------------------------</span></span>
<span class="line"></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> !</span><span style="color:#AF00DB;--shiki-dark:#C586C0">defined</span><span style="color:#0000FF;--shiki-dark:#569CD6">(__clang__) </span><span style="color:#000000;--shiki-dark:#D4D4D4">||</span><span style="color:#0000FF;--shiki-dark:#569CD6"> __CODEGEARC__ </span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;</span><span style="color:#098658;--shiki-dark:#B5CEA8"> 0x0700</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">class</span><span style="color:#267F99;--shiki-dark:#4EC9B0"> TDeleteFileTask</span><span style="color:#000000;--shiki-dark:#D4D4D4"> : </span><span style="color:#0000FF;--shiki-dark:#569CD6">public</span><span style="color:#267F99;--shiki-dark:#4EC9B0"> TCppInterfacedObject</span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;</span><span style="color:#267F99;--shiki-dark:#4EC9B0">TProc</span><span style="color:#000000;--shiki-dark:#D4D4D4">> {</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">public:</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  String FileName;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#795E26;--shiki-dark:#DCDCAA">   TDeleteFileTask</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#267F99;--shiki-dark:#4EC9B0">String</span><span style="color:#001080;--shiki-dark:#9CDCFE"> aFileName</span><span style="color:#000000;--shiki-dark:#D4D4D4">)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">   {</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">		  FileName = aFileName;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">   }</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">	void</span><span style="color:#0000FF;--shiki-dark:#569CD6"> __fastcall</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Invoke</span><span style="color:#000000;--shiki-dark:#D4D4D4">() {</span></span>
<span class="line"><span style="color:#267F99;--shiki-dark:#4EC9B0">		 TThread</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">Sleep</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#098658;--shiki-dark:#B5CEA8">30000</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span><span style="color:#008000;--shiki-dark:#6A9955"> //wait for 30 secs to give Excel time to start.</span></span>
<span class="line"><span style="color:#267F99;--shiki-dark:#4EC9B0">		 TFile</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">Delete</span><span style="color:#000000;--shiki-dark:#D4D4D4">(FileName);</span><span style="color:#008000;--shiki-dark:#6A9955">  //As it is an xltx file, we can delete it even when it is open on Excel.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    }</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">};</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#endif</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">void</span><span style="color:#0000FF;--shiki-dark:#569CD6"> __fastcall</span><span style="color:#267F99;--shiki-dark:#4EC9B0"> TMainForm</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">AutoOpenRun</span><span style="color:#000000;--shiki-dark:#D4D4D4">()</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">{</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TFlexCelReport* Report = </span><span style="color:#AF00DB;--shiki-dark:#C586C0">new</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFlexCelReport</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  __try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  {</span></span>
<span class="line"><span style="color:#795E26;--shiki-dark:#DCDCAA">	Setup</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Report, </span><span style="color:#001080;--shiki-dark:#9CDCFE">edName</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#001080;--shiki-dark:#9CDCFE">Text</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#001080;--shiki-dark:#9CDCFE">edURL</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#001080;--shiki-dark:#9CDCFE">Text</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#795E26;--shiki-dark:#DCDCAA">GetDataPath</span><span style="color:#000000;--shiki-dark:#D4D4D4">());</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	String FilePath = </span><span style="color:#267F99;--shiki-dark:#4EC9B0">TPath</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">GetTempPath</span><span style="color:#000000;--shiki-dark:#D4D4D4">();</span><span style="color:#008000;--shiki-dark:#6A9955">  //GetTempFileName does not allow us to specify the "xltx" extension.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	GUID g;</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">	if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (</span><span style="color:#795E26;--shiki-dark:#DCDCAA">CreateGUID</span><span style="color:#000000;--shiki-dark:#D4D4D4">(g) != </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	{</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">		throw</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> new</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Exception</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#A31515;--shiki-dark:#CE9178">"Can't create GUID"</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    }</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	String FileName = </span><span style="color:#267F99;--shiki-dark:#4EC9B0">TPath</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">Combine</span><span style="color:#000000;--shiki-dark:#D4D4D4">(FilePath, </span><span style="color:#795E26;--shiki-dark:#DCDCAA">GUIDToString</span><span style="color:#000000;--shiki-dark:#D4D4D4">(g) + </span><span style="color:#A31515;--shiki-dark:#CE9178">".xltx"</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span><span style="color:#008000;--shiki-dark:#6A9955">  //xltx is the extension for excel templates.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	__try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	{</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">	  Report</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">Run</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span></span>
<span class="line"><span style="color:#267F99;--shiki-dark:#4EC9B0">		TPath</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">Combine</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#795E26;--shiki-dark:#DCDCAA">GetDataPath</span><span style="color:#000000;--shiki-dark:#D4D4D4">(), </span><span style="color:#A31515;--shiki-dark:#CE9178">"Getting Started Reports.template.xlsx"</span><span style="color:#000000;--shiki-dark:#D4D4D4">), FileName);</span></span>
<span class="line"><span style="color:#795E26;--shiki-dark:#DCDCAA">		ShellExecute</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">L""</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#001080;--shiki-dark:#9CDCFE">FileName</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span><span style="color:#795E26;--shiki-dark:#DCDCAA">c_str</span><span style="color:#000000;--shiki-dark:#D4D4D4">(), </span><span style="color:#0000FF;--shiki-dark:#569CD6">NULL</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">NULL</span><span style="color:#000000;--shiki-dark:#D4D4D4">,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">			SW_SHOWNORMAL);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	}</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	 __finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	 {</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">       //See https://doc.tmssoftware.com/flexcel/vcl/tips/automatically-open-generated-excel-files.html</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">//C++ builder before XE7 doesn't have a working "Parallel Programming Library" TTask and in XE7 it is buggy.</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">//So we use TThread directly for older C++ builder versions.</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#if</span><span style="color:#0000FF;--shiki-dark:#569CD6"> __CODEGEARC__ </span><span style="color:#000000;--shiki-dark:#D4D4D4">&#x3C;</span><span style="color:#098658;--shiki-dark:#B5CEA8"> 0x0700</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">	   //Classic compiler doesn't support lambdas.</span></span>
<span class="line"><span style="color:#267F99;--shiki-dark:#4EC9B0">	   TThread</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">CreateAnonymousThread</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#795E26;--shiki-dark:#DCDCAA">_di_TProc</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#AF00DB;--shiki-dark:#C586C0">new</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TDeleteFileTask</span><span style="color:#000000;--shiki-dark:#D4D4D4">(FileName)))-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">Start</span><span style="color:#000000;--shiki-dark:#D4D4D4">();</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#else</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">	#ifdef</span><span style="color:#0000FF;--shiki-dark:#569CD6"> __clang__</span></span>
<span class="line"><span style="color:#267F99;--shiki-dark:#4EC9B0">		   TTask</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">Run</span><span style="color:#000000;--shiki-dark:#D4D4D4">([&#x26;]() {</span></span>
<span class="line"><span style="color:#267F99;--shiki-dark:#4EC9B0">			 TThread</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">Sleep</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#098658;--shiki-dark:#B5CEA8">30000</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span><span style="color:#008000;--shiki-dark:#6A9955"> //wait for 30 secs to give Excel time to start.</span></span>
<span class="line"><span style="color:#267F99;--shiki-dark:#4EC9B0">			 TFile</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">Delete</span><span style="color:#000000;--shiki-dark:#D4D4D4">(FileName);</span><span style="color:#008000;--shiki-dark:#6A9955">  //As it is an xltx file, we can delete it even when it is open on Excel.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">			 });</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">	#else</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">	   //Classic compiler doesn't support lambdas.</span></span>
<span class="line"><span style="color:#267F99;--shiki-dark:#4EC9B0">		   TTask</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">Run</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#795E26;--shiki-dark:#DCDCAA">_di_TProc</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#AF00DB;--shiki-dark:#C586C0">new</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TDeleteFileTask</span><span style="color:#000000;--shiki-dark:#D4D4D4">(FileName)));</span></span>
<span class="line"></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">	#endif</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#endif</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	 }</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  }</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  __finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  {</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">	Report</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">Free</span><span style="color:#000000;--shiki-dark:#D4D4D4">();</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  }</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">}</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">//---------------------------------------------------------------------------</span></span>
<span class="line"></span>
<span class="line"></span>
<span class="line"></span></code></pre>


### UMainForm.h

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#008000;--shiki-dark:#6A9955">//---------------------------------------------------------------------------</span></span>
<span class="line"></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#ifndef</span><span style="color:#0000FF;--shiki-dark:#569CD6"> UMainFormH</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#define</span><span style="color:#0000FF;--shiki-dark:#569CD6"> UMainFormH</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">//---------------------------------------------------------------------------</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#include</span><span style="color:#A31515;--shiki-dark:#CE9178"> &#x3C;Classes.hpp></span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#include</span><span style="color:#A31515;--shiki-dark:#CE9178"> &#x3C;Controls.hpp></span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#include</span><span style="color:#A31515;--shiki-dark:#CE9178"> &#x3C;StdCtrls.hpp></span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#include</span><span style="color:#A31515;--shiki-dark:#CE9178"> &#x3C;Forms.hpp></span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#include</span><span style="color:#A31515;--shiki-dark:#CE9178"> &#x3C;Dialogs.hpp></span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#include</span><span style="color:#A31515;--shiki-dark:#CE9178"> &#x3C;Vcl.ExtCtrls.hpp></span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#include</span><span style="color:#A31515;--shiki-dark:#CE9178"> &#x3C;FlexCel.VCLSupport.hpp></span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#include</span><span style="color:#A31515;--shiki-dark:#CE9178"> &#x3C;FlexCel.Core.hpp></span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#include</span><span style="color:#A31515;--shiki-dark:#CE9178"> &#x3C;FlexCel.XlsAdapter.hpp></span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#include</span><span style="color:#A31515;--shiki-dark:#CE9178"> &#x3C;FlexCel.Report.hpp></span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">//---------------------------------------------------------------------------</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">class</span><span style="color:#267F99;--shiki-dark:#4EC9B0"> TMainForm</span><span style="color:#000000;--shiki-dark:#D4D4D4"> : </span><span style="color:#0000FF;--shiki-dark:#569CD6">public</span><span style="color:#267F99;--shiki-dark:#4EC9B0"> TForm</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">{</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">__published:</span><span style="color:#008000;--shiki-dark:#6A9955">	// IDE-managed Components</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	TLabeledEdit *edName;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	TLabeledEdit *edURL;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	TCheckBox *cbAutoOpen;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	TButton *btnCancel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	TButton *btnGo;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	TSaveDialog *SaveDialog;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">	void</span><span style="color:#0000FF;--shiki-dark:#569CD6"> __fastcall</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> btnCancelClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#267F99;--shiki-dark:#4EC9B0">TObject</span><span style="color:#0000FF;--shiki-dark:#569CD6"> *</span><span style="color:#001080;--shiki-dark:#9CDCFE">Sender</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">	void</span><span style="color:#0000FF;--shiki-dark:#569CD6"> __fastcall</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> btnGoClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#267F99;--shiki-dark:#4EC9B0">TObject</span><span style="color:#0000FF;--shiki-dark:#569CD6"> *</span><span style="color:#001080;--shiki-dark:#9CDCFE">Sender</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">private:</span><span style="color:#008000;--shiki-dark:#6A9955">	// User declarations</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">	void</span><span style="color:#0000FF;--shiki-dark:#569CD6"> __fastcall</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> AutoOpenRun</span><span style="color:#000000;--shiki-dark:#D4D4D4">();</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">	void</span><span style="color:#0000FF;--shiki-dark:#569CD6"> __fastcall</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> NormalRun</span><span style="color:#000000;--shiki-dark:#D4D4D4">();</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">	void</span><span style="color:#0000FF;--shiki-dark:#569CD6"> __fastcall</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Setup</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#267F99;--shiki-dark:#4EC9B0">TFlexCelReport</span><span style="color:#0000FF;--shiki-dark:#569CD6">*</span><span style="color:#001080;--shiki-dark:#9CDCFE"> ReportStart</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#267F99;--shiki-dark:#4EC9B0">String</span><span style="color:#001080;--shiki-dark:#9CDCFE"> UserName</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#267F99;--shiki-dark:#4EC9B0">String</span><span style="color:#001080;--shiki-dark:#9CDCFE"> UserUrl</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#267F99;--shiki-dark:#4EC9B0">String</span><span style="color:#001080;--shiki-dark:#9CDCFE"> DataPath</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#267F99;--shiki-dark:#4EC9B0">	String</span><span style="color:#0000FF;--shiki-dark:#569CD6"> __fastcall</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> GetDataPath</span><span style="color:#000000;--shiki-dark:#D4D4D4">();</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">public:</span><span style="color:#008000;--shiki-dark:#6A9955">		// User declarations</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">	__fastcall</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TMainForm</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#267F99;--shiki-dark:#4EC9B0">TComponent</span><span style="color:#0000FF;--shiki-dark:#569CD6">*</span><span style="color:#001080;--shiki-dark:#9CDCFE"> Owner</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">};</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">//---------------------------------------------------------------------------</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">extern</span><span style="color:#000000;--shiki-dark:#D4D4D4"> PACKAGE TMainForm *MainForm;</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">//---------------------------------------------------------------------------</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#endif</span></span>
<span class="line"></span>
<span class="line"></span></code></pre>


