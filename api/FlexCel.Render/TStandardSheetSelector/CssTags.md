---
uid: TStandardSheetSelector.CssTags
description: TStandardSheetSelector.CssTags
---

# TStandardSheetSelector.CssTags Property

This property has a list of Macros that you can use in the CSS definitions\. You can reference this value in the CSS properties by using \<\#variable>

For example, you could set a Macro "Mycolor" with CssTags\.Add\("mycolor", "red"\); and then define a CssProperty: CssWhenTop\.Main = "background\-color:\<\#mycolor>";


This method by default contains the following Macros:
* width: Width of the selector when it is on the right or on the left\.
* bordercolor: Color for the borders\.
* pagecolor: Color of the page\. This is normally white, and will be used in the color of the active tab, so it blends with the page background\.
* activetabfg: Color for the text in the active tab\. The default is black\.
* unselectedtabbg: Color for the background of the unselected tabs\. The default is gray, so the active tab stands out\.
* unselectedtabfg: Color for the text in the unselected tabs\.
* hoverbg: Color for the unselected tab when you hover the mouse over it\.
* hoverfg: Color for the text of the unselected tab when you hover the mouse over it\.




You can modify those Macros or add your own definitions here and use them when defining your CSS\.

**Note that the variables are not case sensitive\. You can write them in any combination of lowercase and uppercase\.**

## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TStandardSheetSelector/index.md">TStandardSheetSelector</a>.CssTags: TFDictionary&lt;string, string&gt;</code></pre>

## See also

* [TStandardSheetSelector](../TStandardSheetSelector/index.md)

