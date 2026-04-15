---
uid: TXlsFile.AddCustomXmlPart
description: TXlsFile.AddCustomXmlPart
---

# TXlsFile\.AddCustomXmlPart Method

Adds a custom XML part to the file, as described in [https://msdn.microsoft.com/en-us/library/bb608618.aspx](https://msdn.microsoft.com/en-us/library/bb608618.aspx)

## Remarks

Excel saves the file in the encoding specified by the xml declaration\. But this goes against the spec\.




From Open Packaging specification:



XML content shall be encoded using either UTF\-8 or UTF\-16\. If any part includes an encoding declaration, as defined in $4\.3\.3 of the XML 1\.0 specification, that declaration shall not name any encoding other than UTF\-8 or UTF\-16\. Package implementers shall enforce this requirement upon creation and retrieval of the XML content\. \[M1\.17\]



FlexCel will behave like Excel and use the encoding in the xml declaration if one is present, but you should make that encoding UTF8 or UTF16\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.AddCustomXmlPart(const part: <a href="../../FlexCel.Core/TCustomXmlPart/index.md">TCustomXmlPart</a>); override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**part**|[TCustomXmlPart](../../FlexCel.Core/TCustomXmlPart/index.md)|Part to add\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

