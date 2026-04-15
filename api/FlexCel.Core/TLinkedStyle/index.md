---
uid: TLinkedStyle
description: TLinkedStyle
---

# TLinkedStyle Record

This class is used as a part of a [TFlxFormat](../TFlxFormat/index.md) class, and stores how a cell format is linked to a style\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TLinkedStyle = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Assign](Assign.md)|Copies a new style into this object\.<br />|
|[SameData](SameData.md)|Returns true if the 2 instances have the same data\.<br />|
|[Clone](Clone.md)|Returns a deep copy of the object\.<br />|
|[Equals](Equals.md)|Returns true if obj and this object have the same value\.<br />|
|[GetHashCode](GetHashCode.md)|Returns a hashcode for this object\.<br />|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


## Properties

|Name|Description|
|---|---|
|[AutomaticChoose](AutomaticChoose.md)|When this property is true \(the default\) FlexCel will automatically choose which linked properties to apply depending on what changes from the base style\. For example, if this style has a different font than the basic style, the font will be not linked, and when you change the base style it will keep the same\.<br />Excel behaves this way when it adds styles\. To manually choose what the format will affect, set this to none\.<br />This property doesn't correspond with any Excel property, and it is not stored in the file\.<br />|
|[LinkedNumericFormat](LinkedNumericFormat.md)|If true, the numeric format will be linked to the parent style, and it will change when you change the style\.<br />If false the numeric format will not change even if you change it in the base style\.<br />**Note that this property has no effect unless [AutomaticChoose](AutomaticChoose.md) is false\.**|
|[LinkedFont](LinkedFont.md)|If true, the font will be linked to the parent style, and it will change when you change the style\.<br />If false the font will not change even if you change it in the base style\.<br />**Note that this property has no effect unless [AutomaticChoose](AutomaticChoose.md) is false\.**|
|[LinkedAlignment](LinkedAlignment.md)|If true, the alignment will be linked to the parent style, and it will change when you change the style\.<br />If false the alignment not change even if you change it in the base style\.<br />**Note that this property has no effect unless [AutomaticChoose](AutomaticChoose.md) is false\.**|
|[LinkedBorder](LinkedBorder.md)|If true, the border will be linked to the parent style, and it will change when you change the style\.<br />If false the border will not change even if you change it in the base style\.<br />**Note that this property has no effect unless [AutomaticChoose](AutomaticChoose.md) is false\.**|
|[LinkedFill](LinkedFill.md)|If true, the fill pattern will be linked to the parent style, and it will change when you change the style\.<br />If false the fill pattern will not change even if you change it in the base style\.<br />**Note that this property has no effect unless [AutomaticChoose](AutomaticChoose.md) is false\.**|
|[LinkedProtection](LinkedProtection.md)|If true, the protection will be linked to the parent style, and it will change when you change the style\.<br />If false the protection will not change even if you change it in the base style\.<br />**Note that this property has no effect unless [AutomaticChoose](AutomaticChoose.md) is false\.**|


