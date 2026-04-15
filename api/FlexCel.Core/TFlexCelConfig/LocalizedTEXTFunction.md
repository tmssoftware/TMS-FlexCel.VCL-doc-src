---
uid: TFlexCelConfig.LocalizedTEXTFunction
description: TFlexCelConfig.LocalizedTEXTFunction
---

# TFlexCelConfig.LocalizedTEXTFunction Property

The =TEXT\(\) function in Excel changes with the locale\.



Imagine you have a cell with the value "1\.23" and format the cell with a number format of "0\.00"\.
If you open the file with an English\-Localized Excel you will see "1\.23", but if you open the same file with a German\-Localized Excel, you will see "1,23" instead\. It happens automatically\.



But if you have a formula '=TEXT\(1\.23,"0\.00"\)' it will show correctly in an English\-Localized Excel, and as '123' in a German\-Localized one\. This is because the format string "0\.00" is not converted automatically to "0,00" which is what a German Excel would need\.



This makes the function TEXT\(\) useless if you need to share the file with users in others locales, and we recommend you **avoid using TEXT\(\) if possible**\. But if you can't change the spreadsheets, FlexCel offers two different behaviors for the function:

1\. If LocalizedTEXTFunction is false \(the default\), FlexCel will always expect English strings in TEXT\. You will always have to write =TEXT\(A1,"0\.00"\) in the cells, no matter the locale of your application\. This method works better if you are creating PDFs from the xlsx files, as the PDFs will always work if you write the TEXT functions in English\. The xlsx files will break if you distribute them to non\-English\-speaking countries, but there is no way to have TEXT\(\) not break one way or the other\.



2\. If LocalizedTEXTFunction is true, FlexCel will expect "0,00" if the locale is German, and "0\.00" if it is English\.
Use this mode if you are only targeting users all with the same locale, so you can write the correct xlsx files for them\.
If reading Excel files created by others with =TEXT, you might also need to set LocalizedTEXTFunction=true and set the FlexCel locale to match the locale the files where created in, in order to see the correct values\.



To avoid breaking backwards compatibility, this setting is false by default\. But you might find better to turn it on at the start of your app, so FlexCel will behave more like a localized Excel\. TEXT\(\) is still broken and you should avoid using it, but at least it will work for users with the same locale\. Note also that this is a static property and it will affect all the threads of your app\. It is recommended to change it once at the startup of the app, and not keep changing it\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TFlexCelConfig/index.md">TFlexCelConfig</a>.LocalizedTEXTFunction: Boolean</code></pre>

## See also

* [TFlexCelConfig](../TFlexCelConfig/index.md)

