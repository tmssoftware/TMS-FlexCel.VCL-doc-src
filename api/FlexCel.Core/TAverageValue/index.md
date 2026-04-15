---
uid: TAverageValue
description: TAverageValue
---

# TAverageValue Record

This class is for internal use\. It is used to calculate an average over a range of cells\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TAverageValue = record;</code></pre>

## Fields

|Name|Description|
|---|---|
|[Sum](Sum.md)|Contains the sum of the cells\. The average is the Sum / ValueCount|
|[ValueCount](ValueCount.md)|Contains the number of cells\. The average is the Sum / ValueCount|


## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new TAverageValue|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


