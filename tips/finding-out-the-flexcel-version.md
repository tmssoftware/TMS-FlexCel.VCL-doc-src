# Finding out which FlexCel version you are using

Sometimes you want to know the exact FlexCel version you are using from inside your app, and you might also want to make sure you aren't using a trial. You can use the following code to find out:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //The FlexCelIsTrial constant in FlexCel.Core is true if this version is a trial</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FlexCelIsTrial </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#000000;--shiki-dark:#D4D4D4"> WriteLn(</span><span style="color:#A31515;--shiki-dark:#CE9178">'ERROR: This is a trial version of FlexCel!'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //The FlexCelVersion constant in FlexCel.Core contains the current version.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  WriteLn(FlexCelVersion);</span></span>
<span class="line"></span></code></pre>

