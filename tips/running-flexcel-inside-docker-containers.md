---
uid: RunningFlexCelInsideDockerContainers
---

# Running FlexCel inside Docker containers

Docker containers are an excellent alternative for distributing applications that work the same anywhere. Conceptually they are similar to deploying to a Linux machine (and they share the same issues), but there is an extra problem.

## Fonts strike once again

When running FlexCel in a different Operating System, the first thing to check is that the fonts FlexCel needs to work on are available. Specifically, when inside a docker container, it might be the case that no fonts are available at all, causing SKIA to return an invalid font with no name, zero width, and zero height. FlexCel will, in most cases, catch those errors and tell you to install the fonts. But in other cases, it might not. So be aware to always check for fonts.

There are two issues with fonts:

### The "No font available at all" problem

It happens when there are zero fonts available in the OS, and the problem is common in containers. This is where SKIA returns a font with no name, and you will be informed of the issue. The problem goes away simply by having a single font installed. But having a single font installed will lead us to the next point:

### The "Some fonts aren't available" problem 

FlexCel uses the font files to calculate cell widths and heights during exporting and in other operations like autofitting. If you have a single font available to the OS, that font will be used as a substitute for any "real" font used in the Excel file. So metrics will likely be wrong.

To fix this, ** you need to have not just one generic font installed but all the required fonts instead. **


## Installing fonts in a Docker container

To install some fonts into a docker container, you must first copy them to the folder where "Dockerfile" is. Once you have them there, you can zip them and install them with the commands:

Ubuntu or Debian Container:
<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">WORKDIR</span><span style="color:#000000;--shiki-dark:#D4D4D4"> /app</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">RUN</span><span style="color:#000000;--shiki-dark:#D4D4D4"> apt-get update</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">RUN</span><span style="color:#000000;--shiki-dark:#D4D4D4"> apt-get -y install fontconfig</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">RUN</span><span style="color:#000000;--shiki-dark:#D4D4D4"> mkdir -p /usr/share/fonts/truetype/</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">COPY</span><span style="color:#000000;--shiki-dark:#D4D4D4"> ./fonts/* /usr/share/fonts/truetype/</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">RUN</span><span style="color:#000000;--shiki-dark:#D4D4D4"> fc-cache -f</span></span>
<span class="line"></span></code></pre>


Alpine-Linux Container:
<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">WORKDIR</span><span style="color:#000000;--shiki-dark:#D4D4D4"> /app</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">RUN</span><span style="color:#000000;--shiki-dark:#D4D4D4"> apk add --no-cache fontconfig</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">RUN</span><span style="color:#000000;--shiki-dark:#D4D4D4"> mkdir -p /usr/share/fonts/truetype/</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">COPY</span><span style="color:#000000;--shiki-dark:#D4D4D4"> ./fonts/* /usr/share/fonts/truetype/</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">RUN</span><span style="color:#000000;--shiki-dark:#D4D4D4"> fc-cache -f</span></span>
<span class="line"></span>
<span class="line"></span></code></pre>


Others Linux distributions will likely be similar, but might vary in the package manager they use (apk, apt-get, pacman, etc)

> [!Note]
> 
> Remember that you might need to copy multiple font files to install a single font. For example to install Arial you need to install:
>   - arial.ttf   // Normal font
>   - arialbd.ttf // Bold variant
>   - arialbi.ttf // Bold-Italic variant
>   - ariali.ttf  // Italic variant.
> 

