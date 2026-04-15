---
uid: FlexCelDllInit
description: FlexCelDllInit
---

# FlexCelDllInit Method

Use this method to initialize FlexCel when encapsulating it in a dll\.



Note that you don't normally need to call this method, as FlexCel is initialized automatically\. But when you are hosting FlexCel inside a dll instead of the main application you need to call this method before calling the methods in the dll\. Currently, this method will just initialize GDI\+ when running in Windows, because GDI\+ can't be initialized from the dll itself\. When you use this method, always call [FlexCelDllShutdown](FlexCelDllShutdown.md) before closing your app\.




## Syntax

**Unit:** [FlexCel.Core](index.md)

<pre><code class="lang-delphi hljs">procedure FlexCelDllInit;</code></pre>

