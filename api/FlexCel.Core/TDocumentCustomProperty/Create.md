---
uid: TDocumentCustomProperty.Create
description: TDocumentCustomProperty.Create
---

# TDocumentCustomProperty\.Create Method

## Overloads

* [TDocumentCustomProperty\.Create\(string, string, Integer, string, TDocumentCustomPropertyType, string\)](#tdocumentcustompropertycreatestring-string-integer-string-tdocumentcustompropertytype-string)
* [TDocumentCustomProperty\.Create\(string, string, Integer, string, TDocumentCustomPropertyType, string, string\)](#tdocumentcustompropertycreatestring-string-integer-string-tdocumentcustompropertytype-string-string)

# TDocumentCustomProperty\.Create\(string, string, Integer, string, TDocumentCustomPropertyType, string\)
Creates a new instance of this object\. Don't call this overload if PropType is Unknown, since  in that case you also need to specify PropTypeStr

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TDocumentCustomProperty/index.md">TDocumentCustomProperty</a>.Create(const aName: string; const aFmtId: string; const aPId: Integer; const aLinkTarget: string; const aPropType: <a href="../TDocumentCustomPropertyType.md">TDocumentCustomPropertyType</a>; const aValue: string): <a href="../TDocumentCustomProperty/index.md">TDocumentCustomProperty</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aName**|string|See [Name](Name.md)\.|
|const|**aFmtId**|string|See [FmtId](FmtId.md)\.|
|const|**aPId**|Integer|See [PId](PId.md)\.|
|const|**aLinkTarget**|string|See [LinkTarget](LinkTarget.md)\.|
|const|**aPropType**|[TDocumentCustom&#8203;Property&#8203;Type](../TDocumentCustomPropertyType.md)|See [PropType](PropType.md)\.|
|const|**aValue**|string|See [Value](Value.md)\.|


## See also

* [TDocumentCustomProperty](../TDocumentCustomProperty/index.md)

# TDocumentCustomProperty\.Create\(string, string, Integer, string, TDocumentCustomPropertyType, string, string\)
Creates a new instance of this object\. Call this overload if PropType is Unknown, since  in that case you also need to specify PropTypeStr

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TDocumentCustomProperty/index.md">TDocumentCustomProperty</a>.Create(const aName: string; const aFmtId: string; const aPId: Integer; const aLinkTarget: string; const aPropType: <a href="../TDocumentCustomPropertyType.md">TDocumentCustomPropertyType</a>; const aValue: string; const aPropTypeStr: string): <a href="../TDocumentCustomProperty/index.md">TDocumentCustomProperty</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aName**|string|See [Name](Name.md)\.|
|const|**aFmtId**|string|See [FmtId](FmtId.md)\.|
|const|**aPId**|Integer|See [PId](PId.md)\.|
|const|**aLinkTarget**|string|See [LinkTarget](LinkTarget.md)\.|
|const|**aPropType**|[TDocumentCustom&#8203;Property&#8203;Type](../TDocumentCustomPropertyType.md)|See [PropType](PropType.md)\.|
|const|**aValue**|string|See [Value](Value.md)\.|
|const|**aPropTypeStr**|string|See [PropTypeStr](PropTypeStr.md)\.|


## See also

* [TDocumentCustomProperty](../TDocumentCustomProperty/index.md)

