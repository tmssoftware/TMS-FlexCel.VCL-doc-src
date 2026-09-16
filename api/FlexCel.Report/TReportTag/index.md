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
|[ApplyFormatTag](ApplyFormatTag.md)|Modifies a format\.\(For example "Font\-Name"\)\.|
|[ConfigTag](ConfigTag.md)|Returns a particular configuration tag\.|
|[ConfigTagParams](ConfigTagParams.md)|Returns the parameters for a particular configuration tag\.|
|[TryGetTag](TryGetTag.md)|All available tags\.|
|[TryGetTagParams](TryGetTagParams.md)|Number of params for all available tags\.|


## Properties

|Name|Description|
|---|---|
|[ColFull1](ColFull1.md)|Range delimiter\.|
|[ColFull2](ColFull2.md)|Range delimiter\.|
|[ColRange1](ColRange1.md)|Range delimiter\.|
|[ColRange2](ColRange2.md)|Range delimiter\.|
|[CrossTabFull1](CrossTabFull1.md)|Range delimiter\.|
|[CrossTabFull2](CrossTabFull2.md)|Range delimiter\.|
|[CrossTabRange1](CrossTabRange1.md)|Range delimiter\.|
|[CrossTabRange2](CrossTabRange2.md)|Range delimiter\.|
|[DbSeparator](DbSeparator.md)|"\."|
|[InternalDB](InternalDB.md)|"\_&#8203;\_&#8203;\#&#8203;\#&#8203;INT\_&#8203;RNAL\_&#8203;"|
|[KeepColsTogether](KeepColsTogether.md)|Named Range starting with KeepColumns\_|
|[KeepRowsTogether](KeepRowsTogether.md)|Named Range starting with KeepRows\_|
|[ParamDelim](ParamDelim.md)|Function delimiter\. \(for example: "\<\#if\(xx ; yy ; zz\)>|
|[Relationship&#8203;Separator](RelationshipSeparator.md)|"\->"|
|[RowFull1](RowFull1.md)|Range delimiter\.|
|[RowFull2](RowFull2.md)|Range delimiter\.|
|[RowRange1](RowRange1.md)|Range delimiter\.|
|[RowRange2](RowRange2.md)|Range delimiter\.|
|[StrAbsoluteReferences](StrAbsoluteReferences.md)|ABSOLUTEREFERENCES|
|[StrAggAvg](StrAggAvg.md)|"Avg"|
|[StrAggCount](StrAggCount.md)|"Count"|
|[StrAggMax](StrAggMax.md)|"Max"|
|[StrAggMin](StrAggMin.md)|"Min"|
|[StrAggSum](StrAggSum.md)|"Sum"|
|[StrAlignBottom](StrAlignBottom.md)|"Bottom"|
|[StrAlignCenter](StrAlignCenter.md)|"Center"|
|[StrAlignLeft](StrAlignLeft.md)|"LEFT"|
|[StrAlignRight](StrAlignRight.md)|"Right"|
|[StrAlignTop](StrAlignTop.md)|"Top"|
|[StrAutofit](StrAutofit.md)|"Autofit"|
|[StrAutofitMode&#8203;Balanced](StrAutofitModeBalanced.md)|"Balanced"|
|[StrAutofitModeFirst](StrAutofitModeFirst.md)|"First"|
|[StrAutofitModeLast](StrAutofitModeLast.md)|"Last"|
|[StrAutofitModeNone](StrAutofitModeNone.md)|"None"|
|[StrAutofitOff](StrAutofitOff.md)|"Selected"|
|[StrAutofitOn](StrAutofitOn.md)|"All"|
|[StrClose](StrClose.md)|Close a Tag\.|
|[StrCloseHLink](StrCloseHLink.md)|Close an Hyperlink Tag\. As we can't use \# on hyperlink texts, this gives an alternative\.|
|[StrCloseParen](StrCloseParen.md)|Close Parenthesis\.|
|[StrConfigSheet](StrConfigSheet.md)|CONFIG|
|[StrCopyCols](StrCopyCols.md)|"C"|
|[StrCopyRows](StrCopyRows.md)|"R"|
|[StrCopyRowsAndCols](StrCopyRowsAndCols.md)|"RC"|
|[StrDataSetAlias](StrDataSetAlias.md)|"ALIAS"|
|[StrDataSetAlias2](StrDataSetAlias2.md)|"\.\.ALIAS\.\."|
|[StrDbEnd](StrDbEnd.md)|"\]"|
|[StrDbStart](StrDbStart.md)|"\["|
|[StrDebug](StrDebug.md)|DEBUG|
|[StrDebugIntelligent&#8203;Page&#8203;Breaks](StrDebugIntelligentPageBreaks.md)|DEBUGINTELLIGENTPAGEBREAKS|
|[StrDefinedGlobal](StrDefinedGlobal.md)|"Global"|
|[StrDefinedLocal](StrDefinedLocal.md)|"Local"|
|[StrDeleteLastRow](StrDeleteLastRow.md)|"X"|
|[StrDontGrow](StrDontGrow.md)|"DontGrow"|
|[StrDontInsertRanges](StrDontInsertRanges.md)|"FIXED"|
|[StrDontKeepAutofit](StrDontKeepAutofit.md)|"Fixed"|
|[StrDontShrink](StrDontShrink.md)|"DontShrink"|
|[StrDynamicInclude](StrDynamicInclude.md)|"Dynamic"|
|[StrEndKeepTogether](StrEndKeepTogether.md)|End of tag for keeprowstogether and keepcolstogether|
|[StrEqual](StrEqual.md)|=|
|[StrErrorsInResult&#8203;File](StrErrorsInResultFile.md)|ERRORSINRESULTFILE|
|[StrExcludeSheet](StrExcludeSheet.md)|"\."|
|[StrFullDelete](StrFullDelete.md)|"Full"|
|[StrFullDs](StrFullDs.md)|"\*"|
|[StrFullDsCaptions](StrFullDsCaptions.md)|"\*\*"|
|[StrHide](StrHide.md)|"Hide"|
|[StrInCol](StrInCol.md)|"InCol"|
|[StrInRow](StrInRow.md)|"InRow"|
|[StrKeepAutofit](StrKeepAutofit.md)|"Keep"|
|[StrOpen](StrOpen.md)|Open a Tag\.|
|[StrOpenHLink](StrOpenHLink.md)|\*\*WARNING\*\*Excel2003 does not let you write this either on hyperlinks, so use StrOpenHLink2\.<br />Open an Hyperlink Tag\. As we can't use \# on hyperlink texts, this gives an alternative\.<br />|
|[StrOpenHLink2](StrOpenHLink2.md)|Open an Hyperlink Tag\. As we can't use \# on hyperlink texts, this gives an alternative\.|
|[StrOpenParen](StrOpenParen.md)|Open Parenthesis\.|
|[StrQuote](StrQuote.md)|Quote\.|
|[StrRelativeDelete](StrRelativeDelete.md)|"Relative"|
|[StrRowCountColumn](StrRowCountColumn.md)|"\#RecordCount"|
|[StrRowPosColumn](StrRowPosColumn.md)|"\#RecordPos"|
|[StrSemiAbsolute&#8203;References](StrSemiAbsoluteReferences.md)|SEMIABSOLUTEREFERENCES|
|[StrShow](StrShow.md)|"Show"|
|[StrStaticInclude](StrStaticInclude.md)|"Static"|
|[StrVeryHide](StrVeryHide.md)|"Very Hide"|
|[SwapSeries](SwapSeries.md)|SWAP SERIES|
|[TagTableKeys](TagTableKeys.md)|List of tag ids\.<br />|


