---
uid: IEffectProperties
description: IEffectProperties
---

# IEffectProperties Interface

A class encapsulating an effect that can be used for subtle, intense or moderate types\. This class can contain either a standard list of effects \(which you can access with EffectLst\) or a Directed Acyclic Graph \(DAG\)\.
One of EffectLst or EffectDag will always be null\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">IEffectProperties = interface(IInterface);</code></pre>

## Methods

|Name|Description|
|---|---|
|[Clone](Clone.md)|Returns a deep copy of the object\.<br />|
|[CompareTo](CompareTo.md)|**Overloaded<br />**  [CompareTo\(TObject\)](CompareTo.md#ieffectpropertiescomparetotobject)<br />  [CompareTo\(IEffectProperties\)](CompareTo.md#ieffectpropertiescomparetoieffectproperties)<br />|


## Properties

|Name|Description|
|---|---|
|[EffectLst](EffectLst.md)|Effect encapsulated by this class when it contains a list of effects\. If it contains a DAG, this property is null ans [EffectDag](EffectDag.md) will contain the DAG\.<br />|
|[EffectDag](EffectDag.md)|Effect encapsulated by this class when it contains a Directed Acyclic Graph of effects\. If it contains a list, this property is null ans [EffectLst](EffectLst.md) will contain the List\.<br />|
|[HasEffects](HasEffects.md)|Returns true if there are any effects\.<br />|
|[IsDag](IsDag.md)|Returns true if this class contains a DAG\. When true, [EffectDag](EffectDag.md) is not null\.<br />|


