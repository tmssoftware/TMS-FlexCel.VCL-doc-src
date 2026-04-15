---
uid: Getting_Started_Reports-Delphi
description: Getting_Started_Reports-Delphi
---


# Getting started with Reports (Delphi)

> [!Note]
> This demo is available in your FlexCel installation at ***&lt;FlexCel Install Folder>*\\Demo\\Delphi\\Modules\\20\.Reports\\10\.Getting Started Reports** and also at [https:&#8203;//&#8203;github.&#8203;com/&#8203;tmssoftware/&#8203;TMS-&#8203;FlexCel.&#8203;VCL-&#8203;demos/&#8203;tree/&#8203;master/&#8203;Delphi/&#8203;Modules/&#8203;20.&#8203;Reports/&#8203;10.&#8203;Getting Started Reports](https://github\.com/tmssoftware/TMS\-FlexCel\.VCL\-demos/tree/master/Delphi/Modules/20\.Reports/10\.Getting%20Started%20Reports)


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

### UMainForm.pas

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">unit</span><span style="color:#000000;--shiki-dark:#D4D4D4"> UMainForm;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">interface</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">uses</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Windows, Messages, SysUtils, Variants, Classes, Graphics,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FlexCel.VCLSupport, FlexCel.Core, FlexCel.XlsAdapter, FlexCel.Report,</span></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">  {$if CompilerVersion >= 23.0}</span><span style="color:#000000;--shiki-dark:#D4D4D4"> System.UITypes, </span><span style="color:#811F3F;--shiki-dark:#D16969">{$IFEND}</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ShellApi,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Controls, Forms, Dialogs, StdCtrls, ExtCtrls;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">type</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TMainForm = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span><span style="color:#000000;--shiki-dark:#D4D4D4">(TForm)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    edName: TLabeledEdit;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    edURL: TLabeledEdit;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    cbAutoOpen: TCheckBox;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    btnCancel: TButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    btnGo: TButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    SaveDialog: TSaveDialog;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> btnCancelClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> btnGoClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  private</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Setup</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> ReportStart: TFlexCelReport; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> UserName, UserUrl,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      DataPath: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> AutoOpenRun</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> NormalRun</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> GetDataPath</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    { Private declarations }</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  public</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    { Public declarations }</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  MainForm: TMainForm;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">implementation</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">uses</span></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">  {$if CompilerVersion >= 28.0}</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Threading, </span><span style="color:#811F3F;--shiki-dark:#D16969">{$IFEND}</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4"> IOUtils;</span></span>
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
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> cbAutoOpen.Checked </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#000000;--shiki-dark:#D4D4D4"> AutoOpenRun </span><span style="color:#0000FF;--shiki-dark:#569CD6">else</span><span style="color:#000000;--shiki-dark:#D4D4D4"> NormalRun;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TMainForm.GetDataPath</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := TPath.Combine(TPath.GetDirectoryName(ParamStr(</span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">)), </span><span style="color:#A31515;--shiki-dark:#CE9178">'..\..'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TMainForm.Setup</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> ReportStart: TFlexCelReport; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> UserName: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> UserUrl: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> DataPath: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //Set report variables, including an image.</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ReportStart.SetValue(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Date'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, Now);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ReportStart.SetValue(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Name'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, UserName);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ReportStart.SetValue(</span><span style="color:#A31515;--shiki-dark:#CE9178">'TwoLines'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'First line'</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + </span><span style="color:#A31515;--shiki-dark:#CE9178">#13#10</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + </span><span style="color:#A31515;--shiki-dark:#CE9178">'Second Line'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ReportStart.SetValue(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Empty'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TReportValue.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Empty</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ReportStart.SetValue(</span><span style="color:#A31515;--shiki-dark:#CE9178">'LinkPage'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, UserUrl);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ReportStart.SetValue(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Img'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TFile.ReadAllBytes(TPath.Combine(DataPath, </span><span style="color:#A31515;--shiki-dark:#CE9178">'img.png'</span><span style="color:#000000;--shiki-dark:#D4D4D4">)));</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TMainForm.NormalRun</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Report: TFlexCelReport;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FileExt: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#0000FF;--shiki-dark:#569CD6"> not</span><span style="color:#000000;--shiki-dark:#D4D4D4"> SaveDialog.Execute </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Report := TFlexCelReport.Create(</span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Setup(Report, edName.Text, edURL.Text, GetDataPath);</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    //FlexCel doesn't do a 100% accurate conversion between xls and xlsx, it isn't designed for that</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    //So to create an xls file is it best to use an xls template, and for xlsx and xlsx template.</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> TPath.GetExtension(SaveDialog.FileName) = </span><span style="color:#A31515;--shiki-dark:#CE9178">'.xlsx'</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FileExt := </span><span style="color:#A31515;--shiki-dark:#CE9178">'.xlsx'</span><span style="color:#0000FF;--shiki-dark:#569CD6"> else</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FileExt := </span><span style="color:#A31515;--shiki-dark:#CE9178">'.xls'</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Report.Run(</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      TPath.Combine(GetDataPath, </span><span style="color:#A31515;--shiki-dark:#CE9178">'Getting Started Reports.template'</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + FileExt),</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      SaveDialog.FileName);</span></span>
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
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TMainForm.AutoOpenRun</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Report: TFlexCelReport;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FilePath, FileName: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Report := TFlexCelReport.Create(</span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Setup(Report, edName.Text, edURL.Text, GetDataPath);</span></span>
<span class="line"></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FilePath := TPath.GetTempPath();  </span><span style="color:#008000;--shiki-dark:#6A9955">//GetTempFileName does not allow us to specify the "xltx" extension.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FileName := TPath.Combine(FilePath, TGuid.NewGuid.ToString + </span><span style="color:#A31515;--shiki-dark:#CE9178">'.xltx'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);  </span><span style="color:#008000;--shiki-dark:#6A9955">//xltx is the extension for excel templates.</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Report.Run(</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        TPath.Combine(GetDataPath, </span><span style="color:#A31515;--shiki-dark:#CE9178">'Getting Started Reports.template.xlsx'</span><span style="color:#000000;--shiki-dark:#D4D4D4">),</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        FileName);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        ShellExecute(</span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">''</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">PCHAR</span><span style="color:#000000;--shiki-dark:#D4D4D4">(FileName), </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">, SW_SHOWNORMAL);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">     finally</span></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">  {$if CompilerVersion &#x3C; 28.0}</span><span style="color:#000000;--shiki-dark:#D4D4D4"> </span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">        //For Delphi &#x3C; XE7, we don't have TTask, so we use this other code instead.</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">        //The code here is not perfect, since if you exit the app before the thread ends,</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">        //Delphi will kill the thread and not delete the file.</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">        //So for a real app, in Delphi &#x3C; XE7, you would have to check OnTerminate in the app</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">        //and delete pending files. For simplicity we won't do it here.</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">        //The TTask version for Delphi >=XE7 will delete the file even if you exit the app.</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">        //So when using Delphi>=XE7 you don't need to do anything.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        </span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        TThread.CreateAnonymousThread(</span><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">         TThread.Sleep(</span><span style="color:#098658;--shiki-dark:#B5CEA8">30000</span><span style="color:#000000;--shiki-dark:#D4D4D4">); </span><span style="color:#008000;--shiki-dark:#6A9955">//wait for 30 secs to give Excel time to start.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">         TFile.Delete(FileName);  </span><span style="color:#008000;--shiki-dark:#6A9955">//As it is an xltx file, we can delete it even when it is open on Excel.</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">         end</span><span style="color:#000000;--shiki-dark:#D4D4D4">).Start; </span></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">  {$ELSE}</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">       //See https://doc.tmssoftware.com/flexcel/vcl/tips/automatically-open-generated-excel-files.html</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">       TTask.Run(</span><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">         TThread.Sleep(</span><span style="color:#098658;--shiki-dark:#B5CEA8">30000</span><span style="color:#000000;--shiki-dark:#D4D4D4">); </span><span style="color:#008000;--shiki-dark:#6A9955">//wait for 30 secs to give Excel time to start.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">         TFile.Delete(FileName);  </span><span style="color:#008000;--shiki-dark:#6A9955">//As it is an xltx file, we can delete it even when it is open on Excel.</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">         end</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">  {$IFEND}</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">     end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Report.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span></span>
<span class="line"></span>
<span class="line"></span></code></pre>


