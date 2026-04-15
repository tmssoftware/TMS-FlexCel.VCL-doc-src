---
uid: TClientAnchor
description: TClientAnchor
---

# TClientAnchor Record

Image Anchor information\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TClientAnchor = record;</code></pre>

## Fields

|Name|Description|
|---|---|
|[ChildAnchor](ChildAnchor.md)|Returns the offset on the parent system for the image, when it is grouped\.<br />For example, if the parent shape on the group is 100 px wide, and ChildAnchor has a dx of 0\.5, the image starts 50px to the right of the parent\. If the shape is not grouped  or it is the shape on top of the group, ChildAnchor is null\. When this member is not null, other values on ClientAnchor have no meaning\.<br />|


## Methods

|Name|Description|
|---|---|
|[CalcImageHeight&#8203;Internal](CalcImageHeightInternal.md)|This might be called with a workbook or a sheet\. If with a workbook, verify the sheet is the correct one\.<br />|
|[Create](Create.md)|**Overloaded<br />**  [Create](Create.md#tclientanchorcreate)<br />  [Create\(TFlxAnchorType, Integer, Integer, Integer, Integer, Integer, Integer, IRowColSize\)](Create.md#tclientanchorcreatetflxanchortype-integer-integer-integer-integer-integer-integer-irowcolsize)<br />  [Create\(TFlxAnchorType, Integer, Integer, Integer, Integer, Integer, Integer, Integer, Integer\)](Create.md#tclientanchorcreatetflxanchortype-integer-integer-integer-integer-integer-integer-integer-integer)<br />  [Create\(Boolean, TFlxAnchorType, Integer, Integer, Integer, Integer, Integer, Integer, Integer, Integer\)](Create.md#tclientanchorcreateboolean-tflxanchortype-integer-integer-integer-integer-integer-integer-integer-integer)<br />  [Create\(TFlxAnchorType, Integer, Integer, Integer, Integer, Integer, Integer, Integer, Integer, IRowColSize\)](Create.md#tclientanchorcreatetflxanchortype-integer-integer-integer-integer-integer-integer-integer-integer-irowcolsize)<br />|
|[CreateKeeping&#8203;Aspect&#8203;Ratio](CreateKeepingAspectRatio.md)|This method will create an anchor so the image keeps its aspect ratio, and it is contained inside the group of cells\.<br />If you supply negative values for Col2 or Row2, then those values will be ignored\. If you set Col2 negative, then this method will place the image between Row1 and Row2, and calculate Col2 so the image keeps its aspect ratio\.<br />Similar if you set Row2 negative\.<br />|
|[Inc](Inc.md)|Returns a COPY of the anchor with rows and cols incremented by one|
|[Dec](Dec.md)|Returns a COPY of the anchor with rows and cols decremented by one|
|[CalcImageCoords](CalcImageCoords.md)|**Overloaded<br />**  [CalcImageCoords\(Double, Double, IRowColSize\)](CalcImageCoords.md#tclientanchorcalcimagecoordsdouble-double-irowcolsize)<br />  [CalcImageCoords\(Double, Double, Double, Double, IRowColSize\)](CalcImageCoords.md#tclientanchorcalcimagecoordsdouble-double-double-double-irowcolsize)<br />|
|[CalcImageCoords&#8203;InPoints](CalcImageCoordsInPoints.md)|Calculates the width and height of the image in Points\.<br />|
|[CalcImageOrigin&#8203;InPoints](CalcImageOriginInPoints.md)|Calculates the origin of the image in Points\.<br />|
|[Dx1Pix](Dx1Pix.md)|Returns the offset of the object in resolution\-&#8203;independent\-&#8203;pixels \(1/96 of an inch\) from the left of the cell\.<br />|
|[Dy1Pix](Dy1Pix.md)|Returns the offset of the object in resolution\-&#8203;independent\-&#8203;pixels \(1/96 of an inch\) from the top of the cell\.<br />|
|[Dx2Pix](Dx2Pix.md)|Returns the offset of the object in resolution\-&#8203;independent\-&#8203;pixels \(1/96 of an inch\) from the left of the cell\.<br />|
|[Dy2Pix](Dy2Pix.md)|Returns the offset of the object in resolution\-&#8203;independent\-&#8203;pixels \(1/96 of an inch\) from the top of the cell\.<br />|
|[Dx1Points](Dx1Points.md)|Returns the offset of the object in points from the left of the cell\. This is used for display, and is not the exact conversion from Dx1Pix\.<br />|
|[Dy1Points](Dy1Points.md)|Returns the offset of the object in points from the top of the cell\.<br />|
|[Dx2Points](Dx2Points.md)|Returns the offset of the object in points from the left of the cell\.<br />|
|[Dy2Points](Dy2Points.md)|Returns the offset of the object in points from the top of the cell\.<br />|
|[Clone](Clone.md)|Creates a copy of the Anchor|
|[Equals](Equals.md)|Returns true if both objects have the same data\.<br />|
|[GetHashCode](GetHashCode.md)|Returns the hash code for the object\.<br />|
|[Contains](Contains.md)|Returns true if the target anchor is inside or equal to this one\.<br />|
|[Null](Null.md)|Returns an undefined Anchor\.<br />|
|[CalcChildRect](CalcChildRect.md)|Returns the coordinates of the shape when it is part of a group\.<br />|
|[IsNull](IsNull.md)|Returns true if the record doesn't have a defined value\.<br />|
|[HasValue](HasValue.md)|Returns true if the record has a defined value\. This is the inverse of [IsNull](IsNull.md)|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


## Properties

|Name|Description|
|---|---|
|[Biff8Length](Biff8Length.md)|Length of the Serialized array\.<br />This serialized array is in biff8 format, so it doesn't allow more than 65536 rows\.<br />|
|[ChartCoords](ChartCoords.md)|If true, this object is inside a chart, and columns and rows range from 0 to 4000\.<br />|
|[AnchorType](AnchorType.md)|How the image behaves when copying/inserting cells\.<br />|
|[Col1](Col1.md)|First column of object|
|[Dx1](Dx1.md)|Delta x of image, on 1/1024 of a cell\.  0 means totally at the left, 512 on half of the cell, 1024 means at the left of next cell\.<br />|
|[Row1](Row1.md)|First Row of object\.<br />|
|[Dy1](Dy1.md)|Delta y of image on 1/255 of a cell\. 0 means totally at the top, 128 on half of the cell, 255 means at the top of next cell\.<br />|
|[Col2](Col2.md)|Last column of object\.<br />|
|[Dx2](Dx2.md)|Delta x of image, on 1/1024 of a cell\.  0 means totally at the left, 512 on half of the cell, 1024 means at the left of next cell\.<br />|
|[Row2](Row2.md)|Last row of object\.<br />|
|[Dy2](Dy2.md)|Delta y of image on 1/255 of a cell\. 0 means totally at the top, 128 on half of the cell, 255 means at the top of next cell\.<br />|


