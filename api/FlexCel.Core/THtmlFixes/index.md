---
uid: THtmlFixes
description: THtmlFixes
---

# THtmlFixes Record

Defines special fixes to the generated files to workaround browser bugs\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">THtmlFixes = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Equals](Equals.md)|True if both objects are equal\.<br />|
|[GetHashCode](GetHashCode.md)|Hash code for the struct\.<br />|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


## Properties

|Name|Description|
|---|---|
|[IE6Transparent&#8203;PngSupport](IE6TransparentPngSupport.md)|By default, Internet explorer does not support transparent PNGs\. Normally this is not an issue, since Excel does not use  much transparency\. But if you rely on transparent images and don't want to use gif images instead of png, you can set this property to true\. It will add special code to the HTML file to support transparent images in IE6\.<br />|
|[Outlook2007Css&#8203;Support](Outlook2007CssSupport.md)|Outlook 2007 renders HTML worse than previous versions, since it switched to the Word 2007 rendering engine instead of Internet Explorer to show HTML emails\. If you apply this fix, some code will be added to the generated HTML file to improve the display in Outlook 2007\. Other browsers will not be affected and will still render the original file\. Turn this option on if you plan to email the generated file as an HTML email or to edit them in Word 2007\. Note that the pages will not validate with the w3c validator if this option is on\.<br />|
|[WordWrapSupport](WordWrapSupport.md)|Some older browsers \(and Word 2007\) might not support the CSS white\-space tag\. In this case, if a line longer than a cell cannot be expanded to the right \(because there is data in the next cell\) it will wrap down instead of being cropped\. This fix will cut the text on this cell to the displayable characters\. If a letter was displayed by the half on the right, after applying this fix it will not display\.<br />This fix is automatically applied when [Outlook2007Css&#8203;Support](Outlook2007CssSupport.md)[...[more]](WordWrapSupport.md)|


