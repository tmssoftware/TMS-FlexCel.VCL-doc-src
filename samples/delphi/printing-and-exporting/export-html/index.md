---
uid: Export_HTML-Delphi
description: Export_HTML-Delphi
---


# Exporting Excel files to HTML (Delphi)

> [!Note]
> This demo is available in your FlexCel installation at ***&lt;FlexCel Install Folder>*\\Demo\\Delphi\\Modules\\25\.Printing and Exporting\\40\.Export HTML** and also at [https:&#8203;//&#8203;github.&#8203;com/&#8203;tmssoftware/&#8203;TMS-&#8203;FlexCel.&#8203;VCL-&#8203;demos/&#8203;tree/&#8203;master/&#8203;Delphi/&#8203;Modules/&#8203;25.&#8203;Printing and Exporting/40.Export HTML](https://github\.com/tmssoftware/TMS\-FlexCel\.VCL\-demos/tree/master/Delphi/Modules/25\.Printing%20and%20Exporting/40\.Export%20HTML)


## Overview


FlexCel can natively export an Excel file to HTML, in many formats like XHTML 1.1, HTML 3.2, HTML 4.1 strict or HTML 5.

## Concepts

- HTML is a format that makes emphasis in semantics over presentation,
  and because of this reason the HTML file will not be as faithful
  to the original file as a PDF. PDF are targeted especially for
  handling presentation. Anyway, the output is very similar and in
  many ways better (and more cross-browser) than the HTML generated
  by Excel itself when saving to HTML.

- Among the things that are **not** exported you can find:

- ActiveX objects

- 3D Charts (They will be rendered as 2d)

- Not common AutoShapes (most used Autoshapes, as rectangles, rounded
  rectangles, ellipses, etc are exported)

## Files

### UExportHTML.pas

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">unit</span><span style="color:#000000;--shiki-dark:#D4D4D4"> UExportHTML;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">interface</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">uses</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Windows, Messages, SysUtils, Variants, Classes, Graphics,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Controls, Forms, Dialogs, ImgList, ActnList, StdCtrls,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Tabs, Grids,ExtCtrls, ComCtrls, ToolWin,</span></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">  {$if CompilerVersion >= 23.0}</span><span style="color:#000000;--shiki-dark:#D4D4D4"> System.UITypes, </span><span style="color:#811F3F;--shiki-dark:#D16969">{$IFEND}</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ShellAPI, UMailDialog,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FlexCel.VCLSupport, FlexCel.Core, FlexCel.XlsAdapter, FlexCel.Render;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">type</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TFExportHTML = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span><span style="color:#000000;--shiki-dark:#D4D4D4">(TForm)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolBar1: TToolBar;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolButton1: TToolButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolButton2: TToolButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolButton3: TToolButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolButton4: TToolButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolButton6: TToolButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Actions: TActionList;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ActionOpen: TAction;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ActionExportAsHTML: TAction;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ActionExportAsMHTML: TAction;</span></span>
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
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    chPrintHeadings: TCheckBox;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Panel3: TPanel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Label4: TLabel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    cbImages: TCheckBox;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    cbComments: TCheckBox;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    cbHyperlinks: TCheckBox;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    cbHeadersFooters: TCheckBox;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Panel4: TPanel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Label5: TLabel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    cbOutlook2007: TCheckBox;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    cbIe6Png: TCheckBox;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Panel5: TPanel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Label6: TLabel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    cbLeft: TCheckBox;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    cbTop: TCheckBox;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    cbRight: TCheckBox;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    cbBottom: TCheckBox;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Panel6: TPanel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Label7: TLabel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Label8: TLabel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    cbHtmlVersion: TComboBox;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    cbFileFormat: TComboBox;</span></span>
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
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Panel8: TPanel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Label15: TLabel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    edSheetSeparator: TEdit;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Panel9: TPanel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Label16: TLabel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    edBodyStart: TEdit;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Panel10: TPanel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Label17: TLabel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    edImages: TEdit;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Panel11: TPanel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    edCss: TEdit;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    cbCss: TCheckBox;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    cbReplaceFonts: TCheckBox;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    chFormulaText: TCheckBox;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ExportDialog: TSaveDialog;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    sbSVG: TCheckBox;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Label18: TLabel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    cbEmbedImages: TCheckBox;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolbarImages_100Scale: TImageList;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolbarImages_300Scale: TImageList;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ActionCloseExecute</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ActionOpenExecute</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> cbSheetChange</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ActionExportAsHTMLExecute</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> cbExportObjectChange</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> cbCssClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ActionExportAsMHTMLExecute</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> FormCreate</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  private</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Html: TFlexCelHtmlExport;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> LoadSheetConfig</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> HasFileOpen</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Boolean</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> LoadPreferences</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Boolean</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> HtmlFont</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> sender: TObject; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> e: THtmlFontEventArgs);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> GenerateMHTML</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  public</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    constructor</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Create</span><span style="color:#000000;--shiki-dark:#D4D4D4">(aOwner: TComponent); </span><span style="color:#0000FF;--shiki-dark:#569CD6">override</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    destructor</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Destroy</span><span style="color:#000000;--shiki-dark:#D4D4D4">; </span><span style="color:#0000FF;--shiki-dark:#569CD6">override</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    { Public declarations }</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FExportHTML: TFExportHTML;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">implementation</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">uses</span><span style="color:#000000;--shiki-dark:#D4D4D4"> IOUtils, UFlexCelHDPI;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">{$R *.dfm}</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">constructor</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFExportHTML.Create</span><span style="color:#000000;--shiki-dark:#D4D4D4">(aOwner: TComponent);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  inherited</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Html := TFlexCelHtmlExport.Create;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Html.AllowOverwritingFiles := </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Html.HtmlFont := HtmlFont;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">destructor</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFExportHTML.Destroy</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Html.Workbook.Free;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FreeAndNil(Html);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  inherited</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFExportHTML.FormCreate</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  RegisterForHDPI(Self, </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFExportHTML.HtmlFont</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> sender: TObject; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> e: THtmlFontEventArgs);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> cbReplaceFonts.Checked </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    e.FontFamily := </span><span style="color:#A31515;--shiki-dark:#CE9178">'arial, sans-serif'</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFExportHTML.ActionCloseExecute</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Close;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFExportHTML.ActionExportAsHTMLExecute</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  CssFileName: </span><span style="color:#0000FF;--shiki-dark:#569CD6">String</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FileNameToOpen: </span><span style="color:#0000FF;--shiki-dark:#569CD6">String</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  SelectorPosition: TSheetSelectorPositionSet;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  GeneratedFiles: TArray&#x3C;</span><span style="color:#0000FF;--shiki-dark:#569CD6">String</span><span style="color:#000000;--shiki-dark:#D4D4D4">>;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#0000FF;--shiki-dark:#569CD6"> not</span><span style="color:#000000;--shiki-dark:#D4D4D4"> HasFileOpen </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#0000FF;--shiki-dark:#569CD6"> not</span><span style="color:#000000;--shiki-dark:#D4D4D4"> LoadPreferences </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> cbFileFormat.ItemIndex = </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Html.HtmlFileFormat := THtmlFileFormat.MHtml;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ExportDialog.FilterIndex := </span><span style="color:#098658;--shiki-dark:#B5CEA8">2</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#0000FF;--shiki-dark:#569CD6"> else</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Html.HtmlFileFormat := THtmlFileFormat.Html;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ExportDialog.FilterIndex := </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#0000FF;--shiki-dark:#569CD6"> not</span><span style="color:#000000;--shiki-dark:#D4D4D4"> ExportDialog.Execute </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Html.AllowOverwritingFiles := </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Html.SavedImagesFormat := THtmlImageFormat.Png;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  CssFileName := </span><span style="color:#A31515;--shiki-dark:#CE9178">''</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> cbCss.Checked </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    CssFileName := edCss.Text;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FileNameToOpen := ExportDialog.FileName;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  case</span><span style="color:#000000;--shiki-dark:#D4D4D4"> cbHtmlVersion.ItemIndex </span><span style="color:#0000FF;--shiki-dark:#569CD6">of</span></span>
<span class="line"><span style="color:#098658;--shiki-dark:#B5CEA8">    0</span><span style="color:#000000;--shiki-dark:#D4D4D4">: Html.HtmlVersion := THtmlVersion.Html_32;</span></span>
<span class="line"><span style="color:#098658;--shiki-dark:#B5CEA8">    2</span><span style="color:#000000;--shiki-dark:#D4D4D4">: Html.HtmlVersion := THtmlVersion.XHTML_10;</span></span>
<span class="line"><span style="color:#098658;--shiki-dark:#B5CEA8">    3</span><span style="color:#000000;--shiki-dark:#D4D4D4">: Html.HtmlVersion := THtmlVersion.Html_5;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    else</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Html.HtmlVersion := THtmlVersion.Html_401;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> edBodyStart.Text &#x3C;> </span><span style="color:#A31515;--shiki-dark:#CE9178">''</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Html.ExtraInfo.BodyStart := TArray&#x3C;</span><span style="color:#0000FF;--shiki-dark:#569CD6">String</span><span style="color:#000000;--shiki-dark:#D4D4D4">>.Create(edBodyStart.Text);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  case</span><span style="color:#000000;--shiki-dark:#D4D4D4"> cbExportObject.ItemIndex </span><span style="color:#0000FF;--shiki-dark:#569CD6">of</span></span>
<span class="line"><span style="color:#098658;--shiki-dark:#B5CEA8">    0</span><span style="color:#000000;--shiki-dark:#D4D4D4">:</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      SelectorPosition := [];</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> cbTop.Checked </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        SelectorPosition:= SelectorPosition + [TSheetSelectorPosition.Top];</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> cbLeft.Checked </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        SelectorPosition:= SelectorPosition + [TSheetSelectorPosition.Left];</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> cbBottom.Checked </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        SelectorPosition:= SelectorPosition + [TSheetSelectorPosition.Bottom];</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> cbRight.Checked </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        SelectorPosition:= SelectorPosition + [TSheetSelectorPosition.Right];</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Html.ExportAllVisibleSheetsAsTabs(TPath.GetDirectoryName(ExportDialog.FileName),</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        TPath.GetFileNameWithoutExtension(ExportDialog.FileName),</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        TPath.GetExtension(ExportDialog.FileName),</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        edImages.Text, CssFileName, TStandardSheetSelector.Create(SelectorPosition), </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      FileNameToOpen := TPath.Combine(TPath.GetDirectoryName(ExportDialog.FileName), TPath.GetFileNameWithoutExtension(ExportDialog.FileName));</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      FileNameToOpen := TPath.Combine(FileNameToOpen, Html.Workbook.SheetName);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      FileNameToOpen := TPath.Combine(FileNameToOpen, TPath.GetExtension(ExportDialog.FileName));</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#098658;--shiki-dark:#B5CEA8">    1</span><span style="color:#000000;--shiki-dark:#D4D4D4">:</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Html.ExportAllVisibleSheetsAsOneHtmlFile(ExportDialog.FileName, edImages.Text, CssFileName, edSheetSeparator.Text);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#098658;--shiki-dark:#B5CEA8">    2</span><span style="color:#000000;--shiki-dark:#D4D4D4">:</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        Html.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Export</span><span style="color:#000000;--shiki-dark:#D4D4D4">(ExportDialog.FileName, edImages.Text, CssFileName);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  GeneratedFiles := Html.GeneratedFiles.GetHtmlFiles;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Length(GeneratedFiles) = </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ShowMessage(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Error: No file has been generated'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#0000FF;--shiki-dark:#569CD6"> else</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> MessageDlg(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Do you want to open the generated file?'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, mtConfirmation, [mbYes, mbNo], </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">) = mrYes </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      ShellExecute(</span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'open'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">PCHAR</span><span style="color:#000000;--shiki-dark:#D4D4D4">(GeneratedFiles[</span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">]), </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">, SW_SHOWNORMAL);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFExportHTML.ActionExportAsMHTMLExecute</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  dr: TModalResult;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#0000FF;--shiki-dark:#569CD6"> not</span><span style="color:#000000;--shiki-dark:#D4D4D4"> HasFileOpen </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#0000FF;--shiki-dark:#569CD6"> not</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Html.FixOutlook2007CssSupport </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    dr := MessageDlg(</span><span style="color:#A31515;--shiki-dark:#CE9178">'You have not checked "Outlook 2007 support". If any of your clients has Outlook express, you should turn this on.'</span><span style="color:#000000;--shiki-dark:#D4D4D4">#</span><span style="color:#098658;--shiki-dark:#B5CEA8">$000A</span><span style="color:#000000;--shiki-dark:#D4D4D4">#</span><span style="color:#098658;--shiki-dark:#B5CEA8">$000A</span><span style="color:#A31515;--shiki-dark:#CE9178">'Use Outlook 2007 fix?'</span><span style="color:#000000;--shiki-dark:#D4D4D4">,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">         TMsgDlgType.mtWarning, [mbYes, mbNo, mbCancel], </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> dr = mrCancel </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">      exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> dr = mrYes </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      cbOutlook2007.Checked := </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Html.FixOutlook2007CssSupport := </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  MailDialog.GetMHTML := GenerateMHTML;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  MailDialog.ShowModal;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFExportHTML.ActionOpenExecute</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls: TExcelFile;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  i: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Int32</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#0000FF;--shiki-dark:#569CD6"> not</span><span style="color:#000000;--shiki-dark:#D4D4D4"> OpenDialog.Execute </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Html.Workbook = </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Html.Workbook := TXlsFile.Create;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Html.Workbook.Open(OpenDialog.FileName);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Caption := </span><span style="color:#A31515;--shiki-dark:#CE9178">'Export: '</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + OpenDialog.FileName;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls := Html.Workbook;</span></span>
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
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFExportHTML.cbCssClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  edCss.Enabled := cbCss.Checked;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFExportHTML.cbExportObjectChange</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  edSheetSeparator.Enabled := cbExportObject.ItemIndex = </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  cbTop.Enabled := cbExportObject.ItemIndex = </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  cbLeft.Enabled := cbExportObject.ItemIndex = </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  cbRight.Enabled := cbExportObject.ItemIndex = </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  cbBottom.Enabled := cbExportObject.ItemIndex = </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  cbSheet.Enabled := cbExportObject.ItemIndex = </span><span style="color:#098658;--shiki-dark:#B5CEA8">2</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFExportHTML.cbSheetChange</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Html.Workbook.ActiveSheet := cbSheet.ItemIndex + </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  LoadSheetConfig;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFExportHTML.LoadSheetConfig</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls: TExcelFile;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls := Html.Workbook;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  chGridLines.Checked := Xls.PrintGridLines;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  chPrintHeadings.Checked := Xls.PrintHeadings;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  chFormulaText.Checked := Xls.ShowFormulaText;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFExportHTML.HasFileOpen</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Boolean</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Html.Workbook = </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ShowMessage(</span><span style="color:#A31515;--shiki-dark:#CE9178">'You need to open a file first.'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFExportHTML.LoadPreferences</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Boolean</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls: TExcelFile;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //NOTE: THERE SHOULD BE *A LOT* MORE VALIDATION OF VALUES ON THIS METHOD.</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //(For example, validate that margins are between bounds)</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  // As this is a simple demo, they are not included.</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Xls := Html.Workbook;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">     //Note: In this demo we will only apply this things to the active sheet.</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">     //If you want to apply the settings to all the sheets, you should loop in the sheets and change them here.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Xls.PrintGridLines := chGridLines.Checked;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Xls.PrintHeadings := chPrintHeadings.Checked;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Xls.ShowFormulaText := chFormulaText.Checked;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Html.PrintRangeLeft := StrToInt(edLeft.Text);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Html.PrintRangeTop := StrToInt(edTop.Text);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Html.PrintRangeRight := StrToInt(edRight.Text);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Html.PrintRangeBottom := StrToInt(edBottom.Text);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (sbSVG.Checked) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Html.SavedImagesFormat := THtmlImageFormat.Svg </span><span style="color:#0000FF;--shiki-dark:#569CD6">else</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Html.SavedImagesFormat := THtmlImageFormat.Png;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Html.EmbedImages := cbEmbedImages.Checked;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Html.FixOutlook2007CssSupport := cbOutlook2007.Checked;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Html.FixIE6TransparentPngSupport := cbIe6Png.Checked;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Html.HidePrintObjects := [];</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#0000FF;--shiki-dark:#569CD6"> not</span><span style="color:#000000;--shiki-dark:#D4D4D4"> cbImages.Checked </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Html.HidePrintObjects:= Html.HidePrintObjects + [THidePrintObjects.Images];</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#0000FF;--shiki-dark:#569CD6"> not</span><span style="color:#000000;--shiki-dark:#D4D4D4"> cbHyperlinks.Checked </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Html.HidePrintObjects:= Html.HidePrintObjects + [THidePrintObjects.Hyperlynks];</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#0000FF;--shiki-dark:#569CD6"> not</span><span style="color:#000000;--shiki-dark:#D4D4D4"> cbComments.Checked </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Html.HidePrintObjects:= Html.HidePrintObjects + [THidePrintObjects.Comments];</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#0000FF;--shiki-dark:#569CD6"> not</span><span style="color:#000000;--shiki-dark:#D4D4D4"> cbHeadersFooters.Checked </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Html.HidePrintObjects:= Html.HidePrintObjects + [THidePrintObjects.Headers, THidePrintObjects.Footers];</span></span>
<span class="line"></span>
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
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFExportHTML.GenerateMHTML</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ms: TBytesStream;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  writer: TStreamWriter;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  preambleLen: </span><span style="color:#0000FF;--shiki-dark:#569CD6">integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  LoadPreferences;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Html.HtmlFileFormat := THtmlFileFormat.MHtml;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Html.AllowOverwritingFiles := </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Html.SavedImagesFormat := THtmlImageFormat.Png;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Html.HtmlVersion := THtmlVersion.Html_401;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> edBodyStart.Text &#x3C;> </span><span style="color:#A31515;--shiki-dark:#CE9178">''</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Html.ExtraInfo.BodyStart := TArray&#x3C;</span><span style="color:#0000FF;--shiki-dark:#569CD6">String</span><span style="color:#000000;--shiki-dark:#D4D4D4">>.Create(edBodyStart.Text);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ms := TBytesStream.Create;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    writer := TStreamWriter.Create(ms, TEncoding.UTF8);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Html.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Export</span><span style="color:#000000;--shiki-dark:#D4D4D4">(writer, Html.Workbook.ActiveFileName, </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      FreeAndNil(writer);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    PreambleLen := Length(TEncoding.UTF8.GetPreamble);</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">(TEncoding.UTF8.GetString(ms.Bytes, preambleLen, ms.Size - preambleLen));</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FreeAndNil(ms);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span></span>
<span class="line"></span>
<span class="line"></span></code></pre>


### UMailDialog.pas

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">unit</span><span style="color:#000000;--shiki-dark:#D4D4D4"> UMailDialog;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">interface</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">uses</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Windows, Messages, SysUtils, Variants, Classes, Graphics,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Controls, Forms, Dialogs, StdCtrls, ExtCtrls,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  IdBaseComponent, IdComponent, IdTCPConnection, IdTCPClient,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  IdExplicitTLSClientServerBase, IdMessageClient, IdSMTPBase, IdSMTP, IdMessage,</span></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">  {$if CompilerVersion >= 23.0}</span><span style="color:#000000;--shiki-dark:#D4D4D4"> System.UITypes, </span><span style="color:#811F3F;--shiki-dark:#D16969">{$IFEND}</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  IdIOHandler, IdIOHandlerSocket, IdIOHandlerStack, IdSSL, IdSSLOpenSSL, StrUtils;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">type</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TMailDialog = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span><span style="color:#000000;--shiki-dark:#D4D4D4">(TForm)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    edFrom: TLabeledEdit;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    edTo: TLabeledEdit;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    edSubject: TLabeledEdit;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    edOutServer: TLabeledEdit;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    btnSend: TButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    btnCancel: TButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Mailer: TIdSMTP;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Msg: TIdMessage;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    edPort: TLabeledEdit;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    edUserName: TLabeledEdit;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    edPassword: TLabeledEdit;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    cbUseTLS: TCheckBox;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    SSLHandler: TIdSSLIOHandlerSocketOpenSSL;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> btnSendClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> FormCreate</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> edFromExit</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> cbUseTLSClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  private</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    OriginalTo, OriginalFrom, OriginalServer: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ValidateFields</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Boolean</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> FillServer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> FillMsgBody</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    { Private declarations }</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  public</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    GetMHTML: TFunc&#x3C;</span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">>;</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    { Public declarations }</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  MailDialog: TMailDialog;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">implementation</span></span>
<span class="line"></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">{$R *.dfm}</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TMailDialog.cbUseTLSClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  edPort.Visible := cbUseTLS.Checked;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  edUserName.Visible := cbUseTLS.Checked;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  edPassword.Visible := cbUseTLS.Checked;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TMailDialog.edFromExit</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6"> if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (OriginalTo = edTo.Text) and (OriginalFrom &#x3C;> edFrom.Text) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    edTo.Text := edFrom.Text;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FillServer;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> edUserName.Text = </span><span style="color:#A31515;--shiki-dark:#CE9178">''</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span><span style="color:#000000;--shiki-dark:#D4D4D4"> edUserName.Text := edFrom.Text;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TMailDialog.FillServer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  AtPos: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Int32</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Server: </span><span style="color:#0000FF;--shiki-dark:#569CD6">String</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (OriginalServer = edOutServer.Text) and (OriginalFrom &#x3C;> edFrom.Text) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    AtPos := Pos(</span><span style="color:#A31515;--shiki-dark:#CE9178">'@'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, edFrom.Text);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> AtPos > </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Server := </span><span style="color:#0000FF;--shiki-dark:#569CD6">copy</span><span style="color:#000000;--shiki-dark:#D4D4D4">(edFrom.Text, AtPos + </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, Length(edFrom.Text));</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      edOutServer.Text := </span><span style="color:#A31515;--shiki-dark:#CE9178">'smtp.'</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + Server;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TMailDialog.FormCreate</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  OriginalTo := edTo.Text;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  OriginalFrom := edFrom.Text;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  OriginalServer := edOutServer.Text;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TMailDialog.ValidateFields</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Boolean</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> OriginalFrom = edFrom.Text </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ShowMessage(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Please change the ''From'' field to the user you are using to send the email'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    edFrom.SetFocus;</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> OriginalTo = edTo.Text </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ShowMessage(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Please change the ''TO'' field to the user you want to send the email'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    edTo.SetFocus;</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> OriginalServer = edOutServer.Text </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ShowMessage(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Please change the ''Outgoing Mail Server'' field to the pop3 server you will use to send the email.'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    edOutServer.SetFocus;</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TMailDialog.FillMsgBody</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  p, p0: </span><span style="color:#0000FF;--shiki-dark:#569CD6">integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  s: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //FlexCel returns both headers and body, as this is the MHTML standard. We need to separate</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //them to add headers to headers and body to body. Maybe other smtp component different from</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //indy could allow to just write the raw block.</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  s := GetMHTML;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  p0 := </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">  while</span><span style="color:#0000FF;--shiki-dark:#569CD6"> true</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> do</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    p := PosEx(</span><span style="color:#A31515;--shiki-dark:#CE9178">#13#10</span><span style="color:#000000;--shiki-dark:#D4D4D4">, s, p0);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (p &#x3C; </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">) or(p >= Length(s) - </span><span style="color:#098658;--shiki-dark:#B5CEA8">3</span><span style="color:#000000;--shiki-dark:#D4D4D4">) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Msg.Headers.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Add</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">Copy</span><span style="color:#000000;--shiki-dark:#D4D4D4">(s, p0, p - p0));</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    p0 := p + </span><span style="color:#098658;--shiki-dark:#B5CEA8">2</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> s[p0] = </span><span style="color:#A31515;--shiki-dark:#CE9178">#13</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> break</span><span style="color:#000000;--shiki-dark:#D4D4D4">; </span><span style="color:#008000;--shiki-dark:#6A9955">//double enter.</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Msg.Body.Text := </span><span style="color:#0000FF;--shiki-dark:#569CD6">copy</span><span style="color:#000000;--shiki-dark:#D4D4D4">(s, p0 + </span><span style="color:#098658;--shiki-dark:#B5CEA8">2</span><span style="color:#000000;--shiki-dark:#D4D4D4">, Length(s));</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TMailDialog.btnSendClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6"> if</span><span style="color:#0000FF;--shiki-dark:#569CD6"> not</span><span style="color:#000000;--shiki-dark:#D4D4D4"> ValidateFields </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> MessageDlg(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Now we will try to send the email using the server '''</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + edOutServer.Text +</span></span>
<span class="line"><span style="color:#A31515;--shiki-dark:#CE9178">     ''''</span><span style="color:#000000;--shiki-dark:#D4D4D4">#</span><span style="color:#098658;--shiki-dark:#B5CEA8">$000A</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + </span><span style="color:#A31515;--shiki-dark:#CE9178">'Note that this is a very simple implementation, and it might not work if the SMTP server needs to login. GMail accounts should work.'</span><span style="color:#000000;--shiki-dark:#D4D4D4">,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">     mtInformation,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">     [mbOk, mbCancel], </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">) &#x3C;> mrOK </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Msg.Clear;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Msg.NoEncode := </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Msg.Headers.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Add</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#A31515;--shiki-dark:#CE9178">'From: '</span><span style="color:#000000;--shiki-dark:#D4D4D4"> +  Trim(edFrom.Text));</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Msg.Recipients.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Add</span><span style="color:#000000;--shiki-dark:#D4D4D4">.Text := Trim(edTo.Text);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Msg.Headers.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Add</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Subject: '</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + Trim(edSubject.Text));</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FillMsgBody;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Mailer.Host := Trim(edOutServer.Text);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> cbUseTLS.Checked </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Mailer.Port := StrToInt(Trim(edPort.Text));</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Mailer.Username := Trim(edUserName.Text);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Mailer.Password := Trim(edPassword.Text);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Mailer.UseTLS := TIdUseTLS.utUseExplicitTLS;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  else</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Mailer.Port := </span><span style="color:#098658;--shiki-dark:#B5CEA8">25</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Mailer.Username := </span><span style="color:#A31515;--shiki-dark:#CE9178">''</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Mailer.Password := </span><span style="color:#A31515;--shiki-dark:#CE9178">''</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Mailer.UseTLS := TIdUseTLS.utNoTLSSupport;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Mailer.Connect;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Mailer.Send(Msg);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Mailer.Disconnect;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  except</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    on</span><span style="color:#000000;--shiki-dark:#D4D4D4"> ex: Exception </span><span style="color:#AF00DB;--shiki-dark:#C586C0">do</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        ShowMessage(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Error trying to send the message: '</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + ex.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Message</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">        exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ShowMessage(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Message has been sent. Please verify your JUNK folder or any filters, since it might be filtered as spam'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ModalResult := mrOk;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span></span>
<span class="line"></span>
<span class="line"></span></code></pre>


