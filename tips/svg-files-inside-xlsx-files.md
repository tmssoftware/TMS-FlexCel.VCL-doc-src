---
uid: SVGFilesInsideXlsxFiles
---
# SVG files inside xlsx files.

## A little bit of history

Back in the old times of 1997, Excel would store the images inside an xls file in a handful of (at the time) standard formats:

* [PNG](https://en.wikipedia.org/wiki/Portable_Network_Graphics): Best for images with text or that required high fidelity. They use lossless compression, which meant images are preserved without modifications, but the files are also larger.

* [JPEG](https://en.wikipedia.org/wiki/JPEG): Best for photos or images where you want to compress a lot. They use lossy compression, which means files are smaller but modified slightly from the original.

* [BMP](https://en.wikipedia.org/wiki/BMP_file_format): Those were similar to PNGs, but with a big difference: they weren't compressed at all. Being uncompressed made them useless except for tiny bitmaps, but if you had small images, they could be rendered faster in a time where computers were much slower than today.

* [WMF/EMF](https://en.wikipedia.org/wiki/Windows_Metafile):  Windows Metafiles. Those are [vectorial formats](https://en.wikipedia.org/wiki/Vector_graphics), which means they scale better than bitmaps and are usually smaller. They also require you to draw them with a vector-image application, and they wouldn't work well for a photo.

* [PICT](https://en.wikipedia.org/wiki/PICT): This was the WMF equivalent for macs before OSX. They were also used to store vector images, but they were used when working in a mac instead of Windows.


Those formats provided a good set for 1997. They allowed vector and bitmap images, and the bitmaps could have lossy or lossless compression.

Let's now advance some years and go to 2007, when Excel introduced the xlsx file format. They used the opportunity to add some additional file formats to the xlsx files:

* [GIF](https://en.wikipedia.org/wiki/GIF): This file format is equivalent to PNG but has worse compression. On the upside, they allow animated images. If you've never tried it, you can add animated gifs to Excel, and they will show with a "Play" button that you can press to start the animation.

* [TIFF](https://en.wikipedia.org/wiki/TIFF). Yet another bitmap format, used as the standard for FAX machines. The one thing they add to already supported bitmap formats is the ability to have "multi-page" images. But as far as we know, Excel doesn't support multi-page tiffs and will only show the first page.


Again, a good set for the time. But if you look closely, you will find that we have five bitmap formats against only three vector formats. And one of the vector formats (PICT) has been dead for years. The other two (WMF and EMF) are essentially the same; both are Windows-only and not really good. So it became clear that Excel needed to support a more modern, cross-platform vector-image format. 

## Enter SVG

Let's advance ten years more to somewhere in 2017 when Excel added SVG support to xlsx files in an [Office-365 rolling update](https://office-watch.com/2016/svg-graphics-coming-to-office-at-long-last/).

This time the situation was different. In 2007, along with the support for tiff and gif, Excel introduced a new file format (xlsx). So it was simple to add new image formats: Old xls files would still support the old set of image formats (images would be converted to the supported formats when saving as xls), and new xlsx files would support the new set.

But SVG was introduced without a file format change. So if they just added SVG images to xlsx, this would break any existing xlsx processing tool, including any old Excel versions. The pictures would look great in the latest Excel, but if you shared the xlsx file with someone using Excel 2013, he wouldn't be able to see any.

To avoid this problem, Excel saves SVG images as both SVG *and* PNG inside the xlsx file. Old Excel versions will ignore the SVG and display the PNG, while SVG-Enabled Excels will show the SVG. Everyone is happy, and this is why old FlexCel versions will still display SVG images even when FlexCel wasn't SVG enabled.

## How FlexCel deals with SVG images

Since version 7.10, FlexCel can handle SVG images. But we had a problem: Neither of the graphic engines we use for image processing (GDI+, SKIA, etc.) can render SVG images. So if we simply added support for reading the new SVG section and ignored the PNG inside the xlsx file, we would be in a strange situation: Old, not-SVG-enabled FlexCels would be able to render xlsx files with SVG correctly (because they would display the alternate PNG), and new, SVG-enabled FlexCels would not (because they would try to render the SVG, which our graphic engines don't support).

And even if you are not using the FlexCel rendering engine,  you might be reading those images and doing something with them. If that is the case, upgrading from FlexCel 7.9 to 7.10 might break your app. Because now we start returning SVGs to it when SVG wasn't a file format that we could return and your app didn't have to support it. Even worse, SVG images can be tricky because they might use fonts not available on your machine.
So again, this might mean that a file converted to PDF completely fine in 7.9 would start rendering wrong in 7.10 because you don't have the fonts needed to display the SVG correctly.

That would be a disaster. Backward compatibility is something we care a lot about, and our idea is that upgrading to newer FlexCel versions should not break anything. You install a new FlexCel version, and that's it. Nothing that was previously working should break. Of course, we can never guarantee 100% that there will be no breaking changes, but we make our best effort to ensure you never have to worry about breaking anything when updating.

So how did 7.10 added SVG support? We made the following changes:

1. We will now read (and write back) both PNGs and SVGs when opening and saving an xlsx file. So if you open a file, modify some cells, and save it back, the file will keep the SVG image as before. FlexCel 7.9 would ignore the SVG image and only write back the PNG. Note that this applies only to xlsx files. As xls doesn't support SVG, only the PNG will be saved to xls files.

2. When you call [TExcelFile.GetImage](~/api/FlexCel.Core/TExcelFile/GetImage.md), we will still return the PNG for SVG images, ensuring that your existing code won't break. There is a new method [TExcelFile.GetImageAlternate](~/api/FlexCel.Core/TExcelFile/GetImageAlternate.md) that will work the same as GetImage for most images but will return the SVG for SVG images. It is now your choice to modify your app to call GetImageAlternate instead of GetImage if you want to handle SVG images. If you don't change anything in your code, 7.10 will keep working as 7.9 did.

3. There are new methods [TExcelFile.SetImageAlternate](~/api/FlexCel.Core/TExcelFile/SetImageAlternate.md) and [TExcelFile.AddImageAlternate](~/api/FlexCel.Core/TExcelFile/AddImageAlternate.md) which will allow you to enter SVG images via the API. Those methods require both the SVG *and* the backup PNG because FlexCel doesn't have an SVG renderer that could automatically convert the SVG to PNG. As usual, APIMate will show you how to enter an SVG image from a file that has it.

4. When rendering a file to PDF or images, FlexCel will continue to use the backing PNG image. This makes it possible to display those images even if our graphics backend doesn't support SVG and also guarantees that there won't be rendering problems due to missing fonts. For SVG and HTML export, there are new properties [TFlexCelHtmlExport.RasterizeSVGImages](~/api/FlexCel.Render/TFlexCelHtmlExport/RasterizeSVGImages.md) and [TFlexCelSvgExport.RasterizeSVGImages](~/api/FlexCel.Render/TFlexCelSvgExport/RasterizeSVGImages.md) which let you decide if you want to use the png or the SVG image for the rendered file. Those properties are false by default, which means that FlexCel will try to use the SVG images for HTML and SVG unless you change the properties.

> [!Warning]
> 
> While not breaking backwards compatibility is one of the highest things on our list, there is a potential little thing that could break here. As mentioned in point 4, when rendering to HTML or SVG, FlexCel 7.10 will now by default use the SVG, not the PNG to do the rendering. This makes sense, because if your file contains a SVG file you will likely want the SVG image to be exported to HTML or SVG. But also as mentioned, if the SVG contains fonts that are not available in every machine, this could break the new files. If you want to be 100% sure that those files will render exactly as intended even if there are missing fonts, you should set RasterizeSVGImages to true. 


> [!Note]
> 
> If adding an SVG file via the API with [TExcelFile.AddImageAlternate](~/api/FlexCel.Core/TExcelFile/AddImageAlternate.md), make sure to provide a reasonably high-resolution PNG alternate image. Very low-resolution PNGs will display ok in a modern Excel (because it will ignore it and render from the SVG), but it will display wrong anywhere else. 


> [!Note]
> 
> The property RasterizeSVGImages mentioned in this tip applies only to images stored inside the xlsx file as SVG. When exporting to HTML, FlexCel also has the ability to render the charts to fully-scalable SVG images instead of PNGs. For that, make sure to set the property [TFlexCelHtmlExport.SavedImagesFormat](~/api/FlexCel.Render/TFlexCelHtmlExport/SavedImagesFormat.md) to SVG.

