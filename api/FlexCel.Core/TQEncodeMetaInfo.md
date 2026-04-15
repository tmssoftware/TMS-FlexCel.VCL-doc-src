---
uid: TQEncodeMetaInfo
description: TQEncodeMetaInfo
---

# TQEncodeMetaInfo Enumeration

Defines how a string returned by Q\-Encode will be handled\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|None|0|This will return the raw Q\-Encoded string, without "=?charset?encoding?" at the beginning or "?=" at the end\.<br />|
|Always|1|This will always return the Q\-Encoded string with "=?charset?encoding?" at the beginning and "?=" at the end\.<br />|
|OnlyIfNeeded|2|This will return the string with "=?charset?encoding?" only if the original string has special characters that need encoding,  if not it will return the original string without encoding\.<br />|


