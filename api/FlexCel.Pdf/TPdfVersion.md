---
uid: TPdfVersion
description: TPdfVersion
---

# TPdfVersion Enumeration

Specifies the version of PDF that FlexCel will generate\.


## Syntax

**Unit:** [FlexCel.Pdf](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|v14|0|The files will be in Pdf 1\.4 format \(Acrobat 5\)\. Older Acrobat versions will still able to open the file, but might miss features like transparency\.<br />|
|v16|1|The files will be in Pdf 1\.6 format \(Acrobat 7\)\. This allows for smaller files, but older Acrobat versions won't be able to open the file at all\. You'll need Acrobat 7 or newer to see them\.<br />|
|v17|2|The files will be in Pdf 1\.7 format \(Acrobat 8\)\. You need Pdf 1\.7 to sign files with SHA512\. Since SHA1 is deprecated for signing, FlexCel will automatically choose v17 if the document is signed, no matter which version you manually select\.<br />|


