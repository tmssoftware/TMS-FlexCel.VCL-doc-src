---
uid: TPdfWriter.GetFontFolder
description: TPdfWriter.GetFontFolder
---

# TPdfWriter.GetFontFolder Event

Use this event if you want to provide your own font information for embedding for a particular object instance\.

For changing the font folder for the full application, use [GetFontFolderGlobal](GetFontFolderGlobal.md) instead\.
Normally FlexCel will search for fonts on \[System\]\\Fonts folder and %%localappdata%%\\Microsoft\\Windows\\Fonts\. If your fonts are in  other location, you can tell FlexCel where they are here\. If you prefer just to give FlexCel the full data on the font, you can use [GetFontData](GetFontData.md) event instead\.



Note that you can return more than one path by separating them with semicolons\. For example if you return "c:\\fonts1;c:\\fonts2" FlexCel will search both in fonts1 and fonts2\. Every folder you specify here must have at least one font\.


FlexCel will search in the folders you return here, and in \*\*all subfolders\*\* of that folders for ttf files\.



In Android, we use a "@folder" syntax to refer to assets\. So for example to specify that the fonts are in the "fonts" folder asset, return "@fonts" here\. If the fonts are in a normal folder, just return the folder\.


## Remarks

FlexCel by default won't try to scan folders if the graphics library used by FlexCel returns the TTF tables directly\. If you are using SKIA or CoreGraphics, this event might not be called\. To ensure this event is called no matter what underlying graphics engine is used, you will need to set [TFlexCelConfig.ForcePdfFontsFromDisk](../../FlexCel.Core/TFlexCelConfig/ForcePdfFontsFromDisk.md) to true\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TPdfWriter/index.md">TPdfWriter</a>.GetFontFolder: TGetFontFolderEventHandler</code></pre>

## Examples

The following code will setup a GetFontFolder event that searches for a font first in c:\\MyFonts, and if the font isn't there, it will search in the default FlexCel search path:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> LocatePDFWriterFontFolder</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> sender: TObject; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> e: TGetFontFolderEventArgs);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  e.FontPath := </span><span style="color:#A31515;--shiki-dark:#CE9178">'c:\MyFonts;'</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + e.FontPath;;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">...</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  pdf := TPdfWriter.Create;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  pdf.GetFontFolder:= LocatePDFWriterFontFolder;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">   // Note: If the font is in c:\MyFonts, you need to tell the Operating System</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">   // to search in that folder too.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  MyFont := TUIFont.CreateNew(</span><span style="color:#A31515;--shiki-dark:#CE9178">'MyFont'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">$C</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    redBrush := TUISolidBrush.CreateNew(Colors.Red);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      pdf.DrawString(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Hello'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, MyFont, redBrush, </span><span style="color:#098658;--shiki-dark:#B5CEA8">$64</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">$64</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      redBrush.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    MyFont.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    pdf.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>



## See also

* [TPdfWriter](../TPdfWriter/index.md)

