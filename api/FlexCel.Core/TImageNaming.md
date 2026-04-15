---
uid: TImageNaming
description: TImageNaming
---

# TImageNaming Enumeration

Defines how images will be automatically named by FlexCel, when you do not supply a better name\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|Default|0|The image will be named using standard naming, in a format similar to "filename\_image\_n\.png"|
|Guid|1|The image will be named using a GUID\. This ensures that any image will be unique even if you have many users requesting the same file at the same time\. \(Default naming will use the same name for all the users, so images would be overwritten\)\.<br />As a downside, everytime an image is called a new file will be created, so you can get a lot of images just from a user refreshing a page\.<br />|


