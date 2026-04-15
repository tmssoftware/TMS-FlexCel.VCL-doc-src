---
uid: TPdfAllowedChanges
description: TPdfAllowedChanges
---

# TPdfAllowedChanges Enumeration

Changes allowed in a signed PDF document\.


## Syntax

**Unit:** [FlexCel.Pdf](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|None|0|No changes to the document are permitted; any change to the document invalidates the signature\.<br />|
|FillingForms\_PageTemplates\_Signing|1|Permitted changes are filling in forms, instantiating page templates, and signing; other changes invalidate the signature\.<br />|
|FillingForms\_PageTemplates\_Signing\_Annotations|2|Permitted are filling in forms, instantiating page templates, and signing, as well as annotation creation, deletion, and modification; other changes invalidate the signature|


