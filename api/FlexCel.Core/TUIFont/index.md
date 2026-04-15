---
uid: TUIFont
description: TUIFont
---

# TUIFont Class

Represents a font used for drawing in a pdf/gdi\+/wpf/winrt canvas\. This class might hold resources which need disposing\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TUIFont = class(TFlexCelObject);</code></pre>

## Methods

|Name|Description|
|---|---|
|[OnFontCreating](OnFontCreating.md)|Replace this event when creating a custom descendant of TUIFont\.<br />|
|[OnFontCreated](OnFontCreated.md)|Replace this event when creating a custom descendant of TUIFont\.<br />|
|[CreateNew](CreateNew.md)|**Overloaded<br />**  [CreateNew\(string, Double\)](CreateNew.md#tuifontcreatenewstring-double)<br />  [CreateNew\(string, Double, TUIFontStyleSet\)](CreateNew.md#tuifontcreatenewstring-double-tuifontstyleset)<br />|
|[CreateFromMemory](CreateFromMemory.md)|Creates a font from the font data\. **IMPORTANT NOTE: When using GDI\+ \(default in Windows\), this method will create a FontCollection that can never be disposed until the application exits\.**<br />When using GDI\+, try not to use this method, or make sure that it is called only a couple of times since the memory for the loaded font won't be released\. On the other hand, calling this method multiple times with the same font is ok, FlexCel will cache the font and not create multiple instances\.<br />|
|[CreateFromFile](CreateFromFile.md)|Creates a font from a font file\. **IMPORTANT NOTE: When using GDI\+ \(default in Windows\), this method will create a FontCollection that can never be disposed until the application exits\.**<br />When using GDI\+, try not to use this method, or make sure that it is called only a couple of times since the memory for the loaded font won't be released\. On the other hand, calling this method multiple times with the same font is ok, FlexCel will cache the font and not create multiple instances\.<br />|
|[CreateSimilarFont](CreateSimilarFont.md)|Creates a font which is the most similar to the one you specify\. Some fonts don't have specific styles like italics or bold, if this is the case, this method will return the same font with a different style\.<br />|
|[GetHeight](GetHeight.md)|Height of the font for a given resolution\.<br />|
|[GetWidth](GetWidth.md)|Returns the width of a string in device\-independent pixels at dpi resolution when written in the current font\.<br />|
|[FontLinespacing](FontLinespacing.md)|Returns the linespacing for the font\.<br />|
|[FontDescent](FontDescent.md)|Returns the font descent\.<br />|
|[SupportsTTFTables](SupportsTTFTables.md)|Returns true if the platform supports returning a TTF table, and you can then use [GetTTFTable](GetTTFTable.md)|
|[GetTTFTable](GetTTFTable.md)|Returns a True Type table for the font, if the platform gives the functionality\. Currently supported in OSX only\.<br />To see if the platform supports returning tables, see [SupportsTTFTables](SupportsTTFTables.md)|
|[ToString](ToString.md)|Returns the font as a string|


## Properties

|Name|Description|
|---|---|
|[Name](Name.md)|Name of the font\.<br />|
|[OriginalFontName](OriginalFontName.md)|Returns the name of the font as stored in the xls/x file, and not the font name after it was replaced by one of the fonts installed in the machine where we are running\.<br />|
|[SizeInPoints](SizeInPoints.md)|Size in points of the font\.<br />|
|[Style](Style.md)|Style of the font \(bold, italics, etc\)\.<br />|
|[Italic](Italic.md)|Returns true if the font is italic\.<br />|
|[Bold](Bold.md)|Returns true if the font is bold\.<br />|


## Events

|Name|Description|
|---|---|
|[FontCreating](FontCreating.md)|Fires before a font is created\. You can customize the font properties and create a different font instead\.<br />Note that this event is static and it applies to the whole app\.<br />|
|[FontCreated](FontCreated.md)|Fires after a font has been created\. You can use this event to handle fonts that don't exist in your system and are replaced by a different font by the OS\.<br />Note that this event is static and it applies to the whole app\.<br />**Remark:** As this event fires after the font has been created, it means that if you modify it the font is created twice\.<br />It is not going to have a big impact in performance, but if possible use the [FontCreating](FontCreating.md) event instead, as it won't cause the font to be created twice\. This event has to be used only for cases where you want to override the default operating system font substitution algorithm\.<br />|


