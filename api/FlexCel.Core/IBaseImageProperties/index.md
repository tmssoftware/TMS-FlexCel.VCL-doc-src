---
uid: IBaseImageProperties
description: IBaseImageProperties
---

# IBaseImageProperties Interface

Image information, for headers and footers, normal images or objects in general\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">IBaseImageProperties = interface(IInterface);</code></pre>

## Methods

|Name|Description|
|---|---|
|[SetCropArea](SetCropArea.md)|This method will NOT copy the area\. Only internal use\.<br />|
|[Clone](Clone.md)|Returns a deep copy of the object\.<br />|


## Properties

|Name|Description|
|---|---|
|[DefaultsToLocked&#8203;Aspect&#8203;Ratio](DefaultsToLockedAspectRatio.md)|This property returns true if the shape by default locks its aspect ratio\. Images do it, comments don't\.<br />You will normally not need to use this value\.<br />|
|[FileName](FileName.md)|FileName of the image\. It sets/gets the original filename of the image before it was inserted\.<br />\(For example: c:\\image\.jpg\) It is not necessary to set this field, and when the image is not inserted from a file but pasted, Excel does not set it either\.<br />|
|[CropArea](CropArea.md)|Cropping coordinates for the Image\.<br />|
|[TransparentColor](TransparentColor.md)|Transparent Color\. [TFlxConsts.&#8203;NoTransparent&#8203;Color](../TFlxConsts/NoTransparentColor.md) \(~0L\) means no transparent color\.<br />|
|[Contrast](Contrast.md)|Contrast of the image\. [TFlxConsts.&#8203;Default&#8203;Contrast](../TFlxConsts/DefaultContrast.md) is the default Contrast\.<br />|
|[Brightness](Brightness.md)|Brightness of the image\. [TFlxConsts.&#8203;Default&#8203;Brightness](../TFlxConsts/DefaultBrightness.md) is the default Brightness\.<br />|
|[Gamma](Gamma.md)|Gamma of the image\. [TFlxConsts.&#8203;Default&#8203;Gamma](../TFlxConsts/DefaultGamma.md) is the default Gamma\.<br />|
|[Lock](Lock.md)|True if this image can't be selected when the sheet is protected\.<br />|
|[Print](Print.md)|If false, the image won't be printed\.<br />|
|[Published](Published.md)|Determines if the image should be published when sent to a server\. This only applies to charts\.<br />|
|[Disabled](Disabled.md)|If true, the object is disabled\.<br />|
|[DefaultSize](DefaultSize.md)|If true, the application is expected to choose the default size of the object\.<br />|
|[AutoFill](AutoFill.md)|If true, the object uses automatic fill style\.<br />|
|[AutoLine](AutoLine.md)|If true, the object uses automatic line style\.<br />|
|[AutoPic](AutoPic.md)|If true, size is formatted automatically by the application\.<br />|
|[Macro](Macro.md)|Macro attached to the image\.<br />|
|[PreferRelativeSize](PreferRelativeSize.md)|Specifies whether the original size of an object is saved after reformatting\.<br />If true, the original size of the object is stored and all resizing is based on a  percentage of that original size\.  Otherwise, each resizing resets the scale to 100%%\.<br />|
|[LockAspectRatio](LockAspectRatio.md)|Specifies whether the aspect ratio of a shape is locked from being edited\.<br />|
|[Grayscale](Grayscale.md)|Image should be displayed in grayscale\.<br />|
|[BiLevel](BiLevel.md)|If true, the image will display in 2 color black and white\.<br />|


