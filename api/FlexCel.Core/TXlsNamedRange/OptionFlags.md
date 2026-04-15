---
uid: TXlsNamedRange.OptionFlags
description: TXlsNamedRange.OptionFlags
---

# TXlsNamedRange.OptionFlags Field

Options of the range\. You can access the options by using the corresponding properties\. \(Hidden, BuiltIn, etc\)\.

You can use this property to set them all at the same time\.

You can get the properties by OR'ing the following values:

01\. Name is hidden\. Corresponds to the property [Hidden](Hidden.md)\.

02\. Name is a function\. Corresponds to the property [FunctionDef](FunctionDef.md)\.

04\. Name is a VB procedure\. If set you also need to set 08 \(name is a macro\)\. Corresponds to the property [VisualBasicProc](VisualBasicProc.md)\.

08\. Name is a Macro\. Corresponds to the property [Proc](Proc.md)\.

16\. Name returns an Array\. Corresponds to the property [CalcExp](CalcExp.md)\.

32\. Name is a BuiltIn name \(like Print\_Area\)\. Corresponds to the property [BuiltIn](BuiltIn.md)\.

8192\. Name will be published when exporting to html\. Corresponds to the property [PublishToServer](PublishToServer.md)\.

16384\. Indicates that the name is used as a workbook parameter  on a version of the workbook that is published to or rendered on a Web or application server\.
Corresponds to the property [WorkbookParameter](WorkbookParameter.md)\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs"><a href="../TXlsNamedRange/index.md">TXlsNamedRange</a>.OptionFlags: Integer;</code></pre>

## See also

* [TXlsNamedRange](../TXlsNamedRange/index.md)

