---
uid: TXlsFile.FillPageHeaderOrFooter
description: TXlsFile.FillPageHeaderOrFooter
---

# TXlsFile\.FillPageHeaderOrFooter Method

Given a Page Header or footer string including macros \(like \[FileName\] or \[PageNo\]\), this method will return the strings that go into the left, right and middle sections\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.FillPageHeaderOrFooter(const fullText: string; var leftText: string; var centerText: string; var rightText: string); override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**fullText**|string|Header or footer text\.|
|var|**leftText**|string|Text that should be left justified\.|
|var|**centerText**|string|Text that should be centered\.|
|var|**rightText**|string|Text that should be right justified\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

