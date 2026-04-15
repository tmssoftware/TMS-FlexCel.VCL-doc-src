---
uid: TDataValidationImeMode
description: TDataValidationImeMode
---

# TDataValidationImeMode Enumeration

The IME \(input method editor\) mode enforced by a data validation\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|NoControl|0|IME Mode Not Controlled\.<br /><br />Data validation does not control the IME control's mode\.<br />|
|Off|1|IME Off\.<br /><br />Forces the IME control to be off when first selecting the cell \(goes to direct cell input mode\)\.<br />|
|On|2|IME On\.<br /><br />Forces the IME control to be on when first selecting the cell\.<br />|
|Disabled|3|IME mode is disabled\.<br /><br />Forces the IME control to be disabled when this cell is selected\.<br />|
|Hiragana|4|Hiragana IME Mode\.<br /><br />Forces the IME control to be on and in Hiragana input mode when first selecting the cell\. Applies when the application's language is Japanese and a Japanese IME control is selected|
|FullKatakana|5|Full Katakana IME Mode\.<br /><br />Forces the IME control to be on and in full\-width Katakana input mode when first selecting the cell\. Applies when the application's language is Japanese and a Japanese IME control is selected\.<br />|
|HalfKatakana|6|Half\-Width Katakana\.<br /><br />Forces the IME control to be on and in half\-width Katakana input mode when first selecting the cell\. Applies when the application's language is Japanese and a Japanese IME control is selected\.<br />|
|FullAlpha|7|Full\-Width Alpha\-Numeric IME Mode\.<br /><br />Forces the IME control to be on and in full\-width alpha\-numeric input mode when the cell is first selected\.<br />|
|HalfAlpha|8|Half Alpha IME\.<br /><br />Forces the IME control to be on and in half\-width alpha\-numeric input mode when the cell is first selected\.<br />|
|FullHangul|9|Full Width Hangul\.<br /><br />Forces the IME control to be on and in full\-width Hangul input mode when first selecting the cell\. Applies when the application's language is Korean and a Korean IME control is selected\.<br />|
|HalfHangul|10|Half\-Width Hangul IME Mode\.<br /><br />Forces the IME control to be on and in half\-width Hangul input mode when first selecting the cell\. Applies when the application's language is Korean and a Korean IME control is selected\.<br />|


