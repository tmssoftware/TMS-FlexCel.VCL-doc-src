---
uid: TExcelFile.CheckDataValidationsInSheet
description: TExcelFile.CheckDataValidationsInSheet
---

# TExcelFile\.CheckDataValidationsInSheet Method

Checks if all the cells in the active sheet inside data validations have values that are valid according to the data validation specifications\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.CheckDataValidationsInSheet(const sheet: Integer; const maxErrors: Integer): <a href="../TCellAddress/index.md">TArray&lt;TCellAddress></a>; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer|Sheet to check \(1 based\)|
|const|**maxErrors**|Integer|The maximum number of errors reported by this method\. To avoid getting a too big list, set it to a number like 100\. If set to 0 or a negative number, the full list of errors will be returned, which can be very big\.|


## Returns

An array with the first maxErrors cells that do not conform to the data validation\. And empty array if all the cells conform\.

## See also

* [TExcelFile](../TExcelFile/index.md)

