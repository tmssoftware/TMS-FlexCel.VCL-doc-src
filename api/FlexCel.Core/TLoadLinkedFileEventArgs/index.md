---
uid: TLoadLinkedFileEventArgs
description: TLoadLinkedFileEventArgs
---

# TLoadLinkedFileEventArgs Class

Arguments passed on [TWorkspace.LoadLinkedFile](../TWorkspace/LoadLinkedFile.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TLoadLinkedFileEventArgs = class(EventArgs);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new Argument\.<br />|


## Properties

|Name|Description|
|---|---|
|[FileName](FileName.md)|The filename of the file we need\. **Note:** The path of this filename is relative to where the parent file is\.<br />you might need to add the main path to it in order to load the files\.<br />|
|[Xls](Xls.md)|Use this parameter to return the ExcelFile that corresponds with [FileName](FileName.md)\.  If you return null here, it means that the file was not found and it will result in \#REF errors in the formulas that reference that file\.<br />|


