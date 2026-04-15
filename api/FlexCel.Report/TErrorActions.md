---
uid: TErrorActions
description: TErrorActions
---

# TErrorActions Enumeration

Enumerates what to do on different FlexCel error situations\.


## Syntax

**Unit:** [FlexCel.Report](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|None|0|FlexCel will try to recover from most errors\.<br />|
|ErrorOnTooManyPageBreaks|1|When true and the number of manual pagebreaks is bigger than the maximum Excel allows, an Exception will be raised\. When false, the page break will be silently omitted\.<br />|


