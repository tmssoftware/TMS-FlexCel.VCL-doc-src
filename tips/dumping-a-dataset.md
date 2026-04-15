# Dumping a Dataset into Excel

One question we get asked from time to time is if FlexCel has a method like “**DumpDataset**” or “**CopyFromRecordset**” (which is the actual name in OLE Automation). This method should take a dataset and dump it into a sheet. 

And the answer is no, we don’t include such a method because it would be too limiting: Normally you will have to customize how the cells are written, and you can’t do that with a single method that does the full export in one piece. So instead, we provide 2 other different solutions to the problem. 

1. FlexCel has [reports](xref:ReportsDeveloperGuide), which you can use to dump a dataset “as is”, mostly as a DumpDataSet method would, but it also lets you do the formatting.

   As an added advantage reports allow you to easily modify the resulting sheets without modifying the code at all, so even the final user can do it.  

   From reports, the most similar thing to "DumpDataset" is to create an empty spreadsheet, write **"&lt;#mydataset.\*>"** on it, save it, and then run the report against your dataset. You can find an example of this in the demos [Generic Reports](xref:Generic_Reports-Delphi) and [Generic Reports 2](xref:Generic_Reports_2-Delphi) 

   Of course those 2 demos focus in “generic” datasets which you don’t know beforehand. If you know what data you are outputting, then you can just write &lt;#dataset.field> in the cells where you want that field written, and format each field as you want. 

   Reports are explicitly designed to deal with the problem of exporting datasets into Excel, but allowing formatting. 

2. The reports in FlexCel work exclusively by calling the FlexCel API, so anything you can do in a report, you can do it directly with the API. So if for any reason you can’t or don’t want to use reports, you can use a method like this:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">uses</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  System.SysUtils, Windows,  DB, DBClient,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FlexCel.Core,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FlexCel.XlsAdapter;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> DumpDataSet</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> ds: TDataSet);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls: TXlsFile;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Row, Col: </span><span style="color:#0000FF;--shiki-dark:#569CD6">integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Fmt: TFlxFormat;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  DateXF, DateTimeXF: </span><span style="color:#0000FF;--shiki-dark:#569CD6">integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls := TXlsFile.Create(</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TExcelFileFormat.v2019, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    //Generate the formats we will be using to format dates and times.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Fmt := xls.GetDefaultFormat;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Fmt.Format := </span><span style="color:#A31515;--shiki-dark:#CE9178">'dd/mm/yyyy hh:mm'</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    DateTimeXF := xls.AddFormat(Fmt);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Fmt := xls.GetDefaultFormat;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Fmt.Format := </span><span style="color:#A31515;--shiki-dark:#CE9178">'dd/mm/yyyy'</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    DateXF := xls.AddFormat(Fmt);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    //Now loop over all records and send them to the file.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ds.First;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Row := </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    while</span><span style="color:#0000FF;--shiki-dark:#569CD6"> not</span><span style="color:#000000;--shiki-dark:#D4D4D4"> ds.Eof </span><span style="color:#AF00DB;--shiki-dark:#C586C0">do</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">      for</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Col := </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#0000FF;--shiki-dark:#569CD6"> to</span><span style="color:#000000;--shiki-dark:#D4D4D4"> ds.FieldCount </span><span style="color:#AF00DB;--shiki-dark:#C586C0">do</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">        case</span><span style="color:#000000;--shiki-dark:#D4D4D4"> ds.Fields[Col - </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">].DataType </span><span style="color:#0000FF;--shiki-dark:#569CD6">of</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">          TFieldType.ftDateTime:</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">          begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            xls.SetCellValue(Row, Col, ds.Fields[col - </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">].AsDateTime, DateTimeXF);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">          end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">          TFieldType.ftDate:</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">          begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            xls.SetCellValue(Row, Col, ds.Fields[col - </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">].AsDateTime, DateXF);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">          end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">          else</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">          begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            xls.SetCellValue(Row, Col, ds.Fields[col - </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">].Value);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">          end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">        end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      ds.Next;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Inc(Row);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.Save(</span><span style="color:#A31515;--shiki-dark:#CE9178">'test.xlsx'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>

