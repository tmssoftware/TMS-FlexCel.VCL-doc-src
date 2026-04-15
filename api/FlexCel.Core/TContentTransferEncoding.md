---
uid: TContentTransferEncoding
description: TContentTransferEncoding
---

# TContentTransferEncoding Enumeration

Defines how a part of a MIME message will be coded\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|QuotedPrintable|0|Use the Quoted Printable algorithm \(RFC 2045 section 6\.7\)\.<br />You will normally use this encoding for text\.<br />When using this option, you need to write the part content using [TMimeWriter.WriteQuotedPrintable](TMimeWriter/WriteQuotedPrintable.md)  or a similar method\.<br />|
|Base64|1|Use base64 algorithm \(RFC 2045 section 6\.7\)\.<br />You would normally use this encoding for binary files\.<br />When using this option, you need to write the part content using [TMimeWriter.WriteBase64](TMimeWriter/WriteBase64.md)  or a similar method\.<br />|


