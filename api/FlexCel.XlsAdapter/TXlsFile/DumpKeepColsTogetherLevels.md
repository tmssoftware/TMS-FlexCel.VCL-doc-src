---
uid: TXlsFile.DumpKeepColsTogetherLevels
description: TXlsFile.DumpKeepColsTogetherLevels
---

# TXlsFile\.DumpKeepColsTogetherLevels Method

This method is used for debugging intelligent page breaks \(see ['Intelligent page breaks' in the Api Developer Guide](xref:ApiDeveloperGuide#intelligent-page-breaks)\.
It will read the keep\-together level for every column and writer it the row "row"\. Note that the contents of row will be overwritten\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.DumpKeepColsTogetherLevels(const row: Integer; const XF: Integer); override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row where the keep\-together levels will be written \(1 based\)\. Existing data in the row will be overwritten\.|
|const|**XF**|Integer|Format for the cells that will be written\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

