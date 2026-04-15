---
uid: TEncryptionType
description: TEncryptionType
---

# TEncryptionType Enumeration

How the file is encrypted\. This applies only to xls files\. Xlsx files are encrypted using the Agile xlsx encryption\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|XorEncryption|0|Excel 95 XOR encryption\.<br />|
|Standard|1|Excel 97/2000 encryption\.<br />|
|Strong|2|Excel XP/2003 encryption\. Note that despite the name, this mode has multiple known  vulnerabilities and it is just marginally better than TEncryptionType\.Standard\.<br />Both use RC4 algorithm to encrypt, which is weak\. If you need files to be really secure, you need to use xlsx \(which supports AES\), not xls\.<br />|


