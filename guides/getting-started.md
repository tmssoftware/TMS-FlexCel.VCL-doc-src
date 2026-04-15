---
uid: GettingStarted
---

# Getting Started with FlexCel Studio for VCL and FireMonkey

## 0. Finding out which files you need to use

Before starting, it is good to know what functionality FlexCel has, and which units you need to use to access that functionality. Here is a list of the units you might need to use in FlexCel explaining what each unit does:

* **FlexCel.VCLSupport** / **FlexCel.FMXSupport** / **FlexCel.SKIASupport** / **FlexCel.LCLSupport**: You always need to use one of these units. Add the "VCL" version for VCL applications, the "FMX" version for Firemonkey, the "SKIA" version for Delphi Linux, and the "LCL" version for Lazarus. Add them to your main program, since they don't export any types and don't expose functionality. They just link the graphics engine to the framework you are using.

* **FlexCel.Core**: This includes the Core types used by all the other FlexCel units. You normally have to include this unit in every unit that uses FlexCel.

* **FlexCel.XlsAdapter**: This is the FlexCel xls/x engine. You need to use this unit if you are dealing with xls or xlsx files. There are very little cases where you won't need to use this unit, like when creating a pdf file by hand. But normally you will need to use it.

* **FlexCel.Render**: This is the FlexCel rendering engine, which renders the contents in an xls/x file into images, pdf, html or other similar file types. You need to use FlexCel.Render whenever you want to export an xls/x file to a different format. You also need to use this unit when autofitting rows or columns, since in order to measure how big a string in a cell is, FlexCel needs to render it to an internal image.

* **FlexCel.Pdf** This is the FlexCel Pdf Engine. Note that this is a generic pdf engine not tied to xls/x files. To convert an xls/x file to pdf, you still need to use FlexCel.Render, which is the engine that can "convert" and xls/x file into an image. You need to use FlexCel.Pdf if you are working directly with the pdf engine, or in general if you are dealing with pdf files. Even when not strictly necessary to convert an Excel file to pdf, it has enumerations and classes that might be needed to access the full pdf functionality when exporting.

*  **FlexCel.Report** This is the FlexCel reporting engine. You need to use this unit if you are doing Excel reports using the [TFlexCelReport](~/api/FlexCel.Report/TFlexCelReport/index.md) class.


## 1. Creating an Excel file with code

The simplest way to use FlexCel is to use the [TXlsFile](~/api/FlexCel.XlsAdapter/TXlsFile/index.md) class to manipulate files.


To get started, create an empty VCL application, add a button, and save it.

Now we need to add the FlexCel units to the "uses" clause. For this example we will add FlexCel.VCLSupport, [FlexCel.Core](xref:FlexCel.Core) and [FlexCel.XlsAdapter](xref:FlexCel.XlsAdapter). We will also be using System.IOUtils for the TPath object:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">uses</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">...</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  System.IOUtils,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FlexCel.VCLSupport, FlexCel.Core, FlexCel.XlsAdapter;</span></span>
<span class="line"></span></code></pre>


Then drop a button into the form, double-click it, and add the following code:



<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> CreateExcelFile</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls: TXlsFile;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //Create a new empty Excel file, with default formatting as if it was created by Excel 2019.</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //Different Excel versions can have different formatting when they create</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //an empty file, so for example</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //Excel 2003 will have a default font of Arial, and 2019 will use Calibri.</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //This format is anyway the starting format, you can change it all later.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls := TXlsFile.Create(</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TExcelFileFormat.v2019, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    //Enters a string into A1</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.SetCellValue(</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'Hello from FlexCel!'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    //Enters a number into A2.</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    //Note that xls.SetCellValue(2, 1, '7') would enter a string.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.SetCellValue(</span><span style="color:#098658;--shiki-dark:#B5CEA8">2</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">7</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    //Enter another floating point number.</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    //All numbers in Excel are floating point,</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    //so even if you enter an integer, it will be stored as double.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.SetCellValue(</span><span style="color:#098658;--shiki-dark:#B5CEA8">3</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">11.3</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    //Enters a formula into A4.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.SetCellValue(</span><span style="color:#098658;--shiki-dark:#B5CEA8">4</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TFormula.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'=Sum(A2:A3)'</span><span style="color:#000000;--shiki-dark:#D4D4D4">));</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    //Saves the file to the "Documents" folder.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.Save(TPath.Combine(TPath.GetDocumentsPath, </span><span style="color:#A31515;--shiki-dark:#CE9178">'test.xlsx'</span><span style="color:#000000;--shiki-dark:#D4D4D4">));</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TForm1.Button1Click</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  CreateExcelFile;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>


