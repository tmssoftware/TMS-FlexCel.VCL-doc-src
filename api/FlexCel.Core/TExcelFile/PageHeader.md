---
uid: TExcelFile.PageHeader
description: TExcelFile.PageHeader
---

# TExcelFile.PageHeader Property

Page header on the active sheet\.
**Note that this property sets the same header for the all the pages\.** In Excel 2007 or newer you can set a different header for the first page, or odd/even pages\. If you want to control these options, see [GetPageHeaderAndFooter](GetPageHeaderAndFooter.md) and [SetPageHeaderAndFooter](SetPageHeaderAndFooter.md)\.


A page header is a string that contains the text for the 3 parts of the header\.




The Left section begins with &amp;L, the Center section with &amp;C and the Right with &amp;R



For example, the text"&amp;LThis goes at the left\!&amp;CThis is centered\!&amp;RThis is right aligned" will write text to all the sections\.








This is the full list of macros you can include:




* &amp;&amp; The "&amp;" character itself
* &amp;L Start of the left section
* &amp;C Start of the centered section
* &amp;R Start of the right section
* &amp;P Current page number
* &amp;N Page count
* &amp;D Current date
* &amp;T Current time
* &amp;A Sheet name
* &amp;F File name without path
* &amp;Z File path without file name \(XP or Newer\)
* &amp;G Picture \(XP or Newer\)
* &amp;U Underlining on/off
* &amp;E Double underlining on/off
* &amp;S Strikeout on/off
* &amp;X Superscript on/off
* &amp;Y Subscript on/off
* &amp;"\<fontname>" Set new font \<fontname>
* &amp;"\<fontname>,\<fontstyle>" Set new font with specified style \<fontstyle>\. The style \<fontstyle> is in most cases one of "Regular", "Bold", "Italic", or "Bold Italic"\. But this setting is dependent on the used font, it may differ \(localized style names, or "Standard", "Oblique", \.\.\.\)\.
* &amp;\<fontheight> Set font height in points \(\<fontheight> is a decimal value\)\. If this command is followed by a plain number to be printed in the header, it will be separated from the font height with a space character\.
* &amp;K\<fontcolor> Set the font color\. Font color can be either specified as a RRGGBB hexadecimal number, like &amp;KFF0000 for red, or as a theme color with "TH\-TINT" like &amp;K08\-024\. For a theme, the first 2  digits before the "\-" sign are the number that corresponds with the [TPrimaryThemeColor](../TPrimaryThemeColor.md), and the other numbers are the tint of the theme\.





Normally, the easiest way to find out which header string you need is to create an xls file on Excel, add a header, open the file with FlexCel and take a look at the generated header \(You can use the ApiMate tool for that\)\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TExcelFile/index.md">TExcelFile</a>.PageHeader: string</code></pre>

## See also

* [TExcelFile](../TExcelFile/index.md)

