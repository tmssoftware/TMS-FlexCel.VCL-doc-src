---
uid: ExportPdf-Delphi
description: ExportPdf-Delphi
---


# Exporting Excel files to PDF (Delphi)

> [!Note]
> This demo is available in your FlexCel installation at ***&lt;FlexCel Install Folder>*\\Demo\\Delphi\\Modules\\25\.Printing and Exporting\\30\.ExportPdf** and also at [https:&#8203;//&#8203;github.&#8203;com/&#8203;tmssoftware/&#8203;TMS-&#8203;FlexCel.&#8203;VCL-&#8203;demos/&#8203;tree/&#8203;master/&#8203;Delphi/&#8203;Modules/&#8203;25.&#8203;Printing and Exporting/&#8203;30.&#8203;ExportPdf](https://github\.com/tmssoftware/TMS\-FlexCel\.VCL\-demos/tree/master/Delphi/Modules/25\.Printing%20and%20Exporting/30\.ExportPdf)


## Overview


FlexCel can natively export an Excel file to PDF, without needing to
have Excel or Adobe Pdf installed.

## Concepts

- FlexCel PDF output is not 100% identical to Excel output, and it
  can't be that way. But it is very similar, and this includes
  fonts, colors, margins, headers/footers/images, etc. It can print
  cells with multiple fonts, it can replace the macros on headers
  and footers (like \"&CPage &P of &N\"), export headers and
  hyperlinks, correctly export conditional formats and the list goes
  on.

- Among the things that are **not** exported you can find:

  - ActiveX objects

  - 3D Charts (They will be rendered as 2d)

  - Not common AutoShapes (most used Autoshapes, as rectangles, rounded
    rectangles, ellipses, etc are exported)

## Files

### UExportPdf.pas

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">unit</span><span style="color:#000000;--shiki-dark:#D4D4D4"> UExportPdf;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">interface</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">uses</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Windows, Messages, SysUtils, Variants, Classes, Graphics,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Controls, Forms, Dialogs, ImgList, ActnList, StdCtrls,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Tabs, Grids,ExtCtrls, ComCtrls, ToolWin,</span></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">  {$if CompilerVersion >= 23.0}</span><span style="color:#000000;--shiki-dark:#D4D4D4"> System.UITypes, </span><span style="color:#811F3F;--shiki-dark:#D16969">{$IFEND}</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ShellAPI,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FlexCel.VCLSupport, FlexCel.Core, FlexCel.XlsAdapter, FlexCel.Render, FlexCel.Pdf;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">type</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TFExportPdf = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span><span style="color:#000000;--shiki-dark:#D4D4D4">(TForm)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolBar1: TToolBar;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolButton1: TToolButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolButton2: TToolButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolButton3: TToolButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolButton6: TToolButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Actions: TActionList;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ActionOpen: TAction;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ActionExportAsPdf: TAction;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ActionClose: TAction;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    OpenDialog: TOpenDialog;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolbarImages: TImageList;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolButton5: TToolButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Panel1: TPanel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Label1: TLabel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    cbExportObject: TComboBox;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    cbSheet: TComboBox;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Label2: TLabel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Panel2: TPanel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Label3: TLabel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    chGridLines: TCheckBox;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    chPrintLeft: TCheckBox;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Panel3: TPanel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Label4: TLabel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Panel6: TPanel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Label7: TLabel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Panel7: TPanel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Label9: TLabel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    edTop: TEdit;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Label10: TLabel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Label11: TLabel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    edBottom: TEdit;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Label12: TLabel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    edLeft: TEdit;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    edRight: TEdit;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Label13: TLabel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Label14: TLabel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Panel9: TPanel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Label16: TLabel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    cbConfidential: TCheckBox;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    chFormulaText: TCheckBox;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ExportDialog: TSaveDialog;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    edHeader: TLabeledEdit;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    edFooter: TLabeledEdit;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    chLandscape: TCheckBox;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    chFitIn: TCheckBox;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    edHPages: TLabeledEdit;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    edVPages: TLabeledEdit;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    edZoom: TLabeledEdit;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    edl: TLabeledEdit;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    edt: TLabeledEdit;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    edh: TLabeledEdit;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    edr: TLabeledEdit;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    edb: TLabeledEdit;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    edf: TLabeledEdit;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Panel4: TPanel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Label5: TLabel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    cbFontMapping: TComboBox;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    chEmbed: TCheckBox;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    chSubset: TCheckBox;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    cbKerning: TCheckBox;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Panel5: TPanel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Label6: TLabel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    edSubject: TLabeledEdit;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    edAuthor: TLabeledEdit;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    edTitle: TLabeledEdit;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Panel8: TPanel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Label8: TLabel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    cbPdfType: TComboBox;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    cbVersion: TComboBox;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    cbTagged: TComboBox;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Label15: TLabel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Label17: TLabel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Label18: TLabel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    edLang: TLabeledEdit;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolbarImages_100Scale: TImageList;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolbarImages_300Scale: TImageList;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ScrollBox1: TScrollBox;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ActionCloseExecute</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ActionOpenExecute</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ActionExportAsPdfExecute</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> chFitInClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> cbSheetChange</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> cbExportObjectChange</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> FormCreate</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  private</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Pdf: TFlexCelPdfExport;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> LoadSheetConfig</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> HasFileOpen</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Boolean</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> LoadPreferences</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Boolean</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> PdfExport_AfterGeneratePage</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> sender: TObject;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> e: TPageEventArgs);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  public</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    constructor</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Create</span><span style="color:#000000;--shiki-dark:#D4D4D4">(aOwner: TComponent); </span><span style="color:#0000FF;--shiki-dark:#569CD6">override</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    destructor</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Destroy</span><span style="color:#000000;--shiki-dark:#D4D4D4">; </span><span style="color:#0000FF;--shiki-dark:#569CD6">override</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    { Public declarations }</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FExportPdf: TFExportPdf;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">implementation</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">uses</span><span style="color:#000000;--shiki-dark:#D4D4D4"> IOUtils, UFlexCelHDPI;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">{$R *.dfm}</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">constructor</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFExportPdf.Create</span><span style="color:#000000;--shiki-dark:#D4D4D4">(aOwner: TComponent);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  inherited</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Pdf := TFlexCelPdfExport.Create;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Pdf.AllowOverwritingFiles := </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Pdf.AfterGeneratePage := PdfExport_AfterGeneratePage;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">destructor</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFExportPdf.Destroy</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Pdf.Workbook.Free;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FreeAndNil(Pdf);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  inherited</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFExportPdf.FormCreate</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  RegisterForHDPI(Self, </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFExportPdf.ActionCloseExecute</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Close;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFExportPdf.ActionExportAsPdfExecute</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  PdfStream: TFileStream;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#0000FF;--shiki-dark:#569CD6"> not</span><span style="color:#000000;--shiki-dark:#D4D4D4"> HasFileOpen </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#0000FF;--shiki-dark:#569CD6"> not</span><span style="color:#000000;--shiki-dark:#D4D4D4"> LoadPreferences </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#0000FF;--shiki-dark:#569CD6"> not</span><span style="color:#000000;--shiki-dark:#D4D4D4"> ExportDialog.Execute </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  PdfStream := TFileStream.Create(exportDialog.FileName, fmCreate);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Pdf.BeginExport(PdfStream);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> cbExportObject.ItemIndex = </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Pdf.PageLayout := TPageLayout.Outlines;  </span><span style="color:#008000;--shiki-dark:#6A9955">//To how the bookmarks when opening the file.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Pdf.ExportAllVisibleSheets(</span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TPath.GetFileNameWithoutExtension(exportDialog.FileName));</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#0000FF;--shiki-dark:#569CD6"> else</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Pdf.PageLayout := TPageLayout.None;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Pdf.ExportSheet;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Pdf.EndExport;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> MessageDlg(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Do you want to open the generated file?'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, mtConfirmation, [mbYes, mbNo], </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">) = mrYes </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      ShellExecute(</span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'open'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">PCHAR</span><span style="color:#000000;--shiki-dark:#D4D4D4">(ExportDialog.FileName), </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">, SW_SHOWNORMAL);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FreeAndNil(PdfStream);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFExportPdf.ActionOpenExecute</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls: TExcelFile;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  i: </span><span style="color:#0000FF;--shiki-dark:#569CD6">integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#0000FF;--shiki-dark:#569CD6"> not</span><span style="color:#000000;--shiki-dark:#D4D4D4"> OpenDialog.Execute </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Pdf.Workbook = </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Pdf.Workbook := TXlsFile.Create;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Pdf.Workbook.Open(OpenDialog.FileName);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Caption := </span><span style="color:#A31515;--shiki-dark:#CE9178">'Export: '</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + OpenDialog.FileName;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls := Pdf.Workbook;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  cbSheet.Items.Clear;</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">  for</span><span style="color:#000000;--shiki-dark:#D4D4D4"> i := </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#0000FF;--shiki-dark:#569CD6"> to</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Xls.SheetCount </span><span style="color:#AF00DB;--shiki-dark:#C586C0">do</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    cbSheet.Items.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Add</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Xls.GetSheetName(i));</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  cbSheet.ItemIndex := Xls.ActiveSheet - </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  LoadSheetConfig;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFExportPdf.cbExportObjectChange</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  cbSheet.Enabled := cbExportObject.ItemIndex &#x3C;> </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFExportPdf.cbSheetChange</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Pdf.Workbook.ActiveSheet := cbSheet.ItemIndex + </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  LoadSheetConfig;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFExportPdf.chFitInClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  edVPages.Enabled :=  chFitIn.Checked;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  edHPages.Enabled :=  chFitIn.Checked;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  edZoom.Enabled := </span><span style="color:#0000FF;--shiki-dark:#569CD6">not</span><span style="color:#000000;--shiki-dark:#D4D4D4"> chFitIn.Checked;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFExportPdf.LoadSheetConfig</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls: TExcelFile;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  m: TXlsMargins;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls := Pdf.Workbook;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  chGridLines.Checked := Xls.PrintGridLines;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  chFormulaText.Checked := Xls.ShowFormulaText;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  chPrintLeft.Checked := TPrintOptions.LeftToRight </span><span style="color:#0000FF;--shiki-dark:#569CD6">in</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Xls.PrintOptions;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  edHeader.Text := Xls.PageHeader;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  edFooter.Text := Xls.PageFooter;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  chFitIn.Checked := Xls.PrintToFit;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  edHPages.Text := IntToStr(Xls.PrintNumberOfHorizontalPages);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  edVPages.Text := IntToStr(Xls.PrintNumberOfVerticalPages);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  edVPages.Enabled := chFitIn.Checked;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  edHPages.Enabled := chFitIn.Checked;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  edZoom.Enabled := </span><span style="color:#0000FF;--shiki-dark:#569CD6">not</span><span style="color:#000000;--shiki-dark:#D4D4D4"> chFitIn.Checked;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  edZoom.Text := IntToStr(Xls.PrintScale);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  m := Xls.GetPrintMargins;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  edl.Text := FloatToStr(m.Left);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  edt.Text := FloatToStr(m.Top);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  edr.Text := FloatToStr(m.Right);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  edb.Text := FloatToStr(m.Bottom);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  edf.Text := FloatToStr(m.Footer);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  edh.Text := FloatToStr(m.Header);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  chLandscape.Checked :=  Xls.PrintLandscape;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  edAuthor.Text := Xls.DocumentProperties.GetStandardProperty(TPropertyId.Author);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  edTitle.Text := Xls.DocumentProperties.GetStandardProperty(TPropertyId.Title);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  edSubject.Text := Xls.DocumentProperties.GetStandardProperty(TPropertyId.Subject);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFExportPdf.HasFileOpen</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Boolean</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Pdf.Workbook = </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ShowMessage(</span><span style="color:#A31515;--shiki-dark:#CE9178">'You need to open a file first.'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFExportPdf.LoadPreferences</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Boolean</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls: TExcelFile;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  m: TXlsMargins;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span><span style="color:#008000;--shiki-dark:#6A9955">  //NOTE: THERE SHOULD BE *A LOT* MORE VALIDATION OF VALUES ON THIS METHOD. (For example, validate that margins are between bounds)</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  // As this is a simple demo, they are not included.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Xls := Pdf.Workbook;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Xls.PrintGridLines := chGridLines.Checked;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Xls.PageHeader := edHeader.Text;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Xls.PageFooter := edFooter.Text;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Xls.ShowFormulaText := chFormulaText.Checked;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> chFitIn.Checked </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Xls.PrintToFit := </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Xls.PrintNumberOfHorizontalPages := StrToInt(edHPages.Text);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Xls.PrintNumberOfVerticalPages := StrToInt(edVPages.Text);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#0000FF;--shiki-dark:#569CD6"> else</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Xls.PrintToFit := </span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> chPrintLeft.Checked </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Xls.PrintOptions:= Xls.PrintOptions + [TPrintOptions.LeftToRight] </span><span style="color:#0000FF;--shiki-dark:#569CD6">else</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Xls.PrintOptions:= Xls.PrintOptions - [TPrintOptions.LeftToRight];</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Xls.PrintScale := StrToInt(edZoom.Text);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    except</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">        begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">          ShowMessage(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Invalid Zoom'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">          exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">        end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    m := TXlsMargins.Create;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    m.Left := StrToFloat(edl.Text);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    m.Top := StrToFloat(edt.Text);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    m.Right := StrToFloat(edr.Text);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    m.Bottom := StrToFloat(edb.Text);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    m.Footer := StrToFloat(edf.Text);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    m.Header := StrToFloat(edh.Text);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Xls.SetPrintMargins(m);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Pdf.PrintRangeLeft := StrToInt(edLeft.Text);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Pdf.PrintRangeTop := StrToInt(edTop.Text);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Pdf.PrintRangeRight := StrToInt(edRight.Text);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Pdf.PrintRangeBottom := StrToInt(edBottom.Text);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> chEmbed.Checked </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Pdf.FontEmbed := TFontEmbed.Embed </span><span style="color:#0000FF;--shiki-dark:#569CD6">else</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Pdf.FontEmbed := TFontEmbed.None;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> chSubset.Checked </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Pdf.FontSubset := TFontSubset.Subset </span><span style="color:#0000FF;--shiki-dark:#569CD6">else</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Pdf.FontSubset := TFontSubset.DontSubset;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Pdf.Kerning := cbKerning.Checked;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    case</span><span style="color:#000000;--shiki-dark:#D4D4D4"> cbFontMapping.ItemIndex </span><span style="color:#0000FF;--shiki-dark:#569CD6">of</span></span>
<span class="line"><span style="color:#098658;--shiki-dark:#B5CEA8">      0</span><span style="color:#000000;--shiki-dark:#D4D4D4">:</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        Pdf.FontMapping := TFontMapping.ReplaceAllFonts;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#098658;--shiki-dark:#B5CEA8">      1</span><span style="color:#000000;--shiki-dark:#D4D4D4">:</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        Pdf.FontMapping := TFontMapping.ReplaceStandardFonts;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#098658;--shiki-dark:#B5CEA8">      2</span><span style="color:#000000;--shiki-dark:#D4D4D4">:</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        Pdf.FontMapping := TFontMapping.DontReplaceFonts;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    case</span><span style="color:#000000;--shiki-dark:#D4D4D4"> cbPdfType.ItemIndex </span><span style="color:#0000FF;--shiki-dark:#569CD6">of</span></span>
<span class="line"><span style="color:#098658;--shiki-dark:#B5CEA8">      0</span><span style="color:#000000;--shiki-dark:#D4D4D4">: Pdf.PdfType := TPdfType.Standard;</span></span>
<span class="line"><span style="color:#098658;--shiki-dark:#B5CEA8">      1</span><span style="color:#000000;--shiki-dark:#D4D4D4">: Pdf.PdfType := TPdfType.PDFA1;</span></span>
<span class="line"><span style="color:#098658;--shiki-dark:#B5CEA8">      2</span><span style="color:#000000;--shiki-dark:#D4D4D4">: Pdf.PdfType := TPdfType.PDFA2;</span></span>
<span class="line"><span style="color:#098658;--shiki-dark:#B5CEA8">      3</span><span style="color:#000000;--shiki-dark:#D4D4D4">: Pdf.PdfType := TPdfType.PDFA3;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    case</span><span style="color:#000000;--shiki-dark:#D4D4D4"> cbTagged.ItemIndex </span><span style="color:#0000FF;--shiki-dark:#569CD6">of</span></span>
<span class="line"><span style="color:#098658;--shiki-dark:#B5CEA8">      0</span><span style="color:#000000;--shiki-dark:#D4D4D4">: Pdf.TagMode := TTagMode.Full;</span></span>
<span class="line"><span style="color:#098658;--shiki-dark:#B5CEA8">      1</span><span style="color:#000000;--shiki-dark:#D4D4D4">: Pdf.TagMode := TTagMode.None;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    case</span><span style="color:#000000;--shiki-dark:#D4D4D4"> cbVersion.ItemIndex </span><span style="color:#0000FF;--shiki-dark:#569CD6">of</span></span>
<span class="line"><span style="color:#098658;--shiki-dark:#B5CEA8">      0</span><span style="color:#000000;--shiki-dark:#D4D4D4">: Pdf.PdfVersion := TPdfVersion.v14;</span></span>
<span class="line"><span style="color:#098658;--shiki-dark:#B5CEA8">      1</span><span style="color:#000000;--shiki-dark:#D4D4D4">: Pdf.PdfVersion := TPdfVersion.v16;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Pdf.Properties := TPdfProperties.Create(</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">                          edTitle.Text,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">                          edAuthor.Text,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">                          edSubject.Text,</span></span>
<span class="line"><span style="color:#A31515;--shiki-dark:#CE9178">                          ''</span><span style="color:#000000;--shiki-dark:#D4D4D4">,</span></span>
<span class="line"><span style="color:#A31515;--shiki-dark:#CE9178">                          ''</span><span style="color:#000000;--shiki-dark:#D4D4D4">,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">                          edLang.Text);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Xls.PrintLandscape := chLandscape.Checked;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  except</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    on</span><span style="color:#000000;--shiki-dark:#D4D4D4"> e: Exception </span><span style="color:#AF00DB;--shiki-dark:#C586C0">do</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        ShowMessage(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Error: '</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + e.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Message</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">        exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFExportPdf.PdfExport_AfterGeneratePage</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> sender: TObject; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> e: TPageEventArgs);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ABrush: TUIBrush;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  AFont: TUIFont;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  x0: RealNumber;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  y0: RealNumber;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  sf: TUISize;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">const</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  s = </span><span style="color:#A31515;--shiki-dark:#CE9178">'Confidential'</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#0000FF;--shiki-dark:#569CD6"> not</span><span style="color:#000000;--shiki-dark:#D4D4D4"> cbConfidential.Checked </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ABrush := TUISolidBrush.CreateNew(TUIColor.FromArgb(</span><span style="color:#098658;--shiki-dark:#B5CEA8">$1E</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">$19</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">$19</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">$19</span><span style="color:#000000;--shiki-dark:#D4D4D4">));  </span><span style="color:#008000;--shiki-dark:#6A9955">//Red=Green=Blue is a shade of gray. Alpha=30 means it is transparent (255 is pure opaque, 0 is pure transparent).</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    AFont := TUIFont.CreateNew(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Arial'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">$48</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      x0 := ((e.DataFile.PageSize.Width * </span><span style="color:#098658;--shiki-dark:#B5CEA8">72</span><span style="color:#000000;--shiki-dark:#D4D4D4">) / </span><span style="color:#098658;--shiki-dark:#B5CEA8">100</span><span style="color:#000000;--shiki-dark:#D4D4D4">) / </span><span style="color:#098658;--shiki-dark:#B5CEA8">2</span><span style="color:#000000;--shiki-dark:#D4D4D4">;  </span><span style="color:#008000;--shiki-dark:#6A9955">//PageSize is in inches/100, our coordinate system is in Points, that is inches/72</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      y0 := ((e.DataFile.PageSize.Height * </span><span style="color:#098658;--shiki-dark:#B5CEA8">72</span><span style="color:#000000;--shiki-dark:#D4D4D4">) / </span><span style="color:#098658;--shiki-dark:#B5CEA8">100</span><span style="color:#000000;--shiki-dark:#D4D4D4">) / </span><span style="color:#098658;--shiki-dark:#B5CEA8">2</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      sf := e.DataFile.MeasureString(s, AFont);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      e.DataFile.Rotate(x0, y0, </span><span style="color:#098658;--shiki-dark:#B5CEA8">$2D</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      e.DataFile.DrawString(s, AFont, ABrush, x0 - (sf.Width / </span><span style="color:#098658;--shiki-dark:#B5CEA8">2</span><span style="color:#000000;--shiki-dark:#D4D4D4">), y0 + (sf.Height / </span><span style="color:#098658;--shiki-dark:#B5CEA8">2</span><span style="color:#000000;--shiki-dark:#D4D4D4">));  </span><span style="color:#008000;--shiki-dark:#6A9955">//the y coord means the bottom of the text, and as the y axis grows down, we have to add sf.height/2 instead of substracting it.</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      FreeAndNil(AFont);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FreeAndNil(ABrush);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span></span>
<span class="line"></span>
<span class="line"></span></code></pre>


