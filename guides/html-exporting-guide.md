---
uid: HtmlExportingGuide
---
# FlexCel HTML Exporting guide

## Introduction

One of the things FlexCel allows you to do is to export your xls/x files to HTML. We do our best to create the HTML files as closely as possible to the original xls/x file, but there are some restrictions in HTML that make it not as good as a PDF export. HTML is a “Flow” format, as opposed to PDF (which is a “Fixed Page” format), and this means the browser can resize and reposition elements depending on the output medium.

With this limitation in mind, we will study now how this is done.

## Creating HTML files

You can create an html by using the **[TFlexCelHtmlExport](~/api/FlexCel.Render/TFlexCelHtmlExport/index.md)** component.


## Creating a file using FlexCelHtmlExport

[TFlexCelHtmlExport](~/api/FlexCel.Render/TFlexCelHtmlExport/index.md) is a straightforward class. You would normally set its **[TFlexCelHtmlExport.Workbook](~/api/FlexCel.Render/TFlexCelHtmlExport/Workbook.md)** property to the Excel file you want to export, and then call **[Export](~/api/FlexCel.Render/TFlexCelHtmlExport//Export.md)**, **[ExportAllVisibleSheetsAsTabs](~/api/FlexCel.Render/TFlexCelHtmlExport//ExportAllVisibleSheetsAsTabs.md)** or **[ExportAllVisibleSheetsAsOneHtmlFile](~/api/FlexCel.Render/TFlexCelHtmlExport//ExportAllVisibleSheetsAsOneHtmlFile.md)** depending on what you want to export.

As always, we will not cover those methods or the properties on FlexCelHtmlExport in detail, since they are described in the reference and it makes no sense to repeat the information here. This document is about the conceptual part of creating HTML files.

### Naming the created files

The first thing we need to note is that creating an HTML file is different from creating a PDF or other types of files in the sense that you actually create many files for a single xls/x file.

Exporting “workbook.xlsx” to PDF will return in just one file: “workbook.pdf”, but it might result in 3 files when exporting to HTML: “workbook.htm”, “workbook\_image1.png” and “workbook.css”

So we need a way to name the different generated files. By default [TFlexCelHtmlExport](~/api/FlexCel.Render/TFlexCelHtmlExport/index.md) will take the name of the main HTML file as a parameter to the export, and generate the name of the images with the following pattern:

&lt;ImagesFolder&gt;\\&lt;htmlfilenamewithoutextension&gt;\_image&lt;imagenumber&gt;.&lt;imageext&gt;

You can change this pattern, but all in all it gives a good default for images being created. You might use a GUID too as name for the generated images, by changing the **[TFlexCelHtmlExport.ImageNaming](~/api/FlexCel.Render/TFlexCelHtmlExport/ImageNaming.md)** property.

Now, you might want or need more control than this over the filenames created, and FlexCelHtmlExport gives you that with the **[GetImageInformation](~/api/FlexCel.Render/TFlexCelHtmlExport//GetImageInformation.md)** event, where you can specify exactly which filename you want for each image or even a stream for each one if you are saving for example the file to a database and not to a file system.

Remember that [GetImageInformation](~/api/FlexCel.Render/TFlexCelHtmlExport//GetImageInformation.md) will be called for every image in the Excel file, even if they are not real images. For example, a chart will be rendered as an image, and so it will throw an OnGetImageInformation event. Also, if you have vertical text and the [TFlexCelHtmlExport.VerticalTextAsImages](~/api/FlexCel.Render/TFlexCelHtmlExport/VerticalTextAsImages.md) property is true, then this event will also be called when creating the images with the vertical text.

> [!Tip]
> 
> When exporting to HTML5, you might choose to embed the images inside the files so there are no extra files generated.
> 
> This is not a good idea for big images, but it can help to avoid the naming issues if your images are light.
> 
> You can export to HTML5 by setting the [TFlexCelHtmlExport.HtmlVersion](~/api/FlexCel.Render/TFlexCelHtmlExport/HtmlVersion.md) property to [THtmlVersion](~/api/FlexCel.Core/THtmlVersion.md).Html_5
> and you can control which images to embed with the [TFlexCelHtmlExport.EmbedImages](~/api/FlexCel.Render/TFlexCelHtmlExport/EmbedImages.md) property.


> [!Tip]
> 
> If you prefer not to use HTML 5 but still would like to embed the images, for example to send the file by email, FlexCel can also export to MHTML which is a format that supports embedding the images.


**CSS** files are another place where you might create extra files. The HTML standard allows embedding the CSS files inside the generated HTML or using an external stylesheet, and so does FlexCelHtmlExport. If you decide to go for an external stylesheet, you need to tell FlexCelHtmlExport where to place it, by providing a **[ICssInformation](~/api/FlexCel.Render/ICssInformation/index.md)** class or a CSS filename to the export methods.

### Embedding the generated HTML inside your own pages

Another thing you that is different in generating HTML from other file formats, is that you might want only a part of the html file and not all of it. For example, imagine you want to embed an Excel file inside your existing company page. You will not want the whole html file (since embedding &lt;html&gt; tags inside other &lt;html&gt; tags is not valid HTML), but only the part between the &lt;body&gt; tags. And you will want to have the &lt;head&gt; part of the file in a separated place, so you can merge it with the &lt;head&gt; tags in your site.

With FlexCelHtmlExport, you can use the **[PartialExportAdd](~/api/FlexCel.Render/TFlexCelHtmlExport//PartialExportAdd.md)** method and the **[TPartialExportState](~/api/FlexCel.Render/TPartialExportState/index.md)** class for this.

You start by creating a new TPartialExportState instance, where FlexCel will store all the information it needs to create your files.

Then, you call [TFlexCelHtmlExport.PartialExportAdd](~/api/FlexCel.Render/TFlexCelHtmlExport/PartialExportAdd.md) for each sheet or file you want to add to the HTML file, using the same TPartialExportState instance as parameter.

Once you have added all the sheets and files you want, you can use the methods in TPartialExportState to get the individual parts of the HTML file.


## Customizing the generated HTML

### General Customization

Customization is a very important part of creating HTML files, since differently from xls/x or pdf files, HTML files usually have to be integrated with an existing site. This means the style of the generated pages must match the general look and feel of the whole website, and we tried not to cut any corners in letting you do so.

### Customizing the raw HTML

There is one property, **[TFlexCelHtmlExport.ExtraInfo](~/api/FlexCel.Render/TFlexCelHtmlExport/ExtraInfo.md)** where you can add extra HTML in different parts of the document. For example, you can use this property to add META tags to your file including the keywords for searching.

### Customizing the Sheet Selector

When exporting a workbook to different HTML files we offer three ways in which you can customize the tabs that represent each sheet:

1. You can get basic customization of colors and properties by changing the [TStandardSheetSelector.CssTags](~/api/FlexCel.Render/TStandardSheetSelector/CssTags.md) property in the [TStandardSheetSelector](~/api/FlexCel.Render/TStandardSheetSelector/index.md) class.

   [TStandardSheetSelector.CssTags](~/api/FlexCel.Render/TStandardSheetSelector/CssTags.md) is a collection of macros that will be replaced in the style definition of the Selector, allowing to change the width of the selector (when placed at the right or at the top, the background color, etc). There is detailed information on the available properties you can change in the [TStandardSheetSelector.CssTags](~/api/FlexCel.Render/TStandardSheetSelector/CssTags.md) reference.

2. If the basic customization is not enough, you can completely redefine the css properties in a TStandardSheetSelector class. There is a general property for the styles that apply to all the position in the selector ([TStandardSheetSelector.CssGeneral](~/api/FlexCel.Render/TStandardSheetSelector/CssGeneral.md)) and then customized properties for all the other positions.

   For example, you could set border black for all [TStandardSheetSelector.CssTags](~/api/FlexCel.Render/TStandardSheetSelector/CssTags.md) with CssGeneral style, and then redefine the border as blue when the tab is on the left by using the [TStandardSheetSelector.CssWhenLeft](~/api/FlexCel.Render/TStandardSheetSelector/CssWhenLeft.md) property.

   You can use the built-in macros when defining your CSS properties and you can even define your own. For example, you could define:

   [TStandardSheetSelector.CssWhenLeft](~/api/FlexCel.Render/TStandardSheetSelector/CssWhenLeft.md).[Main](~/api/FlexCel.Render/TStandardSheetSelectorStyles//Main.md) := 'float: left; width: &lt;\#width&gt;';

   And then set

   [TStandardSheetSelector.CssTags](~/api/FlexCel.Render/TStandardSheetSelector/CssTags.md) \["width"\] := "100px"

   As explained, you can even **define your own macros**. For example you could use

   [TStandardSheetSelector.CssWhenLeft](~/api/FlexCel.Render/TStandardSheetSelector/CssWhenLeft.md).[Main](~/api/FlexCel.Render/TStandardSheetSelectorStyles//Main.md) := 'float: &lt;\#floatpos&gt;;'";

   And then add “floatpos” to the [CssTags](~/api/FlexCel.Render/TStandardSheetSelector//CssTags.md) array. This way you will later be able to change your own styles by replacing the macro values. The syntax for using a macro in a CSS definition is “&lt;\#macroname&gt;”, and then you need to add it to the CssTags array.

3. Normally methods 1. and 2. should be enough to handle most needs, but if you need a completely new way to display your tags, you can just define your own SheetSelector by deriving it from the class [TSheetSelector](~/api/FlexCel.Render/TSheetSelector/index.md). You will need to override the abstract methods in this class to provide the behavior you need. In fact, this is the way [TStandardSheetSelector](~/api/FlexCel.Render/TStandardSheetSelector/index.md) is defined, and you can look at its code when creating your own SheetSelector class.

### Customizing the Fonts

Fonts used in the HTML file are the same that the ones used in the xls/x file, and this might bring some compatibility issues if you expect your file to be shown in a website where it can be opened by people all over the world.

So it is recommended that you stick to standard fonts, like Arial or Times New Roman on the xls/x files you want to export. But if the files already exist and have non standard fonts, you can use the [TFlexCelHtmlExport.HtmlFont](~/api/FlexCel.Render/TFlexCelHtmlExport/HtmlFont.md) event to convert the fonts to standard typefaces. You can search for an example on this in the [Export HTML](xref:Export_HTML-Delphi) demo.

> [!Important]
> 
> The quote character FlexCel uses in style tags is the single quote ('). So, if you need to quote your font names because they have spaces, use a double quote (") so the style declaration is not affected.
> 
> For example, a style declaration in FlexCel might be: style = 'font-decoration: "my font"; '
> 
> You need to use double quotes around "my font" so it does not end the style declaration.


## Export to HTML and FlexCel recalculation

Look at the notes in the **[PdfExportingGuide](xref:PdfExportingGuide#export-to-pdf-and-flexcel-recalculation)** on the recalculating issues, this applies to HTML too.

## Using Relative Hyperlinks

You can create links in Excel, both inside cells or on images, and they will be exported to html. But there is a small issue in that in Excel you can only enter absolute URLs. For example, you can enter:

“https://www.tmssoftware.com/site/flexcel.asp”, but you cannot enter just site/flexcel.asp. If you want your websites to be “site independent”, you need to replace those URLs with relative ones.

You can do this using the **[TFlexCelHtmlExport.BaseUrl](~/api/FlexCel.Render/TFlexCelHtmlExport/BaseUrl.md)** property. If for example you define”BaseUrl” to be "https://www.tmssoftware.com/", whenever a link starts with that text, the text will be removed. In our example, the link:

"https://www.tmssoftware.com/site/flexcel.asp" will be converted to

"site/flexcel.asp"

## Exporting the images as SVG

When using HTML5, FlexCel offers the option to export the images in the file as SVG instead of png/jpeg. This won't change much for standard images, but other objects like charts or autoshapes can be exported in a vectorial format instead of rasterizing them to pngs. SVG objects can also be smaller if embedded in the page.

SVG is well understood by all modern browsers, so it might be a good idea to turn SVG exporting of images on. To do it, change the [TFlexCelHtmlExport.SavedImagesFormat](~/api/FlexCel.Render/TFlexCelHtmlExport/SavedImagesFormat.md) property to [THtmlImageFormat](~/api/FlexCel.Render/THtmlImageFormat.md).Svg.
