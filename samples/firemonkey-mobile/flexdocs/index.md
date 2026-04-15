---
uid: FlexDocs-FireMonkey_Mobile
description: FlexDocs-FireMonkey_Mobile
---


# FlexDocs (FireMonkey Mobile)

> [!Note]
> This demo is available in your FlexCel installation at ***&lt;FlexCel Install Folder>*\\Demo\\FireMonkey Mobile\\Modules\\50\.FlexDocs** and also at [https:&#8203;//&#8203;github.&#8203;com/&#8203;tmssoftware/&#8203;TMS-&#8203;FlexCel.&#8203;VCL-&#8203;demos/&#8203;tree/&#8203;master/&#8203;Fire&#8203;Monkey Mobile/&#8203;Modules/&#8203;50.&#8203;Flex&#8203;Docs](https://github\.com/tmssoftware/TMS\-FlexCel\.VCL\-demos/tree/master/FireMonkey%20Mobile/Modules/50\.FlexDocs)


## Overview


This demo shows the preview control.

## Concepts

- How to use the preview control to display an Excel file.

- How to embed an Excel file in the app by using a .rc file.

- How to export the file to pdf and share it with other apps.

## Files

### UFlexDocs.pas

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">unit</span><span style="color:#000000;--shiki-dark:#D4D4D4"> UFlexDocs;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">interface</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">uses</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  System.SysUtils, System.Types, System.UITypes, System.Classes, System.Variants,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FMX.Types, FMX.Controls, FMX.Forms, FMX.Graphics, FMX.Dialogs,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FlexCel.FMXSupport, FlexCel.Core, FlexCel.XlsAdapter, FlexCel.Render, FlexCel.Pdf, System.Actions,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FMX.ActnList, FMX.FlexCel.DocExport, FMX.StdCtrls, FMX.Layouts,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FMX.FlexCel.Preview, FMX.Controls.Presentation;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">type</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TFFlexDocs = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span><span style="color:#000000;--shiki-dark:#D4D4D4">(TForm)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Previewer: TFlexCelPreviewer;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolBar1: TToolBar;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    btnShare: TButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ActionList1: TActionList;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FlexCelDocExport: TFlexCelDocExport;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ActionShare: TAction;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    btnOpen: TButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ActionOpen: TAction;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ActionShareExecute</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ActionOpenExecute</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  private</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    { Private declarations }</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  public</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    { Public declarations }</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FFlexDocs: TFFlexDocs;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">implementation</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">uses</span><span style="color:#000000;--shiki-dark:#D4D4D4"> IOUtils;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">{$R *.fmx}</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFFlexDocs.ActionOpenExecute</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Template: TResourceStream;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (Previewer.Document &#x3C;> </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">    {$IFNDEF NEXTGEN}</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Previewer.Document.Workbook.Free;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Previewer.Document.Free;</span></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">    {$ENDIF}</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Previewer.Document := </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Previewer.Document := TFlexCelImgExport.Create();</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Template := TResourceStream.Create(HInstance, </span><span style="color:#A31515;--shiki-dark:#CE9178">'WeddingBudget'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, RT_RCDATA);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Previewer.Document.Workbook := TXlsFile.Create(</span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Previewer.Document.Workbook.Open(Template);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Template.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Previewer.InvalidatePreview;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFFlexDocs.ActionShareExecute</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  pdf: TFlexCelPdfExport;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  fs: TFileStream;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TmpFileName: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  DestFolder: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (Previewer.Document = </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">) or (Previewer.Document.Workbook = </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ShowMessage(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Open a file first!'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  DestFolder := TPath.GetDocumentsPath;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> DestFolder = </span><span style="color:#A31515;--shiki-dark:#CE9178">''</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ShowMessage(</span><span style="color:#A31515;--shiki-dark:#CE9178">'This device doesn''t have internal storage'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TmpFileName := TPath.Combine(DestFolder, </span><span style="color:#A31515;--shiki-dark:#CE9178">'doc.pdf'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  pdf := TFlexCelPdfExport.Create(Previewer.Document.Workbook, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    //Android only has 3 fonts by default, so we can't get too fancy with them.</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    //We will replace them all by standard pdf fonts. If we wanted to embed the fonts,</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    //we would have to provide an OnGetFontFolder or OnGetFontData event where we provide</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    //the ttf data for the fonts.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    pdf.FontMapping := TFontMapping.ReplaceAllFonts;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    fs := TFileStream.Create(TmpFileName, fmCreate);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      pdf.BeginExport(fs);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      pdf.ExportAllVisibleSheets(</span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'Sheets'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      pdf.EndExport;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      fs.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    pdf.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">   // To send the file, we need to define a file provider in AndrodiManifest.xml</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  // See https://doc.tmssoftware.com/flexcel/vcl/guides/android-guide.html#sharing-files</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">   FlexCelDocExport.ExportFile(btnShare, TmpFileName);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span></span>
<span class="line"></span>
<span class="line"></span></code></pre>


