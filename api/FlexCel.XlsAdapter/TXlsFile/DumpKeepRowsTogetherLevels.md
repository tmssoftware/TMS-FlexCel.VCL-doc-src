---
uid: TXlsFile.DumpKeepRowsTogetherLevels
description: TXlsFile.DumpKeepRowsTogetherLevels
---

# TXlsFile\.DumpKeepRowsTogetherLevels Method

This method is used for debugging intelligent page breaks \(see ['Intelligent page breaks' in the Api Developer Guide](xref:ApiDeveloperGuide#intelligent-page-breaks)\.
It will read the keep\-together level for every row ad write it at the column "col"\. Note that the contents of col will be overwritten\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.DumpKeepRowsTogetherLevels(const col: Integer; const XF: Integer); override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**col**|Integer|Column where the keep\-together levels will be written \(1 based\)\. Existing data in the column will be overwritten\.|
|const|**XF**|Integer|Format for the cells that will be written\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

