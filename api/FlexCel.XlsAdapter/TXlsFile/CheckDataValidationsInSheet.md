---
uid: TXlsFile.CheckDataValidationsInSheet
description: TXlsFile.CheckDataValidationsInSheet
---

# TXlsFile\.CheckDataValidationsInSheet Method

Checks if all the cells in the active sheet inside data validations have values that are valid according to the data validation specifications\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.CheckDataValidationsInSheet(const sheet: Integer; const maxErrors: Integer): <a href="../../FlexCel.Core/TCellAddress/index.md">TArray&lt;TCellAddress></a>; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer|Sheet to check \(1 based\)|
|const|**maxErrors**|Integer|The maximum number of errors reported by this method\. To avoid getting a too big list, set it to a number like 100\. If set to 0 or a negative number, the full list of errors will be returned, which can be very big\.|


## Returns

An array with the first maxErrors cells that do not conform to the data validation\. And empty array if all the cells conform\.

## See also

* [TXlsFile](../TXlsFile/index.md)

