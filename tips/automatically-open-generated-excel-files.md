# Automatically open generated Excel files.

In the FlexCel demos we follow a common pattern: When we generate a file we ask the user where he wants to save it, and then, we offer to open the generated file in Excel.

The code is something similar to this:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#0000FF;--shiki-dark:#569CD6"> not</span><span style="color:#000000;--shiki-dark:#D4D4D4"> SaveDialog.Execute </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls.Save(SaveDialog.FileName);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> MessageDlg(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Do you want to open the generated file?'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, mtConfirmation, [mbYes, mbNo], </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">) = mrYes </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ShellExecute(</span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'open'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">PCHAR</span><span style="color:#000000;--shiki-dark:#D4D4D4">(SaveDialog.FileName), </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">, SW_SHOWNORMAL);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>


Now, if you have used OLE Automation before FlexCel, you are probably used to a different pattern: In OLE you can launch Excel, fill it with data using Automation, and then leave the file open without saving it. And while I personally think saving the file first is nicer, there might be cases where you want to emulate this behavior of just opening the file without asking the user to save it first.

The bad news is that it is not technically possible to create a file in FlexCel and have it open in Excel without saving it somewhere first. On the other side, the good news is that you can reasonably emulate the behavior and make it look to the user as if the file wasn't saved on disk first.

This trick uses [Excel templates](https://support.office.com/en-us/article/Save-a-workbook-as-a-template-58c6625a-2c0b-4446-9689-ad8baec39e1e), which have an extension **xlt** in Excel 2003 or older (equivalent to xls) and **xltx** in Excel 2007 or newer. An Excel template is similar to an xls/xlsx file, but it has two different characteristics:

1. When you open an xltx file in Excel, Excel makes a copy in memory of it, and doesn't lock the original file. This means that you can remove the template once Excel has opened it without worrying that Excel will be using it.

2. When a user presses "Save" in Excel, Excel won't save the template but show the "Save As..." dialog and let the user choose a filename for saving.

So what we are going to do is to create a temporary xltx file instead of a regular xlsx file, open it in Excel, then wait a little to make sure Excel finished loading it, and then remove the temporary file. To do so, we can use code like this:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">uses</span><span style="color:#000000;--shiki-dark:#D4D4D4"> ... IOUtils, Windows, ShellAPI, Threading, ...</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">...</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  tmpFileName: </span><span style="color:#0000FF;--shiki-dark:#569CD6">String</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">...</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  tmpFileName := TPath.GetTempPath + GuidToString(TGuid.NewGuid) + </span><span style="color:#A31515;--shiki-dark:#CE9178">'.xltx'</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls.Save(tmpFileName);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //The verb to open a Xltx template is "New", not "Open".</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //The second parameter of ShellExecute here is empty,</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //and this will use the default verb, which is also "New".</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ShellExecute(</span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">''</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">PCHAR</span><span style="color:#000000;--shiki-dark:#D4D4D4">(tmpFileName), </span><span style="color:#A31515;--shiki-dark:#CE9178">''</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">''</span><span style="color:#000000;--shiki-dark:#D4D4D4">, SW_SHOW);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TTask.Run(</span><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> begin</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    //Wait 30 seconds to delete the file, so Excel has time to open it.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Sleep(</span><span style="color:#098658;--shiki-dark:#B5CEA8">30000</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    TFile.Delete(tmpFileName);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span></code></pre>


> [!Note]
> 
> Once you use ShellExecute to open the file, you have to wait until Excel finished loading it. In the code above we wait for 30 seconds before deleting the file, but if your files are huge or the machines where Excel is installed are too slow, you might want to increase the time before you try to delete the file.


> [!Note]
> 
> When saving a file to disk, FlexCel automatically detects from the extension that it should be saved as a template, so you don't need to do any extra work. Just save the file with an xlt/x extension and it will be saved as a template. But in other cases like when saving to a stream, FlexCel can't figure out that you want to save as a template, and you will have to explicitly say so. You can tell FlexCel that the file is a template by setting the property [TExcelFile.IsXltTemplate](~/api/FlexCel.Core/TExcelFile/IsXltTemplate.md) to true.


> [!Note]
> 
> When starting the process to open the file, remember that the action needed to open the template in "template mode" is **New**, not **Open** as it is the default in most cases. For example, when you right-click in an xlsx file, "Open" is the default action:
> 
> <img alt = "open xlsx file" src = "../images/open-xlsx-file.png" width = "563" height = "101"/>
> 
> But when you right click in an xltx file, "New" is the default action:
> 
> <img alt = "open xltx file" src = "../images/open-xltx-file.png" width = "563" height = "113"/>
> 
> If you opened a template with "Open" instead of "New", it would behave like a normal xlsx file, being locked by Excel while in use.
> So in the code above, we used the default action instead of the default "Open" action. Had we called:
> 
> <pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ShellExecute(</span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'open'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">PCHAR</span><span style="color:#000000;--shiki-dark:#D4D4D4">(tmpFileName), </span><span style="color:#A31515;--shiki-dark:#CE9178">''</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">''</span><span style="color:#000000;--shiki-dark:#D4D4D4">, SW_SHOW);</span></span>
> <span class="line"></span></code></pre>
> 
> 
> Then the trick wouldn't work.

