---
uid: TExcelFile.SetLink
description: TExcelFile.SetLink
---

# TExcelFile\.SetLink Method

Changes the external link at position i for a new value\. Note that you can't add new links with this method, external links are added automatically when you add formulas that reference other worksheets\. This method is only to change existing links to point to other place\. All formulas pointing to the old link will point to the new\.

Note that the replacing filename should have the same sheets as the original, or the formulas might break\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetLink(const index: Integer; const value: string); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**index**|Integer|Index of the link \(1 based\)\. i goes between 1 and [LinkCount](LinkCount.md)|
|const|**value**|string|Please make sure this is a VALID filename, or you are likely to crash Excel\. Also, xls file format doesn't like paths starting with "\.\.", so you might need to enter the full path here\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

