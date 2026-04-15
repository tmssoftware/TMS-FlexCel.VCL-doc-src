---
uid: TFlexCelPdfExport.GetFontFolder
description: TFlexCelPdfExport.GetFontFolder
---

# TFlexCelPdfExport.GetFontFolder Event

Use this event if you want to provide your own font information for embedding\.
Normally FlexCel will search for fonts on \[System\]\\Fonts folder and %%localappdata%%\\Microsoft\\Windows\\Fonts\. If your fonts are in  other location, you can tell FlexCel where they are here\. If you prefer just to give FlexCel the full data on the font, you can use [GetFontData](GetFontData.md) event instead\.



Note that this property applies only to this object\. To change the property for the full application, use [TPdfWriter.GetFontFolderGlobal](../../FlexCel.Pdf/TPdfWriter/GetFontFolderGlobal.md)

## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TFlexCelPdfExport/index.md">TFlexCelPdfExport</a>.GetFontFolder: TGetFontFolderEventHandler</code></pre>

## Examples

The following code will setup a GetFontFolder event that searches for a font first in c:\\MyFonts, and if the font isn't there, it will search in the default FlexCel search path:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> LocatePDFFontFolder</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> sender: TObject; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> e: TGetFontFolderEventArgs);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  e.FontPath := </span><span style="color:#A31515;--shiki-dark:#CE9178">'c:\MyFonts;'</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + e.FontPath;;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">...</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  pdf := TFlexCelPdfExport.Create(xls, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    pdf.GetFontFolder:= LocatePDFFontFolder;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    pdf.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Export</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#A31515;--shiki-dark:#CE9178">'result.pdf'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    pdf.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>



## See also

* [TFlexCelPdfExport](../TFlexCelPdfExport/index.md)

