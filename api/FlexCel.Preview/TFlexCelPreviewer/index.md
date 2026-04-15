---
uid: TFlexCelPreviewer
description: TFlexCelPreviewer
---

# TFlexCelPreviewer Class

Allows you to preview a file, even if the user has no printers installed\. View the demo on Custom Preview to see how it is used\.


## Syntax

**Unit:** [FlexCel.Preview](../index.md)

<pre><code class="lang-delphi hljs">TFlexCelPreviewer = class(TScrollingWinControl);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new instance of FlexCelPreview\.<br />|


## Methods

|Name|Description|
|---|---|
|[DoStartPageChanged](DoStartPageChanged.md)|Replace this event when creating a custom descendant of FlexCelPreview\.<br />|
|[DoZoomChanged](DoZoomChanged.md)|Replace this event when creating a custom descendant of FlexCelPreview\.<br />|
|[MouseDown](MouseDown.md)|Overrides the standard mousedown event to handle it\.<br />|
|[KeyDown](KeyDown.md)|Overrides the ProcessCmdKey event\.<br />|
|[CMParentFontChanged](CMParentFontChanged.md)|Overrides the OnfontChanged event\.<br />|
|[PaintWindow](PaintWindow.md)|Overrides the OnPaint event\.<br />|
|[Paint](Paint.md)|Does the actual painting\. Override this method in your own classes to modify paint behavior\.<br />|
|[Resize](Resize.md)|Overrides de OnResize method\.<br />|
|[InvalidatePreview](InvalidatePreview.md)|Invalidates the preview and forces the control to reload from the document\.<br />When the control is a Thumbnail you cannot Invalidate it, this will be done automatically when you invalidate the main view\.<br />|
|[AutofitPreviewOnce](AutofitPreviewOnce.md)|Use this method to do a single autofit\. If you want the preview to be in "autofit mode" so it keeps autofitting even if you resize the window, set [AutofitPreview](AutofitPreview.md) instead\.<br />|


## Properties

|Name|Description|
|---|---|
|[Document](Document.md)|Document to be Previewed\.<br />|
|[PageXSeparation](PageXSeparation.md)|Separation \(in display units\) between a page an the next\. Note that if [CenteredPreview](CenteredPreview.md) is true and the preview window is bigger than the page being displayed, this value has no effect\.<br />|
|[CenteredPreview](CenteredPreview.md)|When true, the preview will be drawn at the middle of the window, instead of at the left\. If true, then [PageXSeparation](PageXSeparation.md) is the minimum margin that the preview will have\.<br />|
|[PageYSeparation](PageYSeparation.md)|Separation \(in display units\) between a page an the next\.<br />|
|[EndPreviewAtLastPage](EndPreviewAtLastPage.md)|When true, the preview will stop at the last page, and if you are showing more than one page at the same time you won't be able to select the last page\. When false, FlexCelPreview will add enough space after the last page so all pages are selectable\.<br />Note that in normal cases this won't make a difference, this property only applies if zoom is so small that you can see more than one page in the preview\.<br />|
|[AutofitPreview](AutofitPreview.md)|Defines if the page will be automatically zoomed to fit in the preview\. Note that zoom will never be less than 10%% or 400%%\.<br />If you want to autofit just once, call [AutofitPreviewOnce](AutofitPreviewOnce.md) instead\.<br />|
|[StartPage](StartPage.md)|Page the preview is showing\.<br />|
|[TotalPages](TotalPages.md)|Number of pages displaying\.<br />|
|[Zoom](Zoom.md)|Zoom preview\.<br />|
|[CacheSize](CacheSize.md)|The cache size in number of pages stored at 100%% zoom\. For larger zoom actual number of pages is decreased by \(Zoom\*Zoom\)|
|[ShowThumbsPageNumber](ShowThumbsPageNumber.md)|If true, the thumbnails will display the page number\. Note that this property only affects the thumbnails, not the main preview\.<br />|
|[ThumbnailSmall](ThumbnailSmall.md)|When using this component on Thumbnail mode, set this property to another FlexCelPreview component that will hold the small Thumbnail images\.<br />|
|[ThumbnailLarge](ThumbnailLarge.md)|When using this component on Thumbnail mode, set this property to another FlexCelPreview component that will hold the large Thumbnail images\.<br />|
|[SmoothingMode](SmoothingMode.md)|This affects how the images are rendered on the screen\. Some modes will look a little blurred but with better quality\.<br />Consult the \.NET framework documentation on SmoothingMode for more information|
|[InterpolationMode](InterpolationMode.md)|This affects how the images are rendered on the screen\. Some modes will look a little blurred but with better quality\.<br />Consult the \.NET framework documentation on SmoothingMode for more information|
|[PageShadowSize](PageShadowSize.md)|Shadow size for the pages in the preview\. Set it to 0 to disable shadows\.<br />|
|[PageShadowColor](PageShadowColor.md)|Shadow color for the pages in the preview\.<br />|
|[PageBorderColor](PageBorderColor.md)|Border color for the pages in the preview\.<br />|
|[PageBorderWidth](PageBorderWidth.md)|Border width for the pages in the preview\.<br />|
|[PageBorderStyle](PageBorderStyle.md)|Border style for the pages in the preview\.<br />|
|[PageNumberBgColor](PageNumberBgColor.md)|Background color for the page numbers in the thumbnail view\.<br />|
|[PageNumberSelected&#8203;BgColor](PageNumberSelectedBgColor.md)|Background color for the selected page number in the thumbnail view\.<br />|
|[PageNumberTextColor](PageNumberTextColor.md)|Text color for the page number in the thumbnail view\.<br />|
|[PageNumberSelected&#8203;Text&#8203;Color](PageNumberSelectedTextColor.md)|Text color for the selected page number in the thumbnail view\.<br />|
|[MaxPageSize](MaxPageSize.md)|Returns the maximum height and width of a page\. Note that width and height might not be from the same page, this is the width of the widest page and the height of the tallest page\.<br />|
|[ScrollWheelOffset](ScrollWheelOffset.md)|How many lines the preview should scroll down when the user move the scroll wheel\.<br />|


## Events

|Name|Description|
|---|---|
|[OnStartPageChanged](OnStartPageChanged.md)|Fires when the starting page changes\.<br />|
|[OnZoomChanged](OnZoomChanged.md)|Fires when the Zoom changes\. \(for example, the user uses ctrl\+MouseWeel\)\.<br />|


