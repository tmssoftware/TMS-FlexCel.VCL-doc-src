---
uid: TFlexCelReport.AddRelationship
description: TFlexCelReport.AddRelationship
---

# TFlexCelReport\.AddRelationship Method

## Overloads

* [TFlexCelReport\.AddRelationship\(string, string, string, string\)](#tflexcelreportaddrelationshipstring-string-string-string)
* [TFlexCelReport\.AddRelationship\(string, string, TArray\<string>, TArray\<string>\)](#tflexcelreportaddrelationshipstring-string-tarraystring-tarraystring)

# TFlexCelReport\.AddRelationship\(string, string, string, string\)
Adds a relationship between two tables\. Note that if your tables are datasets, or come from Entity Framework, or your master detail tables are nested, you probably don't need to call this method\. FlexCel will detect the relationships automatically and use them\. This method is only for when you have custom data with no DataRelationships \(as in a dataset\) and where detail tables are not nested to the master \(as in Entity Framework\)\.


## Remarks

You might use this method before adding the tables with AddTable\. Tables must exist when running the report, not when adding the relationship\.

## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelReport/index.md">TFlexCelReport</a>.AddRelationship(const masterTable: string; const detailTable: string; const masterKeyFields: string; const detailKeyFields: string); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**masterTable**|string|Master table for the relationship\.|
|const|**detailTable**|string|Detail table for the relationship\.|
|const|**masterKeyFields**|string|Key fields in the master table that relate with the key fields in the detail table\.<br />Must not be null, and normally will be an array with a single field\. It must be the same length as detailKeyFields/>|
|const|**detailKeyFields**|string|Key fields in the detail table that relate with the key fields in the master table\.<br />Must not be null, and normally will be an array with a single field\.|


## See also

* [TFlexCelReport](../TFlexCelReport/index.md)

# TFlexCelReport\.AddRelationship\(string, string, TArray\<string>, TArray\<string>\)
Adds a relationship between two tables\. Note that if your tables are datasets, or come from Entity Framework, or your master detail tables are nested, you probably don't need to call this method\. FlexCel will detect the relationships automatically and use them\. This method is only for when you have custom data with no DataRelationships \(as in a dataset\) and where detail tables are not nested to the master \(as in Entity Framework\)\.


## Remarks

You might use this method before adding the tables with AddTable\. Tables must exist when running the report, not when adding the relationship\.

## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelReport/index.md">TFlexCelReport</a>.AddRelationship(const masterTable: string; const detailTable: string; const masterKeyFields: TArray&lt;string&gt;; const detailKeyFields: TArray&lt;string&gt;); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**masterTable**|string|Master table for the relationship\.|
|const|**detailTable**|string|Detail table for the relationship\.|
|const|**masterKeyFields**|TArray\<string>|Key fields in the master table that relate with the key fields in the detail table\.<br />Must not be null, and normally will be an array with a single field\. It must be the same length as detailKeyFields/>|
|const|**detailKeyFields**|TArray\<string>|Key fields in the detail table that relate with the key fields in the master table\.<br />Must not be null, and normally will be an array with a single field\.|


## See also

* [TFlexCelReport](../TFlexCelReport/index.md)

