---
uid: TTokenStructuredReference
description: TTokenStructuredReference
---

# TTokenStructuredReference Class

A reference for a cell in a table\. For example the reference in the formula =SUM\(Table1\[\[\#All\],\[SomeColumn\]\]\)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TTokenStructuredReference = class(<a href="../TToken/index.md">TToken</a>);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new Structured Reference argument token\.<br />|


## Properties

|Name|Description|
|---|---|
|[WorkbookName](WorkbookName.md)|Name of the file where the referenced table is\. If this value is empty, then the table  is in the same file as the reference\.<br />|
|[TableName](TableName.md)|Table that used by this reference\.<br />|
|[Sections](Sections.md)|The sections of the table where this reference applies\.<br />|
|[FirstColumn](FirstColumn.md)|First column where the reference applies\. Set it to empty if the reference applies to the whole table\.<br />|
|[LastColumn](LastColumn.md)|Last column where the reference applies\.<br />If empty and FirstColumn is empty too, then the reference applies to the whole table\.<br />If empty but FirstColumn is not empty, then this reference applies only to FirstColumn\.<br />|
|[SpaceAfterComma](SpaceAfterComma.md)|If true, the text of the structured reference arguments will include a space after every comma separating arguments\.<br />|
|[SpaceAfterBrackets](SpaceAfterBrackets.md)|If true, the text of the structure reference will include a space after the brackets which define the arguments\.<br />|


