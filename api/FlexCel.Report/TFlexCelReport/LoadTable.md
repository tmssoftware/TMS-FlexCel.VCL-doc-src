---
uid: TFlexCelReport.LoadTable
description: TFlexCelReport.LoadTable
---

# TFlexCelReport.LoadTable Event

Fires whenever an undefined table is called, allowing to load your own datasets in demand to the report\. For more control, you might use User Tables\. Look at the example for more information\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TFlexCelReport/index.md">TFlexCelReport</a>.LoadTable: TLoadTableEventHandler</code></pre>

## Examples

If you are running a report and don't know beforehand which tables it uses, you can use the following event:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> OnLoadTable</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> sender: TObject; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> e: TLoadTableEventArgs);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //Here GetTable is a method that returns the table to insert with our data.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  (sender </span><span style="color:#0000FF;--shiki-dark:#569CD6">as</span><span style="color:#000000;--shiki-dark:#D4D4D4"> TFlexcelReport).AddTable(e.TableName, GetTable(e.TableName), TRecordCountMode.Normal, TDisposeMode.DisposeAfterRun);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>

And the code:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  flexcelReport := TFlexCelReport.Create(</span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    flexcelReport.LoadTable := OnLoadTable;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    flexcelReport.Run(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Template.xlsx'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'Result.xlsx'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    flexcelReport.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>

Instead of using fr\.AddTable for all used tables before running the report\. If you need tables on demand, you might also look at User Tables or Direct SQL\.


## See also

* [TFlexCelReport](../TFlexCelReport/index.md)