And that is it. You have just made an application that creates an Excel file. Of course we are just scratching the surface:
we will see more advanced uses later in this guide.

> [!Note]
> 
> This sample deduces the file format from the file name. If you saved as "test.**xls**", the file format would be **xls**, not xlsx.
> You can specify the file format in a parameter to the "Save" method if needed; for example when saving to streams.


## 2. Creating a more complex file with code
While creating a simple file is simple (as it should), the functionality in Excel is quite big, and it can be hard to find out the exact method to do something.
FlexCel comes with a tool that makes this simpler:

#### 2.1 Open APIMate
When you install FlexCel, it will install a tool named **APIMate**. You can access it by going to the Start Menu and searching for APIMate.



Or you can compile it from source (sources are included when you install FlexCel).

#### 2.2. Create a file in Excel with the functionality you want.
To get the best results, keep the file simple. Say you want to find out how to add an autofilter, create an empty file in FlexCel and add an autofilter. If you want to find out how to format a cell with a gradient, create a different file and format one cell with a gradient.

Using simple files will make it much easier to find the relevant code in APIMate

#### 2.3. Open the file with APIMate
APIMate will tell you the code you need to recreate the file you created in Excel with FlexCel. You can see the code as Delphi or C++.

You can keep the xls/x file open in both Excel and APIMate, modify the file in Excel, save, press "Refresh" in APIMate to see the changes.

Imagine you have this file, with a cell formatted in blue:

<img alt = "excel for apimate" src = "../images/excel-for-apimate.png" width = "378" height = "294"/>

When you open it in apimate, you should see this code which is the code you need to write in FlexCel to generate the same file:

<img alt = "apimate example" src = "../images/apimate-example.png" width = "720" height = "497"/>

Note that there is a language button in the toolbar where you can choose which language you want the code to be.

## 3. Reading a file
There is a complete example on Reading files in the documentation. But for simple reading, you can do as follows:

Add a Memo component to the form in the app you created in 1. Then add a new Button, and the following code:


<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ReadExcelFile</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> aMemo: TMemo);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls: TXlsFile;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  row, colIndex: </span><span style="color:#0000FF;--shiki-dark:#569CD6">integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  XF: </span><span style="color:#0000FF;--shiki-dark:#569CD6">integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  cell: TCellValue;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  addr: TCellAddress;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  s: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls := TXlsFile.Create(TPath.Combine(TPath.GetDocumentsPath, </span><span style="color:#A31515;--shiki-dark:#CE9178">'test.xlsx'</span><span style="color:#000000;--shiki-dark:#D4D4D4">));</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.ActiveSheetByName := </span><span style="color:#A31515;--shiki-dark:#CE9178">'Sheet1'</span><span style="color:#000000;--shiki-dark:#D4D4D4">;  </span><span style="color:#008000;--shiki-dark:#6A9955">//we'll read sheet1. We could loop over the existing sheets by using xls.SheetCount and xls.ActiveSheet</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    for</span><span style="color:#000000;--shiki-dark:#D4D4D4"> row := </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#0000FF;--shiki-dark:#569CD6"> to</span><span style="color:#000000;--shiki-dark:#D4D4D4"> xls.RowCount </span><span style="color:#AF00DB;--shiki-dark:#C586C0">do</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">      for</span><span style="color:#000000;--shiki-dark:#D4D4D4"> colIndex := </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#0000FF;--shiki-dark:#569CD6"> to</span><span style="color:#000000;--shiki-dark:#D4D4D4"> xls.ColCountInRow(row) </span><span style="color:#AF00DB;--shiki-dark:#C586C0">do</span><span style="color:#008000;--shiki-dark:#6A9955"> //Don't use xls.ColCount as it is slow: See https://doc.tmssoftware.com/flexcel/vcl/guides/performance-guide.html#avoid-calling-colcount</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        XF := -</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        cell := xls.GetCellValueIndexed(row, colIndex, XF);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        addr := TCellAddress.Create(row, xls.ColFromIndex(row, colIndex));</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        s := (</span><span style="color:#A31515;--shiki-dark:#CE9178">'Cell '</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + addr.CellRef + </span><span style="color:#A31515;--shiki-dark:#CE9178">' '</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">        if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (cell.IsEmpty) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#000000;--shiki-dark:#D4D4D4"> s := s + </span><span style="color:#A31515;--shiki-dark:#CE9178">'is empty.'</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">        else</span><span style="color:#0000FF;--shiki-dark:#569CD6"> if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (cell.IsString) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#000000;--shiki-dark:#D4D4D4">  s := s + </span><span style="color:#A31515;--shiki-dark:#CE9178">'has a string: '</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + cell.ToString</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">        else</span><span style="color:#0000FF;--shiki-dark:#569CD6"> if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (cell.IsNumber) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#000000;--shiki-dark:#D4D4D4"> s := s + </span><span style="color:#A31515;--shiki-dark:#CE9178">'has a number: '</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + FloatToStr(cell.AsNumber)</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">        else</span><span style="color:#0000FF;--shiki-dark:#569CD6"> if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (cell.IsBoolean) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#000000;--shiki-dark:#D4D4D4"> s := s + </span><span style="color:#A31515;--shiki-dark:#CE9178">'has a boolean: '</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + BoolToStr(cell.AsBoolean)</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">        else</span><span style="color:#0000FF;--shiki-dark:#569CD6"> if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (cell.IsError) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#000000;--shiki-dark:#D4D4D4"> s := s + </span><span style="color:#A31515;--shiki-dark:#CE9178">'has an error: '</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + cell.ToString</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">        else</span><span style="color:#0000FF;--shiki-dark:#569CD6"> if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (cell.IsFormula) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#000000;--shiki-dark:#D4D4D4"> s := s + </span><span style="color:#A31515;--shiki-dark:#CE9178">'has a formula: '</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + cell.AsFormula.Text</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">        else</span><span style="color:#000000;--shiki-dark:#D4D4D4"> s := s + (</span><span style="color:#A31515;--shiki-dark:#CE9178">'Error: Unknown cell type'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        aMemo.Lines.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Add</span><span style="color:#000000;--shiki-dark:#D4D4D4">(s);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TForm1.Button2Click</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ReadExcelFile(Memo1);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>




