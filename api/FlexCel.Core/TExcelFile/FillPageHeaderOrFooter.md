---
uid: TExcelFile.FillPageHeaderOrFooter
description: TExcelFile.FillPageHeaderOrFooter
---

# TExcelFile\.FillPageHeaderOrFooter Method

Given a Page Header or footer string including macros \(like \[FileName\] or \[PageNo\]\), this method will return the strings that go into the left, right and middle sections\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.FillPageHeaderOrFooter(const fullText: string; var leftText: string; var centerText: string; var rightText: string); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**fullText**|string|Header or footer text\.|
|var|**leftText**|string|Text that should be left justified\.|
|var|**centerText**|string|Text that should be centered\.|
|var|**rightText**|string|Text that should be right justified\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

