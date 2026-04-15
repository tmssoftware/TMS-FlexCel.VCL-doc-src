---
uid: TReportTag
description: TReportTag
---

# TReportTag Record

Tags used in reports\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">TReportTag = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[TryGetTag](TryGetTag.md)|All available tags\.|
|[TryGetTagParams](TryGetTagParams.md)|Number of params for all available tags\.|
|[ConfigTag](ConfigTag.md)|Returns a particular configuration tag\.|
|[ApplyFormatTag](ApplyFormatTag.md)|Modifies a format\.\(For example "Font\-Name"\)\.|
|[ConfigTagParams](ConfigTagParams.md)|Returns the parameters for a particular configuration tag\.|


## Properties

|Name|Description|
|---|---|
|[StrOpen](StrOpen.md)|Open a Tag\.|
|[StrOpenHLink](StrOpenHLink.md)|\*\*WARNING\*\*Excel2003 does not let you write this either on hyperlinks, so use StrOpenHLink2\.<br />Open an Hyperlink Tag\. As we can't use \# on hyperlink texts, this gives an alternative\.<br />|
|[StrOpenHLink2](StrOpenHLink2.md)|Open an Hyperlink Tag\. As we can't use \# on hyperlink texts, this gives an alternative\.|
|[StrClose](StrClose.md)|Close a Tag\.|
|[StrCloseHLink](StrCloseHLink.md)|Close an Hyperlink Tag\. As we can't use \# on hyperlink texts, this gives an alternative\.|
|[ParamDelim](ParamDelim.md)|Function delimiter\. \(for example: "\<\#if\(xx ; yy ; zz\)>|
|[StrOpenParen](StrOpenParen.md)|Open Parenthesis\.|
|[StrCloseParen](StrCloseParen.md)|Close Parenthesis\.|
|[StrQuote](StrQuote.md)|Quote\.|
|[DbSeparator](DbSeparator.md)|"\."|
|[StrFullDs](StrFullDs.md)|"\*"|
|[StrFullDsCaptions](StrFullDsCaptions.md)|"\*\*"|
|[StrDeleteLastRow](StrDeleteLastRow.md)|"X"|
|[StrDontInsertRanges](StrDontInsertRanges.md)|"FIXED"|
|[StrDataSetAlias](StrDataSetAlias.md)|"ALIAS"|
|[StrDataSetAlias2](StrDataSetAlias2.md)|"\.\.ALIAS\.\."|
|[StrExcludeSheet](StrExcludeSheet.md)|"\."|
|[Relationship&#8203;Separator](RelationshipSeparator.md)|"\->"|
|[InternalDB](InternalDB.md)|"\_&#8203;\_&#8203;\#&#8203;\#&#8203;INT\_&#8203;RNAL\_&#8203;"|
|[StrRowCountColumn](StrRowCountColumn.md)|"\#RecordCount"|
|[StrRowPosColumn](StrRowPosColumn.md)|"\#RecordPos"|
|[StrShow](StrShow.md)|"Show"|
|[StrHide](StrHide.md)|"Hide"|
|[StrVeryHide](StrVeryHide.md)|"Very Hide"|
|[StrAutofit](StrAutofit.md)|"Autofit"|
|[StrAutofitOn](StrAutofitOn.md)|"All"|
|[StrAutofitOff](StrAutofitOff.md)|"Selected"|
|[StrKeepAutofit](StrKeepAutofit.md)|"Keep"|
|[StrDontKeepAutofit](StrDontKeepAutofit.md)|"Fixed"|
|[StrAutofitModeFirst](StrAutofitModeFirst.md)|"First"|
|[StrAutofitModeLast](StrAutofitModeLast.md)|"Last"|
|[StrAutofitModeNone](StrAutofitModeNone.md)|"None"|
|[StrAutofitMode&#8203;Balanced](StrAutofitModeBalanced.md)|"Balanced"|
|[StrDefinedLocal](StrDefinedLocal.md)|"Local"|
|[StrDefinedGlobal](StrDefinedGlobal.md)|"Global"|
|[StrRelativeDelete](StrRelativeDelete.md)|"Relative"|
|[StrFullDelete](StrFullDelete.md)|"Full"|
|[StrStaticInclude](StrStaticInclude.md)|"Static"|
|[StrDynamicInclude](StrDynamicInclude.md)|"Dynamic"|
|[StrCopyRows](StrCopyRows.md)|"R"|
|[StrCopyCols](StrCopyCols.md)|"C"|
|[StrCopyRowsAndCols](StrCopyRowsAndCols.md)|"RC"|
|[StrAlignLeft](StrAlignLeft.md)|"LEFT"|
|[StrAlignCenter](StrAlignCenter.md)|"Center"|
|[StrAlignRight](StrAlignRight.md)|"Right"|
|[StrAlignTop](StrAlignTop.md)|"Top"|
|[StrAlignBottom](StrAlignBottom.md)|"Bottom"|
|[StrInRow](StrInRow.md)|"InRow"|
|[StrInCol](StrInCol.md)|"InCol"|
|[StrDontGrow](StrDontGrow.md)|"DontGrow"|
|[StrDontShrink](StrDontShrink.md)|"DontShrink"|
|[StrAggSum](StrAggSum.md)|"Sum"|
|[StrAggAvg](StrAggAvg.md)|"Avg"|
|[StrAggMax](StrAggMax.md)|"Max"|
|[StrAggMin](StrAggMin.md)|"Min"|
|[StrAggCount](StrAggCount.md)|"Count"|
|[StrDbStart](StrDbStart.md)|"\["|
|[StrDbEnd](StrDbEnd.md)|"\]"|
|[RowRange1](RowRange1.md)|Range delimiter\.|
|[RowFull1](RowFull1.md)|Range delimiter\.|
|[RowRange2](RowRange2.md)|Range delimiter\.|
|[RowFull2](RowFull2.md)|Range delimiter\.|
|[ColRange1](ColRange1.md)|Range delimiter\.|
|[ColFull1](ColFull1.md)|Range delimiter\.|
|[ColRange2](ColRange2.md)|Range delimiter\.|
|[ColFull2](ColFull2.md)|Range delimiter\.|
|[CrossTabRange1](CrossTabRange1.md)|Range delimiter\.|
|[CrossTabRange2](CrossTabRange2.md)|Range delimiter\.|
|[CrossTabFull1](CrossTabFull1.md)|Range delimiter\.|
|[CrossTabFull2](CrossTabFull2.md)|Range delimiter\.|
|[KeepRowsTogether](KeepRowsTogether.md)|Named Range starting with KeepRows\_|
|[KeepColsTogether](KeepColsTogether.md)|Named Range starting with KeepColumns\_|
|[StrEndKeepTogether](StrEndKeepTogether.md)|End of tag for keeprowstogether and keepcolstogether|
|[TagTableKeys](TagTableKeys.md)|List of tag ids\.<br />|
|[StrEqual](StrEqual.md)|=|
|[StrConfigSheet](StrConfigSheet.md)|CONFIG|
|[StrDebug](StrDebug.md)|DEBUG|
|[StrErrorsInResult&#8203;File](StrErrorsInResultFile.md)|ERRORSINRESULTFILE|
|[StrDebugIntelligent&#8203;Page&#8203;Breaks](StrDebugIntelligentPageBreaks.md)|DEBUGINTELLIGENTPAGEBREAKS|
|[StrSemiAbsolute&#8203;References](StrSemiAbsoluteReferences.md)|SEMIABSOLUTEREFERENCES|
|[StrAbsoluteReferences](StrAbsoluteReferences.md)|ABSOLUTEREFERENCES|
|[SwapSeries](SwapSeries.md)|SWAP SERIES|


