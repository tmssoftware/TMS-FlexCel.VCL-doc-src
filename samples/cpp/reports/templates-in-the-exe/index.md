---
uid: Templates_In_The_Exe-CPlusPlus
description: Templates_In_The_Exe-CPlusPlus
---


# Templates in the executable (C++)

> [!Note]
> This demo is available in your FlexCel installation at ***&lt;FlexCel Install Folder>*\\Demo\\Cpp\\Modules\\20\.Reports\\60\.Templates In The Exe** and also at [https:&#8203;//&#8203;github.&#8203;com/&#8203;tmssoftware/&#8203;TMS-&#8203;FlexCel.&#8203;VCL-&#8203;demos/&#8203;tree/&#8203;master/&#8203;Cpp/&#8203;Modules/&#8203;20.&#8203;Reports/&#8203;60.&#8203;Templates In The Exe](https://github\.com/tmssoftware/TMS\-FlexCel\.VCL\-demos/tree/master/Cpp/Modules/20\.Reports/60\.Templates%20In%20The%20Exe)


## Overview


Sometimes you might want to distribute your templates embedded in your application,
instead of shipping the separately.

## Concepts

- How to embed a template directly in the exe file. For
  step-by-step instructions please read [Embedding Excel files in your application](~/tips/embedding-excel-files-in-your-application.md) 


- Dealing with **includes**. Included files are normally searched on
  the same path as the original file, but here, as we are reading
  from a stream, we must tell FlexCel where to find the embedded
  template. This is done with the [TFlexCelReport.GetInclude](~/api/FlexCel.Report/TFlexCelReport/GetInclude.md) event.

- While here we show how to use a stream to read a template from the
  executable, you can use a very similar approach to store your
  templates in a database, or in any place you like. Just call the
  [TFlexCelReport.Run](~/api/FlexCel.Report/TFlexCelReport/Run.md) with a stream with your data, and
  assign the [TFlexCelReport.GetInclude](~/api/FlexCel.Report/TFlexCelReport/GetInclude.md) event to assign the data for the included
  files.

## Files

### UMainForm.pas

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">unit</span><span style="color:#000000;--shiki-dark:#D4D4D4"> UMainForm;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">interface</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">uses</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Windows, Messages, SysUtils, Variants, Classes, Graphics,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FlexCel.VCLSupport, FlexCel.Core, FlexCel.XlsAdapter, FlexCel.Report, FlexCel.Render,</span></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">  {$if CompilerVersion >= 23.0}</span><span style="color:#000000;--shiki-dark:#D4D4D4"> System.UITypes, </span><span style="color:#811F3F;--shiki-dark:#D16969">{$IFEND}</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ShellApi,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Controls, Forms, Dialogs, StdCtrls, ExtCtrls;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">type</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TMainForm = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span><span style="color:#000000;--shiki-dark:#D4D4D4">(TForm)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    btnCancel: TButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    btnGo: TButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    SaveDialog: TSaveDialog;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Label1: TLabel;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> btnCancelClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> btnGoClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  private</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> RunReport</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> GetIncludes</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> sender: TObject;</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> e: TGetIncludeEventArgs);</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    { Private declarations }</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  public</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    { Public declarations }</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  MainForm: TMainForm;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">implementation</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">uses</span><span style="color:#000000;--shiki-dark:#D4D4D4"> IOUtils, DemoData;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">{$R *.dfm}</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TMainForm.btnCancelClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Close;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TMainForm.btnGoClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  RunReport;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TMainForm.GetIncludes</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> sender: TObject; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> e: TGetIncludeEventArgs);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  IncReport: TResourceStream;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  b: TBytes;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  IncReport := TResourceStream.Create(hinstance, TPath.GetFileNameWithoutExtension(e.FileName), RT_RCDATA);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    SetLength(b, IncReport.Size);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (Length(b) > </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#000000;--shiki-dark:#D4D4D4"> IncReport.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Read</span><span style="color:#000000;--shiki-dark:#D4D4D4">(b[</span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">], Length(b));</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    e.IncludeData := b;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    IncReport.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TMainForm.RunReport</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Report: TFlexCelReport;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TemplateStream: TResourceStream;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  OutputStream: TFileStream;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#0000FF;--shiki-dark:#569CD6"> not</span><span style="color:#000000;--shiki-dark:#D4D4D4"> SaveDialog.Execute </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Report := TFlexCelReport.Create(</span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Report.GetInclude := GetIncludes; </span><span style="color:#008000;--shiki-dark:#6A9955">//this is only needed if you have includes.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Report.AddTable(DemoTables);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Report.SetValue(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Date'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, Now);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    TemplateStream := TResourceStream.Create(hinstance, </span><span style="color:#A31515;--shiki-dark:#CE9178">'TemplatesInTheExe'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, RT_RCDATA);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      OutputStream := TFileStream.Create(SaveDialog.FileName, fmCreate);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        Report.Run(TemplateStream, OutputStream);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        OutputStream.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      TemplateStream.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Report.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> MessageDlg(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Do you want to open the generated file?'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, mtConfirmation, [mbYes, mbNo], </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">) = mrYes </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ShellExecute(</span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'open'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">PCHAR</span><span style="color:#000000;--shiki-dark:#D4D4D4">(SaveDialog.FileName), </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">, SW_SHOWNORMAL);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span></span>
<span class="line"></span>
<span class="line"></span></code></pre>


### TemplatesInTheExe.cpp

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#008000;--shiki-dark:#6A9955">//---------------------------------------------------------------------------</span></span>
<span class="line"></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#include</span><span style="color:#A31515;--shiki-dark:#CE9178"> &#x3C;vcl.h></span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#pragma</span><span style="color:#E50000;--shiki-dark:#9CDCFE"> hdrstop</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#include</span><span style="color:#A31515;--shiki-dark:#CE9178"> &#x3C;tchar.h></span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">//---------------------------------------------------------------------------</span></span>
<span class="line"><span style="color:#795E26;--shiki-dark:#DCDCAA">USEFORM</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#A31515;--shiki-dark:#CE9178">"UMainForm.cpp"</span><span style="color:#000000;--shiki-dark:#D4D4D4">, MainForm);</span></span>
<span class="line"><span style="color:#795E26;--shiki-dark:#DCDCAA">USEFORM</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#A31515;--shiki-dark:#CE9178">"..</span><span style="color:#CD3131;--shiki-dark:#F44747">\S</span><span style="color:#A31515;--shiki-dark:#CE9178">haredData</span><span style="color:#CD3131;--shiki-dark:#F44747">\D</span><span style="color:#A31515;--shiki-dark:#CE9178">emoData.cpp"</span><span style="color:#000000;--shiki-dark:#D4D4D4">, DemoTables);</span><span style="color:#008000;--shiki-dark:#6A9955"> /* TDataModule: File Type */</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">//---------------------------------------------------------------------------</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">int</span><span style="color:#000000;--shiki-dark:#D4D4D4"> WINAPI </span><span style="color:#795E26;--shiki-dark:#DCDCAA">_tWinMain</span><span style="color:#000000;--shiki-dark:#D4D4D4">(HINSTANCE, HINSTANCE, LPTSTR, </span><span style="color:#0000FF;--shiki-dark:#569CD6">int</span><span style="color:#000000;--shiki-dark:#D4D4D4">)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">{</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">	try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	{</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">		Application</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">Initialize</span><span style="color:#000000;--shiki-dark:#D4D4D4">();</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">		Application</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#001080;--shiki-dark:#9CDCFE">MainFormOnTaskBar</span><span style="color:#000000;--shiki-dark:#D4D4D4"> = </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">		Application</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">CreateForm</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#795E26;--shiki-dark:#DCDCAA">__classid</span><span style="color:#000000;--shiki-dark:#D4D4D4">(TMainForm), &#x26;MainForm);</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">		Application</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">CreateForm</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#795E26;--shiki-dark:#DCDCAA">__classid</span><span style="color:#000000;--shiki-dark:#D4D4D4">(TDemoTables), &#x26;DemoTables);</span></span>
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
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#pragma</span><span style="color:#E50000;--shiki-dark:#9CDCFE"> hdrstop</span></span>
<span class="line"></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#include</span><span style="color:#A31515;--shiki-dark:#CE9178"> "UMainForm.h"</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#include</span><span style="color:#A31515;--shiki-dark:#CE9178"> &#x3C;IOUtils.hpp></span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">//---------------------------------------------------------------------------</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#pragma</span><span style="color:#E50000;--shiki-dark:#9CDCFE"> package</span><span style="color:#0000FF;--shiki-dark:#569CD6">(</span><span style="color:#E50000;--shiki-dark:#9CDCFE">smart_init</span><span style="color:#0000FF;--shiki-dark:#569CD6">)</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#pragma</span><span style="color:#E50000;--shiki-dark:#9CDCFE"> resource</span><span style="color:#A31515;--shiki-dark:#CE9178"> "*.dfm"</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">TMainForm *MainForm;</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">//---------------------------------------------------------------------------</span></span>
<span class="line"><span style="color:#267F99;--shiki-dark:#4EC9B0">__fastcall</span><span style="color:#267F99;--shiki-dark:#4EC9B0"> TMainForm</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">TMainForm</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#267F99;--shiki-dark:#4EC9B0">TComponent</span><span style="color:#0000FF;--shiki-dark:#569CD6">*</span><span style="color:#001080;--shiki-dark:#9CDCFE"> Owner</span><span style="color:#000000;--shiki-dark:#D4D4D4">)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	: </span><span style="color:#795E26;--shiki-dark:#DCDCAA">TForm</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Owner)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">{</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">}</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">//---------------------------------------------------------------------------</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">void</span><span style="color:#0000FF;--shiki-dark:#569CD6"> __fastcall</span><span style="color:#267F99;--shiki-dark:#4EC9B0"> TMainForm</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">btnCancelClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#267F99;--shiki-dark:#4EC9B0">TObject</span><span style="color:#0000FF;--shiki-dark:#569CD6"> *</span><span style="color:#001080;--shiki-dark:#9CDCFE">Sender</span><span style="color:#000000;--shiki-dark:#D4D4D4">)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">{</span></span>
<span class="line"><span style="color:#795E26;--shiki-dark:#DCDCAA">  Close</span><span style="color:#000000;--shiki-dark:#D4D4D4">();</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">}</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">//---------------------------------------------------------------------------</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">void</span><span style="color:#0000FF;--shiki-dark:#569CD6"> __fastcall</span><span style="color:#267F99;--shiki-dark:#4EC9B0"> TMainForm</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">btnGoClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#267F99;--shiki-dark:#4EC9B0">TObject</span><span style="color:#0000FF;--shiki-dark:#569CD6"> *</span><span style="color:#001080;--shiki-dark:#9CDCFE">Sender</span><span style="color:#000000;--shiki-dark:#D4D4D4">)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">{</span></span>
<span class="line"><span style="color:#795E26;--shiki-dark:#DCDCAA">  RunReport</span><span style="color:#000000;--shiki-dark:#D4D4D4">();</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">}</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">//---------------------------------------------------------------------------</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">void</span><span style="color:#0000FF;--shiki-dark:#569CD6"> __fastcall</span><span style="color:#267F99;--shiki-dark:#4EC9B0"> TMainForm</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">GetIncludes</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#267F99;--shiki-dark:#4EC9B0">TObject</span><span style="color:#0000FF;--shiki-dark:#569CD6">*</span><span style="color:#001080;--shiki-dark:#9CDCFE"> sender</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#267F99;--shiki-dark:#4EC9B0">TGetIncludeEventArgs</span><span style="color:#0000FF;--shiki-dark:#569CD6">*</span><span style="color:#001080;--shiki-dark:#9CDCFE"> e</span><span style="color:#000000;--shiki-dark:#D4D4D4">)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">{</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TResourceStream* IncReport = </span><span style="color:#AF00DB;--shiki-dark:#C586C0">new</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TResourceStream</span><span style="color:#000000;--shiki-dark:#D4D4D4">((THandle)HInstance, </span><span style="color:#267F99;--shiki-dark:#4EC9B0">TPath</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">GetFileNameWithoutExtension</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#001080;--shiki-dark:#9CDCFE">e</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#001080;--shiki-dark:#9CDCFE">FileName</span><span style="color:#000000;--shiki-dark:#D4D4D4">), RT_RCDATA);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  __try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  {</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	TBytes b;</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">	b</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span><span style="color:#001080;--shiki-dark:#9CDCFE">Length</span><span style="color:#000000;--shiki-dark:#D4D4D4"> = </span><span style="color:#001080;--shiki-dark:#9CDCFE">IncReport</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#001080;--shiki-dark:#9CDCFE">Size</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">	if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (</span><span style="color:#001080;--shiki-dark:#9CDCFE">b</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span><span style="color:#001080;--shiki-dark:#9CDCFE">Length</span><span style="color:#000000;--shiki-dark:#D4D4D4"> > </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">) </span><span style="color:#001080;--shiki-dark:#9CDCFE">IncReport</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">ReadBuffer</span><span style="color:#000000;--shiki-dark:#D4D4D4">(&#x26;(</span><span style="color:#001080;--shiki-dark:#9CDCFE">b</span><span style="color:#000000;--shiki-dark:#D4D4D4">[</span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">]), </span><span style="color:#001080;--shiki-dark:#9CDCFE">b</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span><span style="color:#001080;--shiki-dark:#9CDCFE">Length</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">	e</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#001080;--shiki-dark:#9CDCFE">IncludeData</span><span style="color:#000000;--shiki-dark:#D4D4D4"> = b;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  }</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  __finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  {</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">	IncReport</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">Free</span><span style="color:#000000;--shiki-dark:#D4D4D4">();</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  }</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">}</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">//---------------------------------------------------------------------------</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">void</span><span style="color:#0000FF;--shiki-dark:#569CD6"> __fastcall</span><span style="color:#267F99;--shiki-dark:#4EC9B0"> TMainForm</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">RunReport</span><span style="color:#000000;--shiki-dark:#D4D4D4">()</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">{</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (!</span><span style="color:#001080;--shiki-dark:#9CDCFE">SaveDialog</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">Execute</span><span style="color:#000000;--shiki-dark:#D4D4D4">()) </span><span style="color:#AF00DB;--shiki-dark:#C586C0">return</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TFlexCelReport* Report = </span><span style="color:#AF00DB;--shiki-dark:#C586C0">new</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFlexCelReport</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  __try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  {</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">	Report</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#001080;--shiki-dark:#9CDCFE">GetInclude</span><span style="color:#000000;--shiki-dark:#D4D4D4"> = GetIncludes;</span><span style="color:#008000;--shiki-dark:#6A9955"> //this is only needed if you have includes.</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">	Report</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">AddTable</span><span style="color:#000000;--shiki-dark:#D4D4D4">(DemoTables);</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">	Report</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">SetValue</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#A31515;--shiki-dark:#CE9178">"Date"</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#267F99;--shiki-dark:#4EC9B0">TReportValue</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">Create</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#267F99;--shiki-dark:#4EC9B0">TCellValue</span><span style="color:#000000;--shiki-dark:#D4D4D4">::</span><span style="color:#795E26;--shiki-dark:#DCDCAA">Create</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#795E26;--shiki-dark:#DCDCAA">Now</span><span style="color:#000000;--shiki-dark:#D4D4D4">())));</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	TResourceStream* TemplateStream = </span><span style="color:#AF00DB;--shiki-dark:#C586C0">new</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TResourceStream</span><span style="color:#000000;--shiki-dark:#D4D4D4">((THandle)HInstance, </span><span style="color:#A31515;--shiki-dark:#CE9178">"TemplatesInTheExe"</span><span style="color:#000000;--shiki-dark:#D4D4D4">, RT_RCDATA);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	__try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	{</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	  TStream* OutputStream = </span><span style="color:#AF00DB;--shiki-dark:#C586C0">new</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFileStream</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#001080;--shiki-dark:#9CDCFE">SaveDialog</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#001080;--shiki-dark:#9CDCFE">FileName</span><span style="color:#000000;--shiki-dark:#D4D4D4">, fmCreate);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	  __try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	  {</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">		Report</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">Run</span><span style="color:#000000;--shiki-dark:#D4D4D4">(TemplateStream, OutputStream);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	  }</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	  __finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	  {</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">		OutputStream</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">Free</span><span style="color:#000000;--shiki-dark:#D4D4D4">();</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	  }</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	}</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	__finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	{</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">	  TemplateStream</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">Free</span><span style="color:#000000;--shiki-dark:#D4D4D4">();</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	}</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  }</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  __finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  {</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">	Report</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#795E26;--shiki-dark:#DCDCAA">Free</span><span style="color:#000000;--shiki-dark:#D4D4D4">();</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  }</span></span>
<span class="line"></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0"> if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (</span><span style="color:#795E26;--shiki-dark:#DCDCAA">MessageDlg</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#A31515;--shiki-dark:#CE9178">L"Do you want to open the generated file?"</span><span style="color:#000000;--shiki-dark:#D4D4D4">, mtConfirmation,</span></span>
<span class="line"><span style="color:#795E26;--shiki-dark:#DCDCAA">	  TMsgDlgButtons</span><span style="color:#000000;--shiki-dark:#D4D4D4">() &#x3C;&#x3C; mbYes &#x3C;&#x3C; mbNo, </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">) == mrYes)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	  {</span></span>
<span class="line"><span style="color:#795E26;--shiki-dark:#DCDCAA">			ShellExecute</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">L"open"</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#001080;--shiki-dark:#9CDCFE">SaveDialog</span><span style="color:#000000;--shiki-dark:#D4D4D4">-></span><span style="color:#001080;--shiki-dark:#9CDCFE">FileName</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span><span style="color:#795E26;--shiki-dark:#DCDCAA">c_str</span><span style="color:#000000;--shiki-dark:#D4D4D4">(), </span><span style="color:#0000FF;--shiki-dark:#569CD6">NULL</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">NULL</span><span style="color:#000000;--shiki-dark:#D4D4D4">,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">			SW_SHOWNORMAL);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	  }</span></span>
<span class="line"></span>
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
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#include</span><span style="color:#A31515;--shiki-dark:#CE9178"> &#x3C;System.Classes.hpp></span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#include</span><span style="color:#A31515;--shiki-dark:#CE9178"> &#x3C;Vcl.Controls.hpp></span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#include</span><span style="color:#A31515;--shiki-dark:#CE9178"> &#x3C;Vcl.StdCtrls.hpp></span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#include</span><span style="color:#A31515;--shiki-dark:#CE9178"> &#x3C;Vcl.Forms.hpp></span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#include</span><span style="color:#A31515;--shiki-dark:#CE9178"> &#x3C;Vcl.Dialogs.hpp></span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#include</span><span style="color:#A31515;--shiki-dark:#CE9178"> "DemoData.h"</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#include</span><span style="color:#A31515;--shiki-dark:#CE9178"> &#x3C;FlexCel.VCLSupport.hpp></span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#include</span><span style="color:#A31515;--shiki-dark:#CE9178"> &#x3C;FlexCel.Core.hpp></span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#include</span><span style="color:#A31515;--shiki-dark:#CE9178"> &#x3C;FlexCel.XlsAdapter.hpp></span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#include</span><span style="color:#A31515;--shiki-dark:#CE9178"> &#x3C;FlexCel.Report.hpp></span></span>
<span class="line"></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">//---------------------------------------------------------------------------</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">class</span><span style="color:#267F99;--shiki-dark:#4EC9B0"> TMainForm</span><span style="color:#000000;--shiki-dark:#D4D4D4"> : </span><span style="color:#0000FF;--shiki-dark:#569CD6">public</span><span style="color:#267F99;--shiki-dark:#4EC9B0"> TForm</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">{</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">__published:</span><span style="color:#008000;--shiki-dark:#6A9955">	// IDE-managed Components</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	TLabel *Label1;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	TButton *btnCancel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	TButton *btnGo;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	TSaveDialog *SaveDialog;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">	void</span><span style="color:#0000FF;--shiki-dark:#569CD6"> __fastcall</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> btnCancelClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#267F99;--shiki-dark:#4EC9B0">TObject</span><span style="color:#0000FF;--shiki-dark:#569CD6"> *</span><span style="color:#001080;--shiki-dark:#9CDCFE">Sender</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">	void</span><span style="color:#0000FF;--shiki-dark:#569CD6"> __fastcall</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> btnGoClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#267F99;--shiki-dark:#4EC9B0">TObject</span><span style="color:#0000FF;--shiki-dark:#569CD6"> *</span><span style="color:#001080;--shiki-dark:#9CDCFE">Sender</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">private:</span><span style="color:#008000;--shiki-dark:#6A9955">	// User declarations</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">	void</span><span style="color:#0000FF;--shiki-dark:#569CD6"> __fastcall</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> RunReport</span><span style="color:#000000;--shiki-dark:#D4D4D4">();</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">	void</span><span style="color:#0000FF;--shiki-dark:#569CD6"> __fastcall</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> GetIncludes</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#267F99;--shiki-dark:#4EC9B0">TObject</span><span style="color:#0000FF;--shiki-dark:#569CD6">*</span><span style="color:#001080;--shiki-dark:#9CDCFE"> sender</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#267F99;--shiki-dark:#4EC9B0">TGetIncludeEventArgs</span><span style="color:#0000FF;--shiki-dark:#569CD6">*</span><span style="color:#001080;--shiki-dark:#9CDCFE"> e</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">public:</span><span style="color:#008000;--shiki-dark:#6A9955">		// User declarations</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">	__fastcall</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TMainForm</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#267F99;--shiki-dark:#4EC9B0">TComponent</span><span style="color:#0000FF;--shiki-dark:#569CD6">*</span><span style="color:#001080;--shiki-dark:#9CDCFE"> Owner</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">};</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">//---------------------------------------------------------------------------</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">extern</span><span style="color:#000000;--shiki-dark:#D4D4D4"> PACKAGE TMainForm *MainForm;</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">//---------------------------------------------------------------------------</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">#endif</span></span>
<span class="line"></span>
<span class="line"></span></code></pre>


