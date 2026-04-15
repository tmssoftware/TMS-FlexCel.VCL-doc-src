---
uid: TPdfErr
description: TPdfErr
---

# TPdfErr Enumeration

Error Codes\. We use this and not actual strings to make sure all are correctly spelled\.


## Syntax

**Unit:** [FlexCel.Pdf](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|ErrInternal|0|Internal error\.<br />|
|ErrInvalidPngImage|1|The png image is corrupt, invalid, or not in a format FlexCel can understand\.|
|ErrInvalidPageSize|2|This PaperKind is not supported\. Please use a custom Paper size\.|
|ErrInvalidFont|3|The font file for this font is invalid\.<br />|
|ErrFontNotFound|4|The font was not found\.<br />|
|ErrFontNotSupported|5|The font is not supported by FlexCel\. Not a CCF or Truetype font\.<br />|
|ErrInvalidPageNumber|6|Invalid page number\.<br />|
|ErrTryingToSignStartedDocument|7|A pdf file must be signed before calling BeginDoc\.<br />|
|ErrNoDotsInSigName|8|Signature names cannot contain dots\.<br />|
|ErrSigningLengthToSmall|9|The estimated size for the signature was smaller than the final size\.<br />|
|ErrUnassingedSignerFactory|10|There is no signer associated with the signature\.<br />|
|ErrInvalidAllowedChanges|11|AllowedChanges value is invalid\.<br />|
|CannotAttachFilesInPDFA1OrA2|12|A PDF/A\-1 or PDF/A\-2 file can't have attached files\. Use PDF/A\-3 for allowing embedding files\.<br />|
|ErrInvalidUnicodeConversion|13|A glyph in the pdf file cannot be mapped back to an Unicode character\.<br />|


