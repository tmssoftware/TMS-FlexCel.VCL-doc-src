---
uid: ReplacingAFontByAnotherInAnExcelFile
---

# Replacing a font by another in an Excel file.

Sometimes you might want to replace all occurrences of a font by another inside an Excel file. Maybe the old font isn't widely available in some new platforms that you want to support, maybe there are licensing issues with the font, or maybe your company changed their corporate font and you need to change it in all existing reports.  The reason doesn't really matter. So, how do we do it?

> [!Note]
> 
> Sometimes you might want to only change the font in the resulting PDF file, not in the xls/x files. If you only care about PDF outputs, make sure also to read the [PDF exporting guide](xref:PdfExportingGuide)


## Step 1: Manually inspect the old and the new font.
Before even starting, let's make this clear: **Fonts can have different metrics**. Some fonts are very similar, like Arial and Helvetica, but some other fonts can be completely different. 

If the fonts you are replacing have similar metrics, you can skip to the next step. But if they don't, the first thing to do is to analyze how different they are.

In this example we are going to replace Calibri by Verdana, so let's write a sentence in Calibri 11pt and Verdana 11pt to see how different they are:

<img alt = "calibri11 vs verdana11" src = "../images/calibri11-vs-verdana11.png" width = "436" height = "77"/>

Oops... they are quite different. So we can't just do a "search and replace" from Calibri to Arial, without breaking the report layout. For this particular phrase, Calibri 11pt should be replaced by something like Verdana 8.5 pt:
<img alt = "calibri11 vs verdana85" src = "../images/calibri11-vs-verdana85.png" width = "366" height = "77"/>

And this means that the existing Calibri text must be reduced in size by about 0.8 to get a similar text in Verdana.

> [!Note]
> 
> 0.8 is the factor for the phrase that we tested: "The secret of getting ahead is getting started."  While it shouldn't vary too much, some phrases will be shorter or longer, depending on the metrics of every character in both fonts. We are doing no exact science here, and unless you are replacing very similar fonts like Arial by Helvetica, you must expect some layouts to break.


## Step 2: Replace the fonts.
Ok, so we now know we have to replace Calibri 11pt by Verdana 8.5pt, or more in general Calibri Npt by Verdana N\*0.8pt.

In Excel, we would have to change the fonts in every cell, and the styles, and the themes, and text inside autoshapes, and text inside charts, and so on. But luckily for us, in FlexCel it is more straightforward. There are two places we have to change: The font list and the themes. And you can do so with the code below:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls: TXlsFile;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  i: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Int32</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  fnt: TFlxFont;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Theme: ITheme;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  textFont: TThemeTextFont;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">const</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FontToReplace = </span><span style="color:#A31515;--shiki-dark:#CE9178">'Calibri'</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ReplaceWith = </span><span style="color:#A31515;--shiki-dark:#CE9178">'Verdana'</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FontFactor = </span><span style="color:#098658;--shiki-dark:#B5CEA8">0.8</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls := TXlsFile.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'original_file.xlsx'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">     //Change the fonts</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    for</span><span style="color:#000000;--shiki-dark:#D4D4D4"> i := </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#0000FF;--shiki-dark:#569CD6"> to</span><span style="color:#000000;--shiki-dark:#D4D4D4"> xls.FontCount </span><span style="color:#AF00DB;--shiki-dark:#C586C0">do</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      fnt := xls.GetFont(i);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> SameText(fnt.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Name</span><span style="color:#000000;--shiki-dark:#D4D4D4">, FontToReplace) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        fnt.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Name</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := ReplaceWith;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        fnt.Size20 := Trunc((fnt.Size20 * FontFactor));</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      xls.SetFont(i, fnt);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">     //Change the theme font</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Theme := xls.GetTheme;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Theme.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Name</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := </span><span style="color:#A31515;--shiki-dark:#CE9178">'My theme'</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Theme.Elements.FontScheme.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Name</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := </span><span style="color:#A31515;--shiki-dark:#CE9178">'My font scheme'</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    textFont := TThemeTextFont.Create(ReplaceWith, </span><span style="color:#A31515;--shiki-dark:#CE9178">''</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TPitchFamily.FIXED_PITCH__SWISS_FONT_FAMILY, FlexCel.Core.TFontCharSet.Ansi);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> SameText(Theme.Elements.FontScheme.MajorFont.Latin.Typeface, FontToReplace) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Theme.Elements.FontScheme.MajorFont.Latin := textFont;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> SameText(Theme.Elements.FontScheme.MajorFont.ComplexScript.Typeface, FontToReplace) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Theme.Elements.FontScheme.MajorFont.ComplexScript := textFont;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> SameText(Theme.Elements.FontScheme.MajorFont.EastAsian.Typeface, FontToReplace) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Theme.Elements.FontScheme.MajorFont.EastAsian := textFont;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> SameText(Theme.Elements.FontScheme.MinorFont.Latin.Typeface, FontToReplace) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Theme.Elements.FontScheme.MinorFont.Latin := textFont;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> SameText(Theme.Elements.FontScheme.MinorFont.ComplexScript.Typeface, FontToReplace) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Theme.Elements.FontScheme.MinorFont.ComplexScript := textFont;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> SameText(Theme.Elements.FontScheme.MinorFont.EastAsian.Typeface, FontToReplace) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Theme.Elements.FontScheme.MinorFont.EastAsian := textFont;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.SetTheme(Theme);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.Save(</span><span style="color:#A31515;--shiki-dark:#CE9178">'result_file.xlsx'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>

