---
uid: Creating_Pdf_Files_With_PDF_API-Delphi
description: Creating_Pdf_Files_With_PDF_API-Delphi
---


# Creating pdf files with the PDF API (Delphi)

> [!Note]
> This demo is available in your FlexCel installation at ***&lt;FlexCel Install Folder>*\\Demo\\Delphi\\Modules\\10\.API\\A0\.Creating Pdf Files With PDF API** and also at [https:&#8203;//&#8203;github.&#8203;com/&#8203;tmssoftware/&#8203;TMS-&#8203;FlexCel.&#8203;VCL-&#8203;demos/&#8203;tree/&#8203;master/&#8203;Delphi/&#8203;Modules/&#8203;10.&#8203;API/&#8203;A0.&#8203;Creating Pdf Files With PDF API](https://github\.com/tmssoftware/TMS\-FlexCel\.VCL\-demos/tree/master/Delphi/Modules/10\.API/A0\.Creating%20Pdf%20Files%20With%20PDF%20API)


## Overview


Even when FlexCel is not a full featured PDF package, it does have a
basic PDF API that you can use to create PDF files from scratch.

## Concepts

- How to create a PDF file using FlexCel\'s internal PDF API. The API
  is very similar to GDI+, and allows you to use a PDF \"Canvas\"
  where you can draw things in. To use the API, you need to use the class [TPdfWriter](~/api/FlexCel.Pdf/TPdfWriter/index.md)

- The PDF API on FlexCel is designed to support exporting Excel
  documents to PDF using **[TFlexCelPdfExport](~/api/FlexCel.Render/TFlexCelPdfExport/index.md)**. But you can use the
  same API [TFlexCelPdfExport](~/api/FlexCel.Render/TFlexCelPdfExport/index.md) uses to create your own PDF files with
  code.

## Files

### UPDFAPI.pas

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">unit</span><span style="color:#000000;--shiki-dark:#D4D4D4"> UPDFAPI;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">interface</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">uses</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Windows, Messages, SysUtils, Classes, Graphics, Controls, Forms, UPaths,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Dialogs, StdCtrls, FlexCel.VCLSupport, FlexCel.Core, FlexCel.Pdf,</span></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">  {$if CompilerVersion >= 23.0}</span><span style="color:#000000;--shiki-dark:#D4D4D4"> System.UITypes, </span><span style="color:#811F3F;--shiki-dark:#D16969">{$IFEND}</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ShellAPI;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">type</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TFPDFAPI = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span><span style="color:#000000;--shiki-dark:#D4D4D4">(TForm)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Memo1: TMemo;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    btnCreateFile: TButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    SaveDialog: TSaveDialog;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> btnCreateFileClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  private</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> CreateFile</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> OpenFile</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FPDFAPI: TFPDFAPI;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">implementation</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">uses</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Generics.Collections;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">{$R *.dfm}</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">type</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TUIBrushes = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span><span style="color:#008000;--shiki-dark:#6A9955">  //a small class to cache the brushes and free them all.</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  private</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Brushes: TObjectDictionary&#x3C;TUIColor, TUIBrush>;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Pens: TObjectDictionary&#x3C;TUIColor, TUIPen>;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  public</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    constructor</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Create</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    destructor</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Destroy</span><span style="color:#000000;--shiki-dark:#D4D4D4">; </span><span style="color:#0000FF;--shiki-dark:#569CD6">override</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> GetBrush</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Color: TUIColor): TUIBrush;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> GetPen</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Color: TUIColor): TUIPen;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFPDFAPI.btnCreateFileClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  CreateFile;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  OpenFile;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFPDFAPI.CreateFile</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  pdf: TPdfWriter;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  fStream: TFileStream;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  f: TUIFont;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  f2: TUIFont;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  points: TArray&#x3C;TUIPointF>;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Coords: TUIRectangle;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Gradient: TUIBrush;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Img: TUIImage;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Brushes: TUIBrushes;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Underline: TUITextDecoration;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#0000FF;--shiki-dark:#569CD6"> not</span><span style="color:#000000;--shiki-dark:#D4D4D4"> SaveDialog.Execute </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Underline := TUITextDecoration.Create(TUIUnderline.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Single</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  </span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  pdf := TPdfWriter.Create;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    fStream := TFileStream.Create(SaveDialog.FileName, fmCreate);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Brushes := TUIBrushes.Create;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        pdf.Compress := </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        pdf.BeginDoc(fStream);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        pdf.YAxisGrowsDown := </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">;  </span><span style="color:#008000;--shiki-dark:#6A9955">//To keep it compatible with GDI+</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        f := TUIFont.CreateNew(</span><span style="color:#A31515;--shiki-dark:#CE9178">'times new roman'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">22.5</span><span style="color:#000000;--shiki-dark:#D4D4D4">, [TUIFontStyle.fsItalic]);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">        try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">          f2 := TUIFont.CreateNew(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Arial'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">12</span><span style="color:#000000;--shiki-dark:#D4D4D4">, [TUIFontStyle.fsItalic]);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">          try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            pdf.SaveState;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            pdf.ClipPolygon(</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">              TArray&#x3C;TUIPointF>.Create(</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">              TUIPointF.Create(</span><span style="color:#098658;--shiki-dark:#B5CEA8">50</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">50</span><span style="color:#000000;--shiki-dark:#D4D4D4">),</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">              TUIPointF.Create(</span><span style="color:#098658;--shiki-dark:#B5CEA8">180</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">50</span><span style="color:#000000;--shiki-dark:#D4D4D4">),</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">              TUIPointF.Create(</span><span style="color:#098658;--shiki-dark:#B5CEA8">50</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">250</span><span style="color:#000000;--shiki-dark:#D4D4D4">),</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">              TUIPointF.Create(</span><span style="color:#098658;--shiki-dark:#B5CEA8">50</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">50</span><span style="color:#000000;--shiki-dark:#D4D4D4">)), </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            pdf.DrawAndFillPolygon(Brushes.GetPen(Colors.Aqua), Brushes.GetBrush(Colors.BlueViolet),</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">              TArray&#x3C;TUIPointF>.Create(</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">              TUIPointF.Create(</span><span style="color:#098658;--shiki-dark:#B5CEA8">10</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">10</span><span style="color:#000000;--shiki-dark:#D4D4D4">),</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">              TUIPointF.Create(</span><span style="color:#098658;--shiki-dark:#B5CEA8">300</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">10</span><span style="color:#000000;--shiki-dark:#D4D4D4">),</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">              TUIPointF.Create(</span><span style="color:#098658;--shiki-dark:#B5CEA8">50</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">300</span><span style="color:#000000;--shiki-dark:#D4D4D4">),</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">              TUIPointF.Create(</span><span style="color:#098658;--shiki-dark:#B5CEA8">10</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">10</span><span style="color:#000000;--shiki-dark:#D4D4D4">)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">              ));</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            pdf.RestoreState;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            pdf.DrawString(</span><span style="color:#A31515;--shiki-dark:#CE9178">'This is the first line on a test of many lines.'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, f, Underline, Brushes.GetBrush(Colors.Navy), </span><span style="color:#098658;--shiki-dark:#B5CEA8">100</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">100</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            pdf.DrawString(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Some unicode: '</span><span style="color:#000000;--shiki-dark:#D4D4D4">#</span><span style="color:#098658;--shiki-dark:#B5CEA8">$0E2A</span><span style="color:#000000;--shiki-dark:#D4D4D4">#</span><span style="color:#098658;--shiki-dark:#B5CEA8">$0E27</span><span style="color:#000000;--shiki-dark:#D4D4D4">#</span><span style="color:#098658;--shiki-dark:#B5CEA8">$0E31</span><span style="color:#000000;--shiki-dark:#D4D4D4">#</span><span style="color:#098658;--shiki-dark:#B5CEA8">$0E2A</span><span style="color:#000000;--shiki-dark:#D4D4D4">#</span><span style="color:#098658;--shiki-dark:#B5CEA8">$0E14</span><span style="color:#000000;--shiki-dark:#D4D4D4">#</span><span style="color:#098658;--shiki-dark:#B5CEA8">$0E35</span><span style="color:#000000;--shiki-dark:#D4D4D4">, f, Underline, Brushes.GetBrush(Colors.ForestGreen), </span><span style="color:#098658;--shiki-dark:#B5CEA8">100</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">200</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            pdf.DrawString(</span><span style="color:#A31515;--shiki-dark:#CE9178">'More lines here!'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, f, Underline, Brushes.GetBrush(Colors.ForestGreen), </span><span style="color:#098658;--shiki-dark:#B5CEA8">200</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">300</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            pdf.DrawString(</span><span style="color:#A31515;--shiki-dark:#CE9178">'And this is the last line.'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, f, Underline, Brushes.GetBrush(Colors.Black), </span><span style="color:#098658;--shiki-dark:#B5CEA8">200</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">400</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            pdf.Properties.Author := </span><span style="color:#A31515;--shiki-dark:#CE9178">'Adri'</span><span style="color:#000000;--shiki-dark:#D4D4D4">#</span><span style="color:#098658;--shiki-dark:#B5CEA8">$00E1</span><span style="color:#A31515;--shiki-dark:#CE9178">'n'</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            pdf.Properties.Title := </span><span style="color:#A31515;--shiki-dark:#CE9178">'This is a test of FlexCel Api'</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            pdf.Properties.Keywords := </span><span style="color:#A31515;--shiki-dark:#CE9178">'test'</span><span style="color:#000000;--shiki-dark:#D4D4D4">#</span><span style="color:#098658;--shiki-dark:#B5CEA8">$000A</span><span style="color:#A31515;--shiki-dark:#CE9178">'flexcel'</span><span style="color:#000000;--shiki-dark:#D4D4D4">#</span><span style="color:#098658;--shiki-dark:#B5CEA8">$000A</span><span style="color:#A31515;--shiki-dark:#CE9178">'api'</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            pdf.NewPage;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            pdf.SaveState;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            pdf.Rotate(</span><span style="color:#098658;--shiki-dark:#B5CEA8">200</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">100</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">45</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            pdf.DrawString(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Some rotated test'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, f, Underline, Brushes.GetBrush(Colors.Black), </span><span style="color:#098658;--shiki-dark:#B5CEA8">200</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">200</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            pdf.RestoreState;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            pdf.DrawString(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Some NOT rotated text'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, f, Underline, Brushes.GetBrush(Colors.Black), </span><span style="color:#098658;--shiki-dark:#B5CEA8">200</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">200</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            pdf.DrawString(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Hello from FlexCel!'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, f2, Brushes.GetBrush(Colors.Black), </span><span style="color:#098658;--shiki-dark:#B5CEA8">200</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">50</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            points := TArray&#x3C;TUIPointF>.Create(TUIPointF.Create(</span><span style="color:#098658;--shiki-dark:#B5CEA8">200</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">100</span><span style="color:#000000;--shiki-dark:#D4D4D4">), TUIPointF.Create(</span><span style="color:#098658;--shiki-dark:#B5CEA8">200</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">50</span><span style="color:#000000;--shiki-dark:#D4D4D4">), TUIPointF.Create(</span><span style="color:#098658;--shiki-dark:#B5CEA8">500</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">50</span><span style="color:#000000;--shiki-dark:#D4D4D4">), TUIPointF.Create(</span><span style="color:#098658;--shiki-dark:#B5CEA8">700</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">100</span><span style="color:#000000;--shiki-dark:#D4D4D4">));</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            pdf.DrawLines(Brushes.GetPen(Colors.DarkOrchid), points);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            Coords := TUIRectangle.Create(</span><span style="color:#098658;--shiki-dark:#B5CEA8">100</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">300</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">100</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">100</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            Gradient := TUILinearGradientBrush.CreateNew(Coords, Colors.Red, Colors.Blue, </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">            try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">              pdf.DrawAndFillRectangle(Brushes.GetPen(Colors.Red), Gradient, </span><span style="color:#098658;--shiki-dark:#B5CEA8">100</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">300</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">100</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">100</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">            finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">              FreeAndNil(Gradient);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">            end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            pdf.DrawRectangle(Brushes.GetPen(Colors.DarkSlateBlue), </span><span style="color:#098658;--shiki-dark:#B5CEA8">100</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">300</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">50</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">50</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            pdf.DrawLine(Brushes.GetPen(Colors.Black), </span><span style="color:#098658;--shiki-dark:#B5CEA8">100</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">300</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">200</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">400</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            Img := TUIImage.FromFile(DataFolder + </span><span style="color:#A31515;--shiki-dark:#CE9178">'test.jpg'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">            try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">              pdf.DrawImage(Img, TUIRectangle.Create(</span><span style="color:#098658;--shiki-dark:#B5CEA8">200</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">300</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">200</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">150</span><span style="color:#000000;--shiki-dark:#D4D4D4">), </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">            finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">              FreeAndNil(Img);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">            end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            pdf.IntersectClipRegion(TUIRectangle.Create(</span><span style="color:#098658;--shiki-dark:#B5CEA8">100</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">100</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">50</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">50</span><span style="color:#000000;--shiki-dark:#D4D4D4">));</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            pdf.FillRectangle(Brushes.GetBrush(Colors.DarkTurquoise), </span><span style="color:#098658;--shiki-dark:#B5CEA8">100</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">100</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">100</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">100</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            pdf.EndDoc;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">          finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            FreeAndNil(f2);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">          end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">        finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">          FreeAndNil(f);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">        end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        FreeAndNil(Brushes);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      FreeAndNil(fStream);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FreeAndNil(pdf);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFPDFAPI.OpenFile</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> MessageDlg(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Do you want to open the generated file?'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, mtConfirmation, [mbYes, mbNo], </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">) = mrYes </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ShellExecute(</span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'open'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">PCHAR</span><span style="color:#000000;--shiki-dark:#D4D4D4">(SaveDialog.FileName), </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">, SW_SHOWNORMAL);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">{ TUIBrushes }</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TUIBrushes.GetBrush</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Color: TUIColor): TUIBrush;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Brushes.TryGetValue(Color, </span><span style="color:#0000FF;--shiki-dark:#569CD6">Result</span><span style="color:#000000;--shiki-dark:#D4D4D4">) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := TUISolidBrush.CreateNew(Color);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Brushes.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Add</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Color, </span><span style="color:#0000FF;--shiki-dark:#569CD6">Result</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TUIBrushes.GetPen</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Color: TUIColor): TUIPen;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Pens.TryGetValue(Color, </span><span style="color:#0000FF;--shiki-dark:#569CD6">Result</span><span style="color:#000000;--shiki-dark:#D4D4D4">) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := TUIPen.CreateNew(Color);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Pens.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Add</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Color, </span><span style="color:#0000FF;--shiki-dark:#569CD6">Result</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">constructor</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TUIBrushes.Create</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Brushes := TObjectDictionary&#x3C;TUIColor, TUIBrush>.Create([doOwnsValues]);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Pens := TObjectDictionary&#x3C;TUIColor, TUIPen>.Create([doOwnsValues]);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">destructor</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TUIBrushes.Destroy</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Pens.Free;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Brushes.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  inherited</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span></span>
<span class="line"></span>
<span class="line"></span></code></pre>


