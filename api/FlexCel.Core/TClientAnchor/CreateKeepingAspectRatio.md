---
uid: TClientAnchor.CreateKeepingAspectRatio
description: TClientAnchor.CreateKeepingAspectRatio
---

# TClientAnchor\.CreateKeepingAspectRatio Method

This method will create an anchor so the image keeps its aspect ratio, and it is contained inside the group of cells\.
If you supply negative values for Col2 or Row2, then those values will be ignored\. If you set Col2 negative, then this method will place the image between Row1 and Row2, and calculate Col2 so the image keeps its aspect ratio\.
Similar if you set Row2 negative\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TClientAnchor/index.md">TClientAnchor</a>.CreateKeepingAspectRatio(const Image: <a href="../TUIImage/index.md">TUIImage</a>; const aAnchorType: <a href="../TFlxAnchorType.md">TFlxAnchorType</a>; const aRow1: Integer; const aDy1: Integer; const aCol1: Integer; const aDx1: Integer; const aRow2: Integer; const aDy2: Integer; const aCol2: Integer; const aDx2: Integer; const aVAlign: <a href="../TFlexCelImageVertAlign.md">TFlexCelImageVertAlign</a>; const aHAlign: <a href="../TFlexCelImageHorizAlign.md">TFlexCelImageHorizAlign</a>; const Workbook: <a href="../IRowColSize/index.md">IRowColSize</a>): <a href="../TClientAnchor/index.md">TClientAnchor</a>; static;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**Image**|[TUIImage](../TUIImage/index.md)|Image that you want to insert\. It is used to know its dimensions and dpi\.|
|const|**aAnchorType**|[TFlxAnchorType](../TFlxAnchorType.md)|How the image behaves when copying/inserting cells\.|
|const|**aRow1**|Integer|First Row of object\.|
|const|**aDy1**|Integer|Delta y of image on 1/255 of a cell\. 0 means totally at the top, 128 on half of the cell, 255 means at the top of next cell\.|
|const|**aCol1**|Integer|First column of object\.|
|const|**aDx1**|Integer|Delta x of image, on 1/1024 of a cell\.  0 means totally at the left, 512 on half of the cell, 1024 means at the left of next cell\.|
|const|**aRow2**|Integer|Last row of object\.**Set it to 0 or negative for unlimited rows\.**|
|const|**aDy2**|Integer|Delta y of image on 1/255 of a cell\. 0 means totally at the top, 128 on half of the cell, 255 means at the top of next cell\.|
|const|**aCol2**|Integer|Last column of object\.**Set it to 0 or negative for unlimited columns\.**|
|const|**aDx2**|Integer|Delta x of image, on 1/1024 of a cell\.  0 means totally at the left, 512 on half of the cell, 1024 means at the left of next cell\.|
|const|**aVAlign**|[TFlexCelImage&#8203;Vert&#8203;Align](../TFlexCelImageVertAlign.md)|How the image will be fit inside the range of cells\.|
|const|**aHAlign**|[TFlexCelImage&#8203;Horiz&#8203;Align](../TFlexCelImageHorizAlign.md)|How the image will be fit inside the range of cells\.|
|const|**Workbook**|[IRowColSize](../IRowColSize/index.md)|ExcelFile with the workbook, used to calculate the cells\.|


## See also

* [TClientAnchor](../TClientAnchor/index.md)

