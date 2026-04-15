---
uid: TFlexCelWriter
description: TFlexCelWriter
---

# TFlexCelWriter Record

Encapsulates a generic writer\. This record converts automatically from a TStreamWriter or a TFlexCelStreamWriter, so you can use both when a FlexCel method requires a TFlexCelWriter\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TFlexCelWriter = record;</code></pre>

## Operators

|Name|Description|
|---|---|
|[Implicit Conversion](op_Implicit.md)|**Overloaded<br />**  [Implicit conversion from TStreamWriter to TFlexCelWriter](op_Implicit.md#implicit-conversion-from-tstreamwriter-to-tflexcelwriter)<br />  [Implicit conversion from TXmlStreamWriter to TFlexCelWriter](op_Implicit.md#implicit-conversion-from-txmlstreamwriter-to-tflexcelwriter)<br />|


## Examples

To use a method that takes a TFlexCelWriter as parameter with a standard Delphi TStreamWriter you would use:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ExportToHtmlWitFlexCelWriter</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> xls: TExcelFile);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Writer: TStreamWriter;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  html: TFlexCelHtmlExport;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Writer := TStreamWriter.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'myfilename.txt'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    html := TFlexCelHtmlExport.Create(xls, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    try</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">      // Note that the method expects a TFlexCelWriter,</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">      // but we can pass a TStreamWriter directly.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      html.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Export</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Writer, </span><span style="color:#A31515;--shiki-dark:#CE9178">'result.html'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      html.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Writer.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>



