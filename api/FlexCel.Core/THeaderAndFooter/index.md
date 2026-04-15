---
uid: THeaderAndFooter
description: THeaderAndFooter
---

# THeaderAndFooter Record

Contains all information about headers and footers in an Excel sheet\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">THeaderAndFooter = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|Initializes an empty THeaderAndFooter record\.<br />|
|[SetAllHeaders](SetAllHeaders.md)|Sets the headers for all the pages to a given string\. **Note that setting this value will  set [DiffEvenPages](DiffEvenPages.md) and [DiffFirstPage](DiffFirstPage.md) to false\.** For a description of the possible values of this string, see [TExcelFile.&#8203;Page&#8203;Header](../TExcelFile/PageHeader.md)|
|[SetAllFooters](SetAllFooters.md)|Sets the footers for all the pages to a given string\. **Note that setting this value will set [DiffEvenPages](DiffEvenPages.md) and [DiffFirstPage](DiffFirstPage.md) to false\.** For a description of the possible values of this string, see [TExcelFile.&#8203;Page&#8203;Header](../TExcelFile/PageHeader.md)|
|[GetHeader](GetHeader.md)|Returns the header for a given page, considering if there are differences in even/odd pages or the first page\.<br />|
|[GetFooter](GetFooter.md)|Returns the footer for a given page, considering if there are differences in even/odd pages or the first page\.<br />|
|[GetHeaderAnd&#8203;Footer&#8203;Kind](GetHeaderAndFooterKind.md)|Returns the kind of footer image for a given page\. This method is normally useful to get the correct image for a specific page\.<br />|
|[Equals](Equals.md)|Returns true if both objects are the same\.<br />|
|[GetHashCode](GetHashCode.md)|Hashcode for the obeject\.<br />|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


## Properties

|Name|Description|
|---|---|
|[DefaultHeader](DefaultHeader.md)|Returns or sets the header for all pages that are not even or the first page\. If [DiffFirstPage](DiffFirstPage.md) is false, then this string also applies to the first page\. If [DiffEvenPages](DiffEvenPages.md) is false, this string also applies for even pages\.<br />For a description of the possible values of this string, see [TExcelFile.&#8203;Page&#8203;Header](../TExcelFile/PageHeader.md)<br />To set a header for all pages, use [SetAllHeaders](SetAllHeaders.md)|
|[DefaultFooter](DefaultFooter.md)|Returns or sets the footer for all pages that are not even or the first page\. If [DiffFirstPage](DiffFirstPage.md) is false, then this string also applies to the first page\. If [DiffEvenPages](DiffEvenPages.md) is false, this string also applies for even pages\.<br />For a description of the possible values of this string, see [TExcelFile.&#8203;Page&#8203;Header](../TExcelFile/PageHeader.md)<br />To set a footer for all pages, use [SetAllFooters](SetAllFooters.md)|
|[EvenHeader](EvenHeader.md)|Header for even pages\. **Note that this value is valid if and only if [DiffEvenPages](DiffEvenPages.md) is true\.**         For a description of the possible values of this string, see [TExcelFile.&#8203;Page&#8203;Header](../TExcelFile/PageHeader.md)<br />If you don't want a different header for even pages, set [DiffEvenPages](DiffEvenPages.md) to false or call [SetAllHeaders](SetAllHeaders.md)\.<br />|
|[EvenFooter](EvenFooter.md)|Footer for even pages\. **Note that this value is valid if and only if [DiffEvenPages](DiffEvenPages.md) is true\.** For a description of the possible values of this string, see [TExcelFile.&#8203;Page&#8203;Header](../TExcelFile/PageHeader.md)<br />If you don't want a different footer for even pages, set [DiffEvenPages](DiffEvenPages.md) to false or call [SetAllFooters](SetAllFooters.md)\.<br />|
|[FirstHeader](FirstHeader.md)|Header for the first page\. **Note that this value is valid if and only if [DiffFirstPage](DiffFirstPage.md) is true\.**         For a description of the possible values of this string, see [TExcelFile.&#8203;Page&#8203;Header](../TExcelFile/PageHeader.md)<br />If you don't want a different header for the first page, set [DiffFirstPage](DiffFirstPage.md) to false or call [SetAllHeaders](SetAllHeaders.md)\.<br />|
|[FirstFooter](FirstFooter.md)|Footer for the first page\.**Note that this value is valid if and only if [DiffFirstPage](DiffFirstPage.md) is true\.**         For a description of the possible values of this string, see [TExcelFile.&#8203;Page&#8203;Header](../TExcelFile/PageHeader.md)<br />If you don't want a different footer for the first page, set [DiffFirstPage](DiffFirstPage.md) to false or call [SetAllFooters](SetAllFooters.md)\.<br />|
|[DiffFirstPage](DiffFirstPage.md)|When true the first page will have a different header and footer from the rest, and it will be specified in [FirstHeader](FirstHeader.md) and [FirstFooter](FirstFooter.md)\. When false, FirstHeader and FirstFooter have no meaning\.<br />|
|[DiffEvenPages](DiffEvenPages.md)|When true even pages will have different headers and footers from odd pages, and headers/footer for even pages will be specified in [EvenHeader](EvenHeader.md) and [EvenFooter](EvenFooter.md)\. When false, EvenHeader and EvenFooter have no meaning\.<br />|
|[ScaleWithDoc](ScaleWithDoc.md)|Determines if to scale header and footer with document scaling or not\.<br />|
|[AlignMargins](AlignMargins.md)|Align header footer margins with page margins\. When true, as left/right margins grow and shrink, the header and footer edges stay aligned with the margins\. When false, headers and footers are aligned on the paper edges, regardless of margins\.<br />|


