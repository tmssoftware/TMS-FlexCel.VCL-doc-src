---
uid: TXlsFile.XlsxExtraCompatibility
description: TXlsFile.XlsxExtraCompatibility
---

# TXlsFile.XlsxExtraCompatibility Property

By default, FlexCel creates xlsx files that conform to the published xlsx spec, but are not necessarily the same as a file Excel would create\. FlexCel might use different prefixes, etc, as the ones Excel choose to use\.
While this is ok, some third party tools might have problems opening the xlsx files if they are not exactly as Excel would create them\. If you are having issues with third party tools and the xlsx files created by FlexCel, you can try setting this property to true\. **Note:** setting this property to true might result in files that contain invalid Ids, because the Ids are used by FlexCel and Excel\. This is a very unlikely possibility, but the risk is there\. If possible, it is best to keep this property false\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TXlsFile/index.md">TXlsFile</a>.XlsxExtraCompatibility: Boolean</code></pre>

## See also

* [TXlsFile](../TXlsFile/index.md)

