---
uid: TMultipartType
description: TMultipartType
---

# TMultipartType Enumeration

Different ways to define a multipart archive\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|Related|0|Parts inside this container are related, for example this message could contain an HTML file and its external images\.<br />|
|Alternative|1|Parts inside this container are an alternative one from the other\. For example, a message could be sent in HTML and plain Text, once inside a different MIME part, and the mail reader should chose the best alternative of the parts to display\.<br />|
|Mixed|2|Parts inside this MIME container are not related, e\.g\. different attachments\.<br />|
|Digest|3|A compilation of messages, used in forwarded emails\.<br />|
|Signed|4|A part containing files and one signature\.<br />|


