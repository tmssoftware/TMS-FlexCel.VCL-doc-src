---
uid: Recalculation_Of_Linked_Files-Delphi
description: Recalculation_Of_Linked_Files-Delphi
---


# Recalculation of linked files (Delphi)

> [!Note]
> This demo is available in your FlexCel installation at ***&lt;FlexCel Install Folder>*\\Demo\\Delphi\\Modules\\10\.API\\77\.Recalculation Of Linked Files** and also at [https:&#8203;//&#8203;github.&#8203;com/&#8203;tmssoftware/&#8203;TMS-&#8203;FlexCel.&#8203;VCL-&#8203;demos/&#8203;tree/&#8203;master/&#8203;Delphi/&#8203;Modules/&#8203;10.&#8203;API/&#8203;77.&#8203;Recalculation Of Linked Files](https://github\.com/tmssoftware/TMS\-FlexCel\.VCL\-demos/tree/master/Delphi/Modules/10\.API/77\.Recalculation%20Of%20Linked%20Files)


## Overview


FlexCel allows complete control over recalculation of linked files. In
this demo, we will show how to create 3 linked files and how to
recalculate them.

## Concepts

- How to create files with formulas that link to other files.

- There are two ways to create a workspace to calculate linked files:

  1. When you know all the files needed in advance, you just add them to
     the workspace before recalculating.

  2. If you don\'t know which files (if any) you are going to need, you
     can use an event to load them on demand. This is the approach we
     use in the [Validate Recalc](~/samples/delphi/api/validate-recalc/index.md) example, since it deals with arbitrary
     files. Whenever you know which files are needed, it is better to
     use the first method.

- **Workspaces can take a lot of memory**. Make sure you free them after recalculating, and also the XlsFiles used in it. If you
  keep the files, those files will point to the workspace even if
  you free it, and it will not be released. You can also
  Clear() the workspace before freeing it to make sure you leave
  no references to it.

## Files

### URecalculationOfLinkedFiles.pas

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">unit</span><span style="color:#000000;--shiki-dark:#D4D4D4"> URecalculationOfLinkedFiles;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">interface</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">uses</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Windows, Messages, SysUtils, Classes, Graphics, Controls, Forms,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Dialogs, StdCtrls, FlexCel.VCLSupport, FlexCel.Core, FlexCel.XlsAdapter,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ShellAPI, ExtCtrls;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">type</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TFRecalculationOfLinkedFiles = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span><span style="color:#000000;--shiki-dark:#D4D4D4">(TForm)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Panel1: TPanel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Label1: TLabel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    CellA1: TEdit;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Label2: TLabel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Label3: TLabel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Cell2: TEdit;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Label4: TLabel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Label5: TLabel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Label6: TLabel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Cell3: TEdit;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Label7: TLabel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Label8: TLabel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Label9: TLabel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Cell4: TEdit;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> CellA1Change</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  private</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> GetValue</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> s: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">): TCellValue;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> CreateFilesAndRecalculate</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FRecalculationOfLinkedFiles: TFRecalculationOfLinkedFiles;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">implementation</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">uses</span><span style="color:#000000;--shiki-dark:#D4D4D4"> IOUtils;</span></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">{$R *.dfm}</span></span>
<span class="line"></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFRecalculationOfLinkedFiles.CellA1Change</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">   //This is a very slow way to do this (recreating the full 3 files each time you type a character)</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">   //but it is the best for what we want to show. (how to create and recalculate spreadsheets)</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">   //In a real world example you would keep the created files in memory and just recalculate them</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">   //when there is a change.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  CreateFilesAndRecalculate;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFRecalculationOfLinkedFiles.CreateFilesAndRecalculate</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls1: TXlsFile;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls2: TXlsFile;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls3: TXlsFile;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Workspace: TWorkspace;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls1 := </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">; xls2 := </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">; xls3 := </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">; Workspace := </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">   //Set up the files.</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls1 := TXlsFile.Create;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls1.NewFile(</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TExcelFileFormat.v2019);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls1.SetCellValue(</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, GetValue(CellA1.Text));</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls1.SetCellValue(</span><span style="color:#098658;--shiki-dark:#B5CEA8">2</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TFormula.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'=[Third File.xls]Sheet1!A1 + 7'</span><span style="color:#000000;--shiki-dark:#D4D4D4">));</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls2 := TXlsFile.Create;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls2.NewFile(</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TExcelFileFormat.v2019);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls2.SetCellValue(</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TFormula.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'=[First File.xls]Sheet1!A1 * 2'</span><span style="color:#000000;--shiki-dark:#D4D4D4">));</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls3 := TXlsFile.Create;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls3.NewFile(</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TExcelFileFormat.v2019);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls3.SetCellValue(</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TFormula.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'=[Second File.xls]Sheet1!A1 * 5'</span><span style="color:#000000;--shiki-dark:#D4D4D4">));</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">     //Create a workspace to recalculate them.</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">     //In this case, as we know what files we need in advance, we will just add them to the workspace</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">     //For an example on how to load files on demand, take a look at the chart example in this demo.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Workspace := TWorkspace.Create;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Workspace.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Add</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#A31515;--shiki-dark:#CE9178">'First File.xls'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, xls1);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Workspace.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Add</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Second File.xls'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, xls2);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Workspace.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Add</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Third File.xls'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, xls3);</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">     //Now that the workspace is set, we can recalculate. We could recalc() in the Workspace object or in any of the files in it.</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">     //The effect is the same, all files will be recalculated.</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">     //DO NOT RECALCULATE EVERY FILE. EACH TIME YOU CALCULATE ONE, YOU ARE CALCULATING THEM ALL.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls1.Recalc;</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">     //Ok, now it is time to show the results.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Cell2.Text := xls2.GetCellValue(</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">).AsFormula.FormulaResult.ToString;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Cell3.Text := xls3.GetCellValue(</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">).AsFormula.FormulaResult.ToString;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Cell4.Text := xls1.GetCellValue(</span><span style="color:#098658;--shiki-dark:#B5CEA8">2</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">).AsFormula.FormulaResult.ToString;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    //In tnis example, the workspace doesn't own the TXlsFiles, so we need to free them all.</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls1.Free;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls2.Free;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls3.Free;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Workspace.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">/// &#x3C;summary></span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">/// This method will try to convert a text to a string, and if not possible, return the text.</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">/// &#x3C;/summary></span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">/// &#x3C;param name="s">&#x3C;/param></span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">/// &#x3C;returns>&#x3C;/returns></span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFRecalculationOfLinkedFiles.GetValue</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> s: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">): TCellValue;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  R: </span><span style="color:#0000FF;--shiki-dark:#569CD6">double</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> TryStrToFloat(s, R) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">(R);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := s;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span></span>
<span class="line"></span>
<span class="line"></span></code></pre>


