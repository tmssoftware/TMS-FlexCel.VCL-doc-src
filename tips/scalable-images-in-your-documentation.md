# Using scalable images in your documentation

When writing FlexCel documentation at tms, we often need to include document screenshots. 

In many cases, a simple screen capture will do. But in others, we'd like something that can scale with the monitor resolution, and a bitmap is not enough. In those cases, we use FlexCel to export the images as SVG (scalar vector graphics).

We will discuss two different cases here:

1. Sometimes you want to render a simple object. Like for example the chart at the top of this [blog post](https://www.tmssoftware.com/site/blog.asp?post=636)
   We created that image from the file in the [Chart API](xref:Chart_API-Delphi) example, using the following code:

      <pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">   var</span></span>
      <span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">     svg: </span><span style="color:#0000FF;--shiki-dark:#569CD6">String</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
      <span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">   ...</span></span>
      <span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">     svg := xls.RenderObjectAsSVG(-</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'@lines of code'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'Lines of code over time'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'This chart was rendered with RenderObjectAsSVG'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TEncoding.UTF8);</span></span>
      <span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">     begin</span></span>
      <span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">       TFile.WriteAllText(</span><span style="color:#A31515;--shiki-dark:#CE9178">'flexcel-lines-of-code.svg'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, svg);</span></span>
      <span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">     end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
      <span class="line"></span></code></pre>
      

2. Other times, you might want to render a part of a sheet, as we did in the [diagram at the end of this article](xref:UsingTokens).
   On those cases, we use code similar to the following:

      <pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">   var</span></span>
      <span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">     svg: TFlexCelSVGExport;</span></span>
      <span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">   ...</span></span>
      <span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">     svg := TFlexCelSVGExport.Create(xls, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
      <span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">     try</span></span>
      <span class="line"><span style="color:#008000;--shiki-dark:#6A9955">        // Set a page size that has the size of the image you want. </span></span>
      <span class="line"><span style="color:#008000;--shiki-dark:#6A9955">        // You will need to experiment a little to get the correct size.</span></span>
      <span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">       svg.PageSize := TPaperDimensions.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'custom'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">$30C</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">$12C</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
      <span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">       svg.SaveAsImage(</span></span>
      <span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">         procedure (x: TSVGExportParameters)</span></span>
      <span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">         begin</span></span>
      <span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">           x.FileName := </span><span style="color:#A31515;--shiki-dark:#CE9178">'result'</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + IntToStr(x.PageNumber) + </span><span style="color:#A31515;--shiki-dark:#CE9178">'.svg'</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
      <span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">         end</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
      <span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">     finally</span></span>
      <span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">       svg.Free;</span></span>
      <span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">     end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
      <span class="line"></span></code></pre>
      

You might change the print scaling of the xlsx file to get a smaller or bigger image.
