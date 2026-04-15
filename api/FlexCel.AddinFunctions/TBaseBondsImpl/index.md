---
uid: TBaseBondsImpl
description: TBaseBondsImpl
---

# TBaseBondsImpl Class

Implements the basics for Bond functions, like CoupDays, CoupDaysNC, CoupDayBS, CoupNCD, CoupNum, CoupPCD\.


## Syntax

**Unit:** [FlexCel.AddinFunctions](../index.md)

<pre><code class="lang-delphi hljs">TBaseBondsImpl = class(<a href="../../FlexCel.Core/TUserDefinedFunction/index.md">TUserDefinedFunction</a>);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new implementation\.<br />|


## Methods

|Name|Description|
|---|---|
|[Calc](Calc.md)|Calculates the result depending on the specific function\.<br />|
|[PrevCoupon](PrevCoupon.md)|Returns the previous coupon for a given coupon\.<br />|
|[NextCoupon](NextCoupon.md)|Returns the next coupon after settlement date\.<br />|
|[LevelDayOfMonth](LevelDayOfMonth.md)|Makes the day in bonddate be as big Maturity date as possible\.<br />|
|[IsEOM](IsEOM.md)|Returns true if the date is the end of month\.<br />|
|[LastDayOfMonth](LastDayOfMonth.md)|Returns the last day of a month\.<br />|
|[Evaluate](Evaluate.md)|Evaluates the function\. Look At Excel docs for parameters\.<br />|


