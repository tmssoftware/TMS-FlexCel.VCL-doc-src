---
uid: LocalizedMonthNames
---


# Localized Month Names

Month names can be more complex than what they look like. 

A simple example:
In Excel, let's write the date "1930-07-18" and let's format it in a Spanish "dd-MMM-yyyy" format:

<img alt = "spanish date with dot" src = "../images/spanish-date-with-dot.png" width = "620" height = "450"/>

As you can see, it uses a dot after the month abbreviation ("jul." instead of "jul"). This is because [Abbreviations must always be followed by a full stop](https://ihdemu.com/en/abbreviations-in-spanish/#:~:text=Abbreviations%20must%20always%20be%20followed,full%20stop)

It makes sense. We native Spanish speakers have always known that abbreviations end in dots. 

But just for fun, let's open this same file we just created in Excel 2007, Windows 7:

<img alt = "spanish date without dot" src = "../images/spanish-date-without-dot.png" width = "363" height = "173"/>

It makes sense, too. While we write dots after abbreviations, it is not common to write dots after abbreviated month names. Maybe because we usually write the [Código trilítero](https://www.wikilengua.org/index.php/Abreviaciones_en_fechas), not the abbreviation. 
So, we can conclude that, initially, the people coding Excel used the "Código trilítero," but then they realized it was wrong and switched to the abbreviation. 

But now, let's look at the .NET world. Let's try this program:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">using</span><span style="color:#267F99;--shiki-dark:#4EC9B0"> System</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">using</span><span style="color:#267F99;--shiki-dark:#4EC9B0"> System</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span><span style="color:#267F99;--shiki-dark:#4EC9B0">Globalization</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">                    </span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">public</span><span style="color:#0000FF;--shiki-dark:#569CD6"> class</span><span style="color:#267F99;--shiki-dark:#4EC9B0"> Program</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">{</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    public</span><span style="color:#0000FF;--shiki-dark:#569CD6"> static</span><span style="color:#0000FF;--shiki-dark:#569CD6"> void</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Main</span><span style="color:#000000;--shiki-dark:#D4D4D4">()</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    {</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">        var</span><span style="color:#001080;--shiki-dark:#9CDCFE"> Culture</span><span style="color:#000000;--shiki-dark:#D4D4D4"> = </span><span style="color:#001080;--shiki-dark:#9CDCFE">CultureInfo</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span><span style="color:#795E26;--shiki-dark:#DCDCAA">CreateSpecificCulture</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#A31515;--shiki-dark:#CE9178">"es-ES"</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#001080;--shiki-dark:#9CDCFE">        Console</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span><span style="color:#795E26;--shiki-dark:#DCDCAA">WriteLine</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">new</span><span style="color:#267F99;--shiki-dark:#4EC9B0"> DateTime</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#098658;--shiki-dark:#B5CEA8">1930</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">7</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">18</span><span style="color:#000000;--shiki-dark:#D4D4D4">).</span><span style="color:#795E26;--shiki-dark:#DCDCAA">ToString</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#A31515;--shiki-dark:#CE9178">"dd/MMM/yy"</span><span style="color:#000000;--shiki-dark:#D4D4D4">));</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    }</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">}</span></span>
<span class="line"></span></code></pre>

If we compile it with .NET 4.8, we will get `18/Jul/30`. No dot, and the "J" in "Julio" is uppercase. What can I say? The whole thing is starting to look crazy. But we shouldn't surrender so soon. Let's change our framework to .NET 8 on the same machine and try again. And now we get "18/jul./30". So they went the reverse route as Excel/Windows, they started with the Código trilítero and then switched to abbreviations.

And Delphi has its own set of cases where it doesn't show the same as Excel (or .NET). Everyone does as they please here.

I could keep writing for hours: we've just made an example with the fourth most spoken language in the world and a language with a [Royal Academy](https://www.rae.es) that ensures it has clear rules. If we use languages with no-so-clear rules, differences start to grow bigger. And we only tried Microsoft Windows here; if we add other OSs, it gets even worse. 

There are combinations where it uses "July" instead of "Jul" as the "July abbreviation," but only for "en-AU," not "en-EN." Don't Australians abbreviate July? I don't know, and it looks like nobody does. 

There are also [Genitive Month Names](https://learn.microsoft.com/en-us/dotnet/api/system.globalization.datetimeformatinfo.monthgenitivenames) and even [Abbreviated Genitive Month Names](https://learn.microsoft.com/en-us/dotnet/api/system.globalization.datetimeformatinfo.abbreviatedmonthgenitivenames). .NET 4 will never use Genitive Month Names, .NET 8 will use them if you have a format string like "dd/MMM/yyyy", but not if you have "MMM" alone. Excel has its own rules (that also changed over the years) on whether to use Genitive month or standard month names. In .NET Core 5, Microsoft [switched from using the built-in Windows functions to ICU](https://learn.microsoft.com/en-us/dotnet/core/extensions/globalization-icu) even in Windows.

This is all to say that it is possible that you won't get the same abbreviated month names that you see in your Excel when you export from FlexCel. And if you see them the same, those might change when you update Windows, .NET, Delphi, or Excel.

It usually won't matter, but in some cases it might. For example, you might see "Jul" in Excel but "July" in FlexCel, and the text won't fit in the cell anymore. I advise not to use abbreviated month names and always leave some extra space in the cell so longer text can fit.

But if you need to get the same results as Excel with FlexCel, you can. 

The first thing is to set the month names  in the TFormatSettings of your app, so they look as you want them to:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">const</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  MyOwnNames: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Array</span><span style="color:#000000;--shiki-dark:#D4D4D4">[</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span><span style="color:#098658;--shiki-dark:#B5CEA8">.12</span><span style="color:#000000;--shiki-dark:#D4D4D4">] </span><span style="color:#0000FF;--shiki-dark:#569CD6">of</span><span style="color:#0000FF;--shiki-dark:#569CD6"> string</span><span style="color:#000000;--shiki-dark:#D4D4D4"> =</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">               (</span><span style="color:#A31515;--shiki-dark:#CE9178">'ENE'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'FEB'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'MAR'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'ABR'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'MAY'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'JUN'</span><span style="color:#000000;--shiki-dark:#D4D4D4">,</span></span>
<span class="line"><span style="color:#A31515;--shiki-dark:#CE9178">                'JUL'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'AGO'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'SET'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'OCT'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'NOV'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'DEC'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Locale: TFormatSettings;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  i: </span><span style="color:#0000FF;--shiki-dark:#569CD6">integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">...</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Locale := TFormatSettings.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'es-ES'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">  for</span><span style="color:#000000;--shiki-dark:#D4D4D4"> i := Low(Locale.ShortMonthNames) </span><span style="color:#0000FF;--shiki-dark:#569CD6">to</span><span style="color:#000000;--shiki-dark:#D4D4D4"> High(Locale.ShortMonthNames) </span><span style="color:#AF00DB;--shiki-dark:#C586C0">do</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Locale.ShortMonthNames[i] := MyOwnNames[i - </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">];</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TFlexCelFormatSettings.SetGlobalFormat(</span><span style="color:#A31515;--shiki-dark:#CE9178">'es-ES'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, Locale);</span></span>
<span class="line"></span></code></pre>


But this won't cover all cases. As we saw in the first screenshot, you can specify a different language for the format of a cell, even if Excel itself is using a different locale. In this case FlexCel will create that locale based in the locale code, and you need to override that too. You can use the code below to override the locale creation:


<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TMyCultureEvents = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  public</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    class</span><span style="color:#0000FF;--shiki-dark:#569CD6"> procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> CultureCreating</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> e: TCultureCreatingEventArgs);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">...</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TFlxNumberFormat.CultureCreating:= TMyCultureEvents.CultureCreating;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">...</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">class</span><span style="color:#0000FF;--shiki-dark:#569CD6"> procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TMyCultureEvents.CultureCreating</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> e: TCultureCreatingEventArgs);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">const</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  MyOwnNames: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Array</span><span style="color:#000000;--shiki-dark:#D4D4D4">[</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span><span style="color:#098658;--shiki-dark:#B5CEA8">.12</span><span style="color:#000000;--shiki-dark:#D4D4D4">] </span><span style="color:#0000FF;--shiki-dark:#569CD6">of</span><span style="color:#0000FF;--shiki-dark:#569CD6"> string</span><span style="color:#000000;--shiki-dark:#D4D4D4"> =</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">               (</span><span style="color:#A31515;--shiki-dark:#CE9178">'ENE'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'FEB'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'MAR'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'ABR'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'MAY'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'JUN'</span><span style="color:#000000;--shiki-dark:#D4D4D4">,</span></span>
<span class="line"><span style="color:#A31515;--shiki-dark:#CE9178">                'JUL'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'AGO'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'SET'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'OCT'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'NOV'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'DEC'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  i: </span><span style="color:#0000FF;--shiki-dark:#569CD6">integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Locale: TFormatSettings;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  case</span><span style="color:#000000;--shiki-dark:#D4D4D4"> e.LanguageCode </span><span style="color:#0000FF;--shiki-dark:#569CD6">of</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  // see https://learn.microsoft.com/en-us/openspecs/office_standards/ms-oe376/6c085406-a698-4e12-9d4d-c3b0ee3dbc4a</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //for the language code</span></span>
<span class="line"><span style="color:#098658;--shiki-dark:#B5CEA8">  1034</span><span style="color:#000000;--shiki-dark:#D4D4D4">:</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span><span style="color:#008000;--shiki-dark:#6A9955">  //Spanish - Spain (Traditional Sort)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Locale := TFormatSettings.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'es-ES'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    for</span><span style="color:#000000;--shiki-dark:#D4D4D4"> i := Low(Locale.ShortMonthNames) </span><span style="color:#0000FF;--shiki-dark:#569CD6">to</span><span style="color:#000000;--shiki-dark:#D4D4D4"> High(Locale.ShortMonthNames) </span><span style="color:#AF00DB;--shiki-dark:#C586C0">do</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Locale.ShortMonthNames[i] := MyOwnNames[i - </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">];</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    e.Culture := Locale;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>

