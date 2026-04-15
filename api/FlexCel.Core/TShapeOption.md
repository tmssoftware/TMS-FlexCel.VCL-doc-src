---
uid: TShapeOption
description: TShapeOption
---

# TShapeOption Enumeration

Many different configuration options for a shape\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|None|0|Not defined\.<br />|
|Rotation|4|Rotation in 1/65536 degrees\.<br />|
|LockRotation|119|No rotation|
|fLockAspectRatio|120|Don't allow changes in aspect ratio|
|fLockPosition|121|Don't allow the shape to be moved|
|fLockAgainstSelect|122|Shape may not be selected|
|fLockCropping|123|No cropping this shape|
|fLockVertices|124|Edit Points not allowed|
|fLockText|125|Do not edit text|
|fLockAdjustHandles|126|Do not adjust|
|fLockAgainstGrouping|127|Do not group this shape|
|lTxid|128|id for the text, value determined by the host|
|dxTextLeft|129|margins relative to shape's inscribed text rectangle \(in EMUs\) 1/10 inch|
|dyTextTop|130|margins relative to shape's inscribed text rectangle \(in EMUs\) 1/20 inch|
|dxTextRight|131|margins relative to shape's inscribed text rectangle \(in EMUs\) 1/10 inch|
|dyTextBottom|132|margins relative to shape's inscribed text rectangle \(in EMUs\) 1/20 inch|
|WrapText|133|Wrap text at shape margins|
|scaleText|134|Text zoom/scale \(used if fFitTextToShape\)|
|anchorText|135|How to anchor the text|
|txflTextFlow|136|Text flow|
|cdirFont|137|Font rotation|
|hspNext|138|ID of the next shape \(used by Word for linked textboxes\)|
|txdir|139|Bi\-Di Text direction|
|fSelectText|187|TRUE if single click selects text, FALSE if two clicks|
|fAutoTextMargin|188|use host's margin calculations|
|fRotateText|189|Rotate text with shape|
|fFitShapeToText|190|Size shape to fit text size|
|fFitTextToShape|191|Size text to fit shape size|
|gtextUNICODE|192|UNICODE text string|
|gtextRTF|193|RTF text string|
|gtextAlign|194|alignment on curve|
|gtextSize|195|default point size|
|gtextSpacing|196|fixed point 16\.16|
|gtextFont|197|font family name|
|gtextFReverseRows|240|Reverse row order|
|fGtext|241|Has text effect|
|gtextFVertical|242|Rotate characters|
|gtextFKern|243|Kern characters|
|gtextFTight|244|Tightening or tracking|
|gtextFStretch|245|Stretch to fit shape|
|gtextFShrinkFit|246|Char bounding box|
|gtextFBestFit|247|Scale text\-on\-path|
|gtextFNormalize|248|Stretch char height|
|gtextFDxMeasure|249|Do not measure along path|
|gtextFBold|250|Bold font|
|gtextFItalic|251|Italic font|
|gtextFUnderline|252|Underline font|
|gtextFShadow|253|Shadow font|
|gtextFSmallcaps|254|Small caps font|
|gtextFStrikethrough|255|Strike through font|
|cropFromTop|256|16\.16 fraction times total image width or height, as appropriate\.<br />|
|cropFromBottom|257|16\.16 fraction times total image width or height, as appropriate\.<br />|
|cropFromLeft|258|16\.16 fraction times total image width or height, as appropriate\.<br />|
|cropFromRight|259|16\.16 fraction times total image width or height, as appropriate\.<br />|
|pib|260|Blip to display|
|pibName|261|Blip file name|
|pibFlags|262|Blip flags|
|pictureTransparent|263|transparent color \(none if ~0UL\)|
|pictureContrast|264|contrast setting|
|pictureBrightness|265|brightness setting|
|pictureGamma|266|16\.16 gamma|
|pictureId|267|Host\-defined ID for OLE objects \(usually a pointer\)|
|pictureDblCrMod|268|Modification used if shape has double shadow|
|pibPrintName|272|Blip file name|
|pibPrintFlags|273|Blip flags|
|fNoHitTestPicture|316|Do not hit test the picture|
|pictureGray|317|grayscale display|
|pictureBiLevel|318|bi\-level display|
|pictureActive|319|Server is active \(OLE objects only\)|
|geoLeft|320|Defines the G \(geometry\) coordinate space\.<br />|
|geoTop|321||
|geoRight|322||
|geoBottom|323||
|shapePath|324||
|pVertices|325||
|pSegmentInfo|326||
|adjustValue|327|Adjustment values corresponding to the positions of the adjust handles of the shape\. The number of values used and their allowable ranges vary from shape type to shape type\.<br />|
|adjust2Value|328|Adjustment values corresponding to the positions of the adjust handles of the shape\. The number of values used and their allowable ranges vary from shape type to shape type\.<br />|
|adjust3Value|329|Adjustment values corresponding to the positions of the adjust handles of the shape\. The number of values used and their allowable ranges vary from shape type to shape type\.<br />|
|adjust4Value|330|Adjustment values corresponding to the positions of the adjust handles of the shape\. The number of values used and their allowable ranges vary from shape type to shape type\.<br />|
|adjust5Value|331|Adjustment values corresponding to the positions of the adjust handles of the shape\. The number of values used and their allowable ranges vary from shape type to shape type\.<br />|
|adjust6Value|332|Adjustment values corresponding to the positions of the adjust handles of the shape\. The number of values used and their allowable ranges vary from shape type to shape type\.<br />|
|adjust7Value|333|Adjustment values corresponding to the positions of the adjust handles of the shape\. The number of values used and their allowable ranges vary from shape type to shape type\.<br />|
|adjust8Value|334|Adjustment values corresponding to the positions of the adjust handles of the shape\. The number of values used and their allowable ranges vary from shape type to shape type\.<br />|
|adjust9Value|335|Adjustment values corresponding to the positions of the adjust handles of the shape\. The number of values used and their allowable ranges vary from shape type to shape type\.<br />|
|adjust10Value|336|Adjustment values corresponding to the positions of the adjust handles of the shape\. The number of values used and their allowable ranges vary from shape type to shape type\.<br />|
|pConnectionSites|337|This property specifies an array of connection sites that a user can use to make a link between shapes\.<br />|
|pConnectionSitesDir|338|This property specifies an array of angles corresponding to the connection sites in the  pConnectionSites\_complex property that are used to determine the direction that a connector links  to the corresponding connection site\.<br />|
|xLimo|339|This property specifies an x coordinate above which limousine scaling is used in the horizontal  direction\. This means that points whose x coordinate is greater than xLimo have their x coordinates  incremented rather than linearly scaled\.<br />|
|yLimo|340|This property specifies an y coordinate above which limousine scaling is used in the vertical  direction\. This means that points whose y coordinate is greater than yLimo have their y coordinates incremented rather than linearly scaled\.<br />|
|pAdjustHandles|341|This property specifies an array of adjust handles which allow a user to manipulate the geometry of this shape\.<br />|
|pGuides|342|Array of guide formula for the shape which specify how the geometry of the shape changes as the adjust handles are dragged\.<br />|
|pInscribe|343|This property specifies an array of rectangles specifying how text should be inscribed within this shape\.<br />|
|fShadowOK|378|Shadow may be set|
|f3DOK|379|3D may be set|
|fLineOK|380|Line style may be set|
|fGtextOK|381|Text effect \(WordArt\) supported|
|fFillShadeShapeOK|382||
|fFillOK|383|OK to fill the shape through the UI or VBAs|
|fillType|384|Type of fill|
|fillColor|385|Foreground color|
|fillOpacity|386|Fixed 16\.16|
|fillBackColor|387|Background color|
|fillBackOpacity|388|Shades only|
|fillCrMod|389|Modification for BW views|
|fillBlip|390|Pattern/texture|
|fillBlipName|391|Blip file name|
|fillBlipFlags|392|Blip flags|
|fillWidth|393|How big \(A units\) to make a metafile texture\.<br />|
|fillHeight|394||
|fillAngle|395|Fade angle \- degrees in 16\.16|
|fillFocus|396|Linear shaded fill focus percent|
|fillToLeft|397|Fraction 16\.16|
|fillToTop|398|Fraction 16\.16|
|fillToRight|399|Fraction 16\.16|
|fillToBottom|400|Fraction 16\.16|
|fillRectLeft|401|For shaded fills, use the specified rectangle instead of the shape's bounding rect to define how large the fade is going to be\.<br />|
|fillRectTop|402||
|fillRectRight|403||
|fillRectBottom|404||
|fillDztype|405||
|fillShadePreset|406|Special shades|
|fillShadeColors|407|a preset array of colors|
|fillOriginX|408||
|fillOriginY|409||
|fillShapeOriginX|410||
|fillShapeOriginY|411||
|fillShadeType|412|Type of shading, if a shaded \(gradient\) fill\.<br />|
|fFilled|443|Is shape filled?|
|fHitTestFill|444|Should we hit test fill?|
|fillShape|445|Register pattern on shape|
|fillUseRect|446|Use the large rect?|
|fNoFillHitTest|447|Hit test a shape as though filled|
|lineColor|448|Color of line|
|lineOpacity|449|Not implemented|
|lineBackColor|450|Background color|
|lineCrMod|451|Modification for BW views|
|lineType|452|Type of line|
|lineFillBlip|453|Pattern/texture|
|lineFillBlipName|454|Blip file name|
|lineFillBlipFlags|455|Blip flags|
|lineFillWidth|456|How big \(A units\) to make a metafile texture\.<br />|
|lineFillHeight|457||
|lineFillDztype|458|How to interpret fillWidth/Height numbers\.<br />|
|lineWidth|459|A units; 1pt == 12700 EMUs|
|lineMiterLimit|460|ratio \(16\.16\) of width|
|lineStyle|461|Draw parallel lines?|
|lineDashing|462|Can be overridden by:|
|lineDashStyle|463|As Win32 ExtCreatePen|
|lineStartArrowhead|464|Arrow at start|
|lineEndArrowhead|465|Arrow at end|
|lineStartArrowWidth|466|Arrow at start|
|lineStartArrowLength|467|Arrow at end|
|lineEndArrowWidth|468|Arrow at start|
|lineEndArrowLength|469|Arrow at end|
|lineJoinStyle|470|How to join lines|
|lineEndCapStyle|471|How to end lines|
|lineColorExt|473|Extended foreground color|
|fInsetPen|505|Inset line\.<br />|
|fInsetPenOK|506|Allow inset line if prop\. is set|
|fArrowheadsOK|507|Allow arrowheads if prop\. is set|
|fLine|508|Any line?|
|fHitTestLine|509|Should we hit test lines?|
|lineFillShape|510|Register pattern on shape|
|fNoLineDrawDash|511|Draw a dashed line if no line|
|shadowType|512|Type of effect|
|shadowColor|513|Foreground color|
|shadowHighlight|514|Embossed color|
|shadowCrMod|515|Modification for BW views|
|shadowOpacity|516|Fixed 16\.16|
|shadowOffsetX|517|Offset shadow|
|shadowOffsetY|518|Offset shadow|
|shadowSecondOffsetX|519|Double offset shadow|
|shadowSecondOffsetY|520|Double offset shadow|
|shadowScaleXToX|521|16\.16|
|shadowScaleYToX|522|16\.16|
|shadowScaleXToY|523|16\.16|
|shadowScaleYToY|524|16\.16|
|shadowPerspectiveX|525|16\.16 / weight|
|shadowPerspectiveY|526|16\.16 / weight|
|shadowWeight|527|scaling factor|
|shadowOriginX|528||
|shadowOriginY|529||
|fShadow|574|Any shadow?|
|fshadowObscured|575|Excel5\-style shadow|
|perspectiveType|576|Where transform applies|
|perspectiveOffsetX|577|The LONG values define a transformation matrix, effectively, each value is scaled by the perspectiveWeight parameter\.<br />|
|perspectiveOffsetY|578||
|perspectiveScaleXToX|579||
|perspectiveScaleYToX|580||
|perspectiveScaleXToY|581||
|perspectiveScaleYToY|582||
|perspectivePerspectiveX|583||
|perspectivePerspectiveY|584||
|perspectiveWeight|585|Scaling factor|
|perspectiveOriginX|586||
|perspectiveOriginY|587||
|fPerspective|639|On/off|
|c3DSpecularAmt|640|Fixed\-point 16\.16|
|c3DDiffuseAmt|641|Fixed\-point 16\.16|
|c3DShininess|642|Default gives OK results|
|c3DEdgeThickness|643|Specular edge thickness|
|c3DExtrudeForward|644|Distance of extrusion in EMUs|
|c3DExtrudeBackward|645||
|c3DExtrudePlane|646|Extrusion direction|
|c3DExtrusionColor|647|Basic color of extruded part of shape; the lighting model used will determine the exact shades used when rendering\.<br />|
|c3DCrMod|648|Modification for BW views|
|f3D|700|Does this shape have a 3D effect?|
|fc3DMetallic|701|Use metallic specularity?|
|fc3DUseExtrusionColor|702||
|fc3DLightFace|703||
|c3DYRotationAngle|704|degrees \(16\.16\) about y axis|
|c3DXRotationAngle|705|degrees \(16\.16\) about x axis|
|c3DRotationAxisX|706|These specify the rotation axis; only their relative magnitudes matter\.<br />|
|c3DRotationAxisY|707||
|c3DRotationAxisZ|708||
|c3DRotationAngle|709|degrees \(16\.16\) about axis|
|c3DRotationCenterX|710|rotation center x \(16\.16 or g\-units\)|
|c3DRotationCenterY|711|rotation center y \(16\.16 or g\-units\)|
|c3DRotationCenterZ|712|rotation center z \(absolute \(emus\)\)|
|c3DRenderMode|713|Full,wireframe, or bcube|
|c3DTolerance|714|pixels \(16\.16\)|
|c3DXViewpoint|715|X view point \(emus\)|
|c3DYViewpoint|716|Y view point \(emus\)|
|c3DZViewpoint|717|Z view distance \(emus\)|
|c3DOriginX|718||
|c3DOriginY|719||
|c3DSkewAngle|720|degree \(16\.16\) skew angle|
|c3DSkewAmount|721|Percentage skew amount|
|c3DAmbientIntensity|722|Fixed point intensity|
|c3DKeyX|723|Key light source direction; only their relative|
|c3DKeyY|724|Key light source direction; only their relative|
|c3DKeyZ|725|magnitudes matter|
|c3DKeyIntensity|726|Fixed point intensity|
|c3DFillX|727|Fill light source direction; only their relative|
|c3DFillY|728|Fill light source direction; only their relative|
|c3DFillZ|729|magnitudes matter|
|c3DFillIntensity|730|Fixed point intensity|
|fc3DConstrainRotation|763||
|fc3DRotationCenterAuto|764||
|fc3DParallel|765|Parallel projection?|
|fc3DKeyHarsh|766|Is key lighting harsh?|
|fc3DFillHarsh|767||
|hspMaster|769|master shape|
|cxstyle|771|Type of connector|
|bWMode|772|Settings for modifications to be made when in different forms of black\-and\-white mode\.<br />|
|bWModePureBW|773||
|bWModeBW|774||
|wzEquationXML|780|This property is present if the shape represents an equation generated by Office 2007 or later\.<br />The property is a string of XML representing a Word 2003 XML document\.<br />The original equation is stored within the oMathPara tag within the document\.<br />|
|fOleIcon|826|For OLE objects, whether the object is in icon form|
|fPreferRelativeResize|827|For UI only\. Prefer relative resizing\.<br />|
|fLockShapeType|828|Lock the shape type \(don't allow Change Shape\)|
|fInitiator|829|Specifies if the shape must be processed by a rules engine\.<br />|
|fDeleteAttachedObject|830||
|fBackground|831|If TRUE, this is the background shape\.<br />|
|spcot|832|Callout type  \(TwoSegment\)|
|dxyCalloutGap|833|Distance from box to first point\.\(EMUs\) \(1/12 inch\)|
|spcoa|834|Callout angle \(Any\)|
|spcod|835|Callout drop type \(Specified\)|
|dxyCalloutDropSpecified|836|if msospcodSpecified, the actual drop distance \(9 points\)|
|dxyCalloutLengthSpecified|837|if fCalloutLengthSpecified, the actual distance \(0\)|
|fCallout|889|Is the shape a callout? \(FALSE\)|
|fCalloutAccentBar|890|does callout have accent bar? \(FALSE\)|
|fCalloutTextBorder|891|does callout have a text border? \(TRUE\)|
|fCalloutMinusX|892|\(FALSE\)|
|fCalloutMinusY|893|FALSE|
|fCalloutDropAuto|894|If true, then we occasionally invert the drop distance \(FALSE\)|
|fCalloutLengthSpecified|895|if true, we look at dxyCalloutLengthSpecified \(FALSE\)|
|wzName|896|Shape Name \(present only if explicitly set\)|
|wzDescription|897|Alternate text|
|pihlShape|898|The hyperlink in the shape\.<br />|
|pWrapPolygonVertices|899|The polygon that text will be wrapped around \(Word\)|
|dxWrapDistLeft|900|Left wrapping distance from text \(Word\)|
|dyWrapDistTop|901|Top wrapping distance from text \(Word\)|
|dxWrapDistRight|902|Right wrapping distance from text \(Word\)|
|dyWrapDistBottom|903|Bottom wrapping distance from text \(Word\)|
|lidRegroup|904|Regroup ID|
|hyperlinkHint|909|Hint used in the hyperlink\.<br />|
|tableRowProperties|928|This property specifies the minimum sizes of the rows in a table\.<br />|
|xlsxShapeDefinition|937|This record has an xlsx/xml definition of the shape\.<br />|
|fLayoutInCell|944|Specifies if the shape is inside a table cell\.<br />|
|fIsBullet|945|Specifies if the shape is a bullet\.<br />|
|fStandardHR|946|Specifies if the horizontal rule doesn't contain a picture\.<br />|
|fNoshadeHR|947|Specifies if a horizontal ruler uses a color without shading\.<br />|
|fHorizRule|948|Specifies if the shape is a horizontal ruler\.<br />|
|fUserDrawn|949|If true the shape is drawn by the user\.<br />|
|fAllowOverlap|950|True if the shape can overlap another shape\.<br />|
|fReallyHidden|951|Only applies to script anchors\.<br />|
|fScriptAnchor|952|True if shape is a script anchor\.<br />|
|fEditedWrap|953|Has the wrap polygon been edited?|
|fBehindDocument|954|Word\-only \(shape is behind text\)|
|fOnDblClickNotify|955|Notify client on a double click|
|fIsButton|956|A button shape \(i\.e\., clicking performs an action\)\. Set for shapes with attached hyperlinks or macros\.<br />|
|fOneD|957|1D adjustment|
|fHidden|958|Do not display|
|fPrint|959|Print this shape|
|pRelationTbl|1284|This property specifies relationships in a diagram\.<br />|
|dgmConstrainBounds|1288|Diagram constrain bounds|
|lineLeftDashStyle|1359|Custom dash style of the line\.<br />|
|lineTopDashStyle|1423|Custom dash style of the line\.<br />|
|lineRightDashStyle|1487|Custom dash style of the line\.<br />|
|lineBottomDashStyle|1551|Custom dash style of the line\.<br />|