## 4. Manipulating files

APIMate will tell you about a huge number of things, like how to paint a cell in red, or how to insert an autofilter.
But there are some methods that APIMate can't tell you about, and from those the most important are the manipulating methods:

* Use [TExcelFile.InsertAndCopyRange](~/api/FlexCel.Core/TExcelFile/InsertAndCopyRange.md) for inserting rows or column or ranges of cells. Also for copying ranges or cells or full rows or full columns.
Or for inserting and copying cells/columns/rows in one operation (like pressing "Copy/Insert copied cells" in Excel).
It can also copy the cells from one sheet to the same sheet, to another sheet, or to another sheet in another file.
InsertAndCopyRange is a heavily overloaded method, and it can do many things depending on the parameters you pass to it.

* Use [TExcelFile.DeleteRange](~/api/FlexCel.Core/TExcelFile/DeleteRange.md) to delete ranges of cells, full rows or full columns.

* Use [TExcelFile.MoveRange](~/api/FlexCel.Core/TExcelFile/MoveRange.md) to move a range, full rows or full columns from one place to another.

* Use [TExcelFile.InsertAndCopySheets](~/api/FlexCel.Core/TExcelFile/InsertAndCopySheets.md) to insert a sheet, to copy a sheet, or to insert and copy a sheet in the same operation.

* Use [TExcelFile.DeleteSheet](~/api/FlexCel.Core/TExcelFile/DeleteSheet.md) to delete a sheet.

## 5. Creating Reports

You can create Excel files with code as shown above, but FlexCel also includes a reporting engine which uses Excel as the report designer.
When using reports you create a template in Excel, write some tags on it, and run the report.
FlexCel will replace those tags by the values from a database or memory.

1. Create an empty file in Excel

2. In cell A1 of the first sheet, write <#Customer.Name>. In cell B1 write <#Customer.Address>

3. In the ribbon, go to "Formulas" tab, and press "Name manager" (In Excel for macOS or Excel 2003, go to Menu->Insert->Name->Define)

4. Create a name "__Customer__" that refers to "=Sheet1!$A$1".
The name is case insensitive, you can write it in any mix of upper and lower case letters.
It needs to start with two underscores ("\_") and end with two underscores too. We could use a single underscore for bands that don't take the full row or "I\_" or "I\_\_" for column reports instead, but this is for more advanced uses.

5. Save the file as "report.template.xlsx" in the "Documents" folder

6. Create a new Console app, save it as "CustomerReport", and paste the following code:


