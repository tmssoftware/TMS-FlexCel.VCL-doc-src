---
uid: TZoomOptions
description: TZoomOptions
---

# TZoomOptions Enumeration

Zoom options for a PDF destination\.


## Syntax

**Unit:** [FlexCel.Pdf](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|None|0|None, leave the zoom unchanged\.<br />|
|Fit|1|Display the page with its contents magnified just enough to fit the entire page within the window both horizontally and vertically\. If the required horizontal and vertical magnification factors are different, use the smaller of the two, centering the page within the window in the other dimension\.<br />|
|FitH|2|Display the page with the vertical coordinate top positioned at the top edge of the window and the contents of the page magnified just enough to fit the entire width of the page within the window\.<br />|
|FitV|3|Display the page with the horizontal coordinate left positioned at the left edge of the window and the contents of the page magnified just enough to fit the entire height of the page within the window\.<br />|
|Zoom|4|Display  the  page  with  the  coordinates  \(left, top\)  posi\- tioned at the upper\-left corner of the window and the contents of the page magnified by the factor zoom\. A negative value for any of the parameters left, top, or zoom specifies that the current value of that parameter is to be retained un\- changed\. A zoom value of 0 has the same meaning as a negative value\.<br />|


