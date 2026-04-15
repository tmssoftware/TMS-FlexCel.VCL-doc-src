---
uid: TCompressionLevel
description: TCompressionLevel
---

# TCompressionLevel Enumeration

This specifies how much the xlsx or pdf files must be compressed\. The bigger compression ratio, the slower it will be to generate the files\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|Optimal|0|Default zip compression\. This is the recommended setting\.<br />|
|Fastest|1|Fastest compression\. Low compression ratio\.<br />|
|NoCompression|2|No Compression is used at all\.<br />|
|Maximum|3|Maximum compression\. Normally not worth it because the compression ratio is almost the same as optimal but it is much slower\.<br />|


