---
uid: TBuiltInSignerFactory.Create
description: TBuiltInSignerFactory.Create
---

# TBuiltInSignerFactory\.Create Constructor

Creates a new instance of this class\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TBuiltInSignerFactory/index.md">TBuiltInSignerFactory</a>.Create(const aSigner: <a href="../../FlexCel.Core/TCmsSigner/index.md">TCmsSigner</a>);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aSigner**|[TCmsSigner](../../FlexCel.Core/TCmsSigner/index.md)|CmsSigner used to sign the pdf files\.<br />**IMPORTANT**: This class will take ownership of the signer and free it\.<br />You shouldn't free the signer yourself\.|


## See also

* [TBuiltInSignerFactory](../TBuiltInSignerFactory/index.md)

