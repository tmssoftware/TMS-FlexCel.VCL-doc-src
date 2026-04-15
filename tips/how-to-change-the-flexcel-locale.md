---
uid: HowToChangeTheFlexCelLocale
---

# How to change the FlexCel locale.

Some formats in Excel change depending on the locale of your machine. We have discussed those formats more in depth in the tip about [internal numeric formats](xref:InternalNumericFormats).

 When FlexCel renders a file to pdf or other format, it needs to know how you want those locales printed. Is it dd/mm/yyyy or mm/dd/yyyy? As you would expect, if you don't do anything, FlexCel picks the locale from your machine settings. If you want to change how FlexCel renders those locale-dependent formats, the simplest way is to just change the machine settings. But sometimes you can't or don't want to change the machine locale, but still want FlexCel to render those formats as if the machine had some specific locale.


 To change the locale without changing the machine locale, you can use the FormatSettings delphi global variable or the class .

 You can change the locale in three different ways:

   1. Change the locale only for the current thread, by using SetThreadFormat or PushThreadFormat. The difference between the two methods is that PushThreadFormat will save the original locale in the thread, so you can restore it after using it by calling PushThreadFormat

   Thread format has the maximum priority: If you set the thread format, then this is what is going to be used by FlexCel, no matter what other settings you change. You can have different threads using different locales at the same time.

   2. Change the Global locale, by using SetGlobalFormat . This option will change the locale for all FlexCel threads where you didn't set an explicit thread locale. If you call SetGlobalFormat and then SetThreadFormat for a specific thread, that thread will use the locale you specify in SetThreadFormat. This method still has more priority than changing the locale of your app with the FormatSettings Delphi global variable.

   3. Change the locale of your full application by changing Delphi's [FormatSettings](http://docwiki.embarcadero.com/Libraries/en/System.SysUtils.FormatSettings) variable. This will change the locale for the full application and this will include FlexCel, unless you use methods 2 or 1 to be more specific about what FlexCel should use.

## Example:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  SaveLocale: TFlexCelFormatSettings;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls: TXlsFile;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  pdf: TFlexCelPdfExport;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  SaveLocale := TFlexCelFormatSettings.PushThreadFormat(</span><span style="color:#A31515;--shiki-dark:#CE9178">'zh-CN'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TFormatSettings.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'zh-CN'</span><span style="color:#000000;--shiki-dark:#D4D4D4">));</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls := TXlsFile.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'chinese.xlsx'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      pdf := TFlexCelPdfExport.Create(xls, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        pdf.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Export</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#A31515;--shiki-dark:#CE9178">'chinese.pdf'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        pdf.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      xls.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    TFlexCelFormatSettings.PopThreadFormat(SaveLocale);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>

