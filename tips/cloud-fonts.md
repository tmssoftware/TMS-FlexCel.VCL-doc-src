---
uid: CloudFonts
---


# Cloud fonts

As we write this tip, Microsoft has just released a [new default font](https://medium.com/microsoft-design/a-change-of-typeface-microsofts-new-default-font-has-arrived-f200eb16718d) for all the Office applications, including Excel. And we've just released support for it, but there are some issues that we just can't fix.

A new default font is usually a headache, as the font is not likely to be available on platforms other than Windows. For that reason alone, we suggest using Calibri until the new Aptos font becomes as ubiquitous. But this time, we have another reason to recommend not switching just yet:

Unlike Calibri, Arial, or all the "classic" fonts, Aptos was delivered as a [Cloud font](https://support.microsoft.com/en-us/office/cloud-fonts-in-office-f7b009fe-037f-45ed-a556-b5fe6ede6adb). As explained in the link above, cloud fonts are available only to the Office apps, and not to Windows itself. This means that your application (and any other application in your machine) can't see them, even if you can see them in Office.

If you are creating a PDF, a workaround for FlexCel in Windows would be to add the folder "%LocalAppData%\Microsoft\FontCache\4\CloudFonts\" in the [TFlexCelPdfExport.GetFontFolder](~/api/FlexCel.Render/TFlexCelPdfExport/GetFontFolder.md) event.

But this isn't a great workaround because:

1. It will only work for PDF files. When printing, or previewing, FlexCel won't find the fonts, and they will be poorly substituted by another, probably breaking the layout of the page.
2. Even when exporting to PDF, FlexCel might sometimes ask the operating system for some font data, and the operating system will provide the wrong font. See also the [FlexCel PDF Exporting Guide](xref:PdfExportingGuide#fonts-in-windows)
3. The place of local fonts is not documented and might change: Today, it is "FontCache\4\CloudFonts," but tomorrow, it might change to "FontCache\5\CloudFonts," and your app will break. 

Given all the issues, if you really want to use Aptos (or any other cloud font) in your files, we recommend installing them locally so that all Windows apps can see them. You can find a nice step-by-step guide in how to do so at https://office-watch.com/2023/cloud-fonts-available-all-programs/

> [!Important]
> 
> At the time of this writing, the Aptos font is only available as a Cloud font, and it is not installed in Windows. It might happen that some Windows update in the future installs the font also in Windows, which would fix most of the issues of this tip. So we recommend you to open the Font Viewer in Windows, and see if the Aptos font isn't available.

