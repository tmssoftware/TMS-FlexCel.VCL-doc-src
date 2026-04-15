---
uid: THtmlVersion
description: THtmlVersion
---

# THtmlVersion Enumeration

Defines the HTML version that will be used when exporting\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|Html\_401|0|The HTML generated will be 4\.01 strict\. See [http://www.w3.org/TR/html401/](http://www.w3.org/TR/html401/)|
|XHTML\_10|1|HTML generated will be XHTML 1\.0\. See [http://www.w3.org/TR/xhtml1/](http://www.w3.org/TR/xhtml1/)|
|Html\_32|2|Html generated will be compatible with 3\.2, and not have any CSS applied\. Useful for when you want simple html markup and don't worry too much about exact looking\. Many properties in FlexCelHtmlExport \(like ie6 transparent png support\) will be ignored in this mode\.<br />|
|Html\_5|3|The html generated will use specific stuff from HTML5, like the ability to rotate text or embed images\.<br />|