<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">program</span><span style="color:#000000;--shiki-dark:#D4D4D4"> CustomerReport;</span></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">{$APPTYPE CONSOLE}</span></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">{$R *.res}</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">uses</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  System.SysUtils, System.IOUtils,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Generics.Collections, Generics.Defaults,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FlexCel.VCLSupport, FlexCel.Core, FlexCel.XlsAdapter,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FlexCel.Report;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">type</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4"> TCustomer = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  private</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FAddress: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6"> public</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">   Name</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">   property</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Address</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#0000FF;--shiki-dark:#569CD6"> read</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FAddress </span><span style="color:#0000FF;--shiki-dark:#569CD6">write</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FAddress;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">   constructor</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Create</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> aName, aAddress: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6"> end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">constructor</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TCustomer.Create</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> aName, aAddress: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Name</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := aName;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FAddress := aAddress;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> CreateReport</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Customers: TObjectList&#x3C;TCustomer>;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  fr: TFlexCelReport;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Customers := TObjectList&#x3C;TCustomer>.Create;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Customers.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Add</span><span style="color:#000000;--shiki-dark:#D4D4D4">(TCustomer.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Bill'</span><span style="color:#000000;--shiki-dark:#D4D4D4">,  </span><span style="color:#A31515;--shiki-dark:#CE9178">'555 demo line'</span><span style="color:#000000;--shiki-dark:#D4D4D4">));</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Customers.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Add</span><span style="color:#000000;--shiki-dark:#D4D4D4">(TCustomer.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Joe'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'556 demo line'</span><span style="color:#000000;--shiki-dark:#D4D4D4">));</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    fr := TFlexCelReport.Create(</span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      fr.AddTable&#x3C;TCustomer>(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Customer'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, Customers);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      fr.Run(</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        TPath.Combine(TPath.GetDocumentsPath, </span><span style="color:#A31515;--shiki-dark:#CE9178">'report.template.xlsx'</span><span style="color:#000000;--shiki-dark:#D4D4D4">),</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">                      TPath.Combine(TPath.GetDocumentsPath, </span><span style="color:#A31515;--shiki-dark:#CE9178">'result.xlsx'</span><span style="color:#000000;--shiki-dark:#D4D4D4">)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      );</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      fr.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Customers.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    CreateReport;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  except</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    on</span><span style="color:#000000;--shiki-dark:#D4D4D4"> E: Exception </span><span style="color:#AF00DB;--shiki-dark:#C586C0">do</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Writeln(E.ClassName, </span><span style="color:#A31515;--shiki-dark:#CE9178">': '</span><span style="color:#000000;--shiki-dark:#D4D4D4">, E.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Message</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span></span>
<span class="line"></span></code></pre>



> [!Note]
> 
> In this example, we used a TObjectList as a datasource for the report. You can also use arrays or TDataSets as sources, or even create your own datasources. Take a
> look at the bundled examples for more information.



## 6. Exporting a file to pdf

FlexCel offers a lot of options to export to pdf, like PDF/A, exporting font subsets, signing the generated pdf documents, etc. This is all shown in the examples and documentation. But for a simple conversion between xls/x and pdf you can use the following code:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">uses</span><span style="color:#000000;--shiki-dark:#D4D4D4"> ..., FlexCel.Core, FlexCel.XlsAdapter, FlexCel.Render;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">...</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ExportToPdf</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> InFile, OutFile: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls: TXlsFile;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  pdf: TFlexCelPdfExport;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls := TXlsFile.Create(InFile);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    pdf := TFlexCelPdfExport.Create(xls, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      pdf.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Export</span><span style="color:#000000;--shiki-dark:#D4D4D4">(OutFile);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      pdf.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"></span>
<span class="line"></span>
<span class="line"></span>
<span class="line"></span>
<span class="line"></span></code></pre>



## 7. Exporting a file to html

As usual, there are too many options when exporting to html to show here: Exporting as HTML 3.2, HTML 4 or HTML 5, embedding images or css, exporting each sheet as a tab and a big long list of etc. And as usual, you can find all the options in the documentation and examples.

For this getting started guide, we will show how to do an export with the default options of the active sheet.

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">uses</span><span style="color:#000000;--shiki-dark:#D4D4D4"> ..., FlexCel.Core, FlexCel.XlsAdapter, FlexCel.Render;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">...</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ExportToHtml</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> InFile, OutFile: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls: TXlsFile;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  html: TFlexCelHtmlExport;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls := TXlsFile.Create(InFile);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    html := TFlexCelHtmlExport.Create(xls, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      html.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Export</span><span style="color:#000000;--shiki-dark:#D4D4D4">(OutFile, </span><span style="color:#A31515;--shiki-dark:#CE9178">''</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      html.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>


## 8. Browsing through the Examples

FlexCel comes with more than 50 examples of how to do specific things. You can open each demo as a standalone project, but you can also use the included "Demo Browser" (this is MainDemo.dproj) to look at them all in a single place.

You can search for specific keywords at the top right of the main screen, to locate the demos that deal with specific features. So for example if you are looking for demos which show encryption, you will write "encrypt" in the search box:

<img alt = "main demo" src = "../images/main-demo.png" width = "663" height = "363"/>

## 9. This ends this small guide, but there is much more.
 Make sure to take a look at all the other documents available here. You can use the tabs at the top of this site to read the different sections.
