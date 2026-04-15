---
uid: TTokenWhitespacePosition
description: TTokenWhitespacePosition
---

# TTokenWhitespacePosition Enumeration

Specifies where the whitespace is added in relation to the next token\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|BeforeToken|0|This is the normal case\. Whitespace is added before the next token\. The only case where this option is  not used is in the case of parentheses\.<br />|
|BeforeOpenParenthesis|1|A parenthesis token covers 2 different parentheses: the open and close ones\. So for parentheses, we need  2 different cases for whitespace\. BeforeOpenParenthesis is for the spaces before the opening parenthesis\.<br />You would use it for example in the formula '=    \("hello"\)'|
|BeforeClosingParenthesis|2|A parenthesis token covers 2 different parentheses: the open and close ones\. So for parentheses, we need  2 different cases for whitespace\. BeforeClosingParenthesis is for the spaces before the closing parenthesis\.<br />You would use it for example in the formula '=\("hello"     \)'|


