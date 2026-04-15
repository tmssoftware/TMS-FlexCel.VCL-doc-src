# Reading only the first row of a file

Sometimes you need to process a big number of files depending on their data in the first rows. If the data isn't what you want, you skip the file.

For those cases, it might make sense not to load the full file in memory, just to read the cell A1 and then close it. And FlexCel has the right tool for the job: **Virtual Mode**

Virtual mode is described in more detail in the [Performance Guide](xref:PerformanceGuide#virtual-mode), but in this tip we will just give you the code to read a file and stop reading after the first cell.

You can also find this example in the [TExcelFile.VirtualMode](~/api/FlexCel.Core/TExcelFile/VirtualMode.md) documentation.

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">type</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">TVirtualCellReader = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  public</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> OnCellRead</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> sender: TObject; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> e: TVirtualCellReadEventArgs);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">{ TVirtualCellReader }</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TVirtualCellReader.OnCellRead</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> sender: TObject;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> e: TVirtualCellReadEventArgs);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (e.Cell.Row > </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> e.Cell.Sheet &#x3C; Length(e.SheetNames) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#000000;--shiki-dark:#D4D4D4"> e.NextSheet := e.SheetNames[e.Cell.Sheet]</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    else</span><span style="color:#000000;--shiki-dark:#D4D4D4"> e.NextSheet := </span><span style="color:#A31515;--shiki-dark:#CE9178">''</span><span style="color:#000000;--shiki-dark:#D4D4D4">; </span><span style="color:#008000;--shiki-dark:#6A9955">// Stop reading the file.</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  else</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    WriteLn(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Cell: '</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TCellAddress.Create(e.SheetNames[e.Cell.Sheet - </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">], e.Cell.Row, e.Cell.Col, </span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">).CellRef);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    WriteLn(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Value: '</span><span style="color:#000000;--shiki-dark:#D4D4D4">, e.Cell.Value.ToString.ToString);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">...</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ReadFirstRowOfAllSheets</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> fileName: </span><span style="color:#0000FF;--shiki-dark:#569CD6">String</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls: TXlsFile;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  CellReader: TVirtualCellReader;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls := TXlsFile.Create;  </span><span style="color:#008000;--shiki-dark:#6A9955">//Create the object but don't open the file yet.</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    CellReader := TVirtualCellReader.Create;  </span><span style="color:#008000;--shiki-dark:#6A9955">// Create a CellReader to handle reading the cells.</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      xls.VirtualMode := </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">;  </span><span style="color:#008000;--shiki-dark:#6A9955">//Set the mode to Virtual.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      xls.VirtualCellRead:= CellReader.OnCellRead; </span><span style="color:#008000;--shiki-dark:#6A9955">//Assign the CellReader to the TXlsFile.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      xls.Open(fileName);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      CellReader.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>

