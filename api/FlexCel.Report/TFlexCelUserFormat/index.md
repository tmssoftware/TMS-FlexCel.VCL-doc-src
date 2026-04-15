---
uid: TFlexCelUserFormat
description: TFlexCelUserFormat
---

# TFlexCelUserFormat Class

A class used to define a cell format in code, that you can call from a report\.


## Remarks

To Create a User format:
1. Create a new class derived from TFlexCelUserFormat\.
2. Override the method [Evaluate](Evaluate.md)\.
3. Add the new user format to the report using [TFlexCelReport.SetUserFormat](../TFlexCelReport/SetUserFormat.md)\.



## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">TFlexCelUserFormat = class(TFlexCelObject);</code></pre>

## Methods

|Name|Description|
|---|---|
|[Evaluate](Evaluate.md)|Override this method on a derived class to implement your own defined function\.<br />|


## Examples

To define a user format that will format the cell according to the first parameter you pass to the function, you would: 1\) Define the class:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TMyUserFormat = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (TFlexCelUserFormat)</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  public</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    constructor</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Create</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Evaluate</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> workbook: TExcelFile; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> range: TXlsCellRange; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> parameters: TFormulaValueArray): TFlxPartialFormat; </span><span style="color:#0000FF;--shiki-dark:#569CD6">override</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">...</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TMyUserFormat.Evaluate</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> workbook: TExcelFile; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> range: TXlsCellRange; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> parameters: TFormulaValueArray): TFlxPartialFormat;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  color: </span><span style="color:#0000FF;--shiki-dark:#569CD6">double</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Format: TFlxFormat;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Apply: TFlxApplyFormat;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Length(parameters) &#x3C;> </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    raise</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Exception.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Invalid number of parameters for user defined format "MyUserFormat"'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  </span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#0000FF;--shiki-dark:#569CD6"> not</span><span style="color:#000000;--shiki-dark:#D4D4D4"> parameters[</span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">].TryToDouble(color, </span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    raise</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Exception.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'The parameter for TMyUserFormat must be a number.'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Format := workbook.GetDefaultFormat;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Format.FillPattern.FgColor := TExcelColor.FromArgb(Round(color));</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Format.FillPattern.BgColor := TExcelColor.Automatic;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Format.FillPattern.Pattern := TFlxPatternStyle.Solid;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Apply := TFlxApplyFormat.Create;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Apply.FillPattern.SetAllMembers(</span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := TFlxPartialFormat.Create(Format, Apply, </span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"></span></code></pre>

2\) Add the function to the report\.


<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  myFormatImpl := TMyUserFormat.Create;  </span><span style="color:#008000;--shiki-dark:#6A9955">//The MyUserFormat class implements an user defined format.</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //Note that we don't have to free myFormatImpl, it will be freed by the report once it is over.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  flexCelReport.SetUserFormat(</span><span style="color:#A31515;--shiki-dark:#CE9178">'MFMT'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, myFormatImpl);  </span><span style="color:#008000;--shiki-dark:#6A9955">//The name used in Excel will be =MFMT().</span></span>
<span class="line"></span></code></pre>

3\) Now, you can write "\<\#format cell\(MFMT;255\)>" on a cell in the template, and it will painted blue\.


