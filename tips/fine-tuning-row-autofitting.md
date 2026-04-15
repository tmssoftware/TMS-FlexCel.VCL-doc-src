---
uid: FineTuningRowAutofitting
---
# Fine-tuning row autofitting.

As discussed in the [Api guide](xref:ApiDeveloperGuide#autofitting-rows-and-columns) *the text in Excel can change with the resolution or zoom of the printed page*, and what fits at one resolution might not fit at another.

The solution for that problem is to make the column or row big enough that it will fit at any resolution, and to do so, [TExcelFile.AutofitRow](~/api/FlexCel.Core/TExcelFile/AutofitRow.md) and [TExcelFile.AutofitCol](~/api/FlexCel.Core/TExcelFile/AutofitCol.md) have two parameters: "adjustment" and "adjustmentFixed"

Basically, if for example AutofitCol calculates that the needed column width is 9, then it will set the actual column width to 9 * adjustment + adjustment fixed.

If adjustment is 1.1 and adjutmentFixed is 0.2, then the column width will be set not to the 9 calculated, but to 9 * 1.1 + 0.2 = 10.1

Similarly, if the autofit engine calculates that the exact row height to fit some lines of text is 100, it will set the row height to 100 * adjustment + adjustmentFixed.

But rows and columns are not the same, and **autofitting rows is different from autofitting columns**. This is because we write horizontally from left to right (or right to left) and not from top to bottom. And adjustment and adjustmentFixed are not great for providing that extra margin when autofitting rows.

Let's imagine we are trying to fit the text "Hello World" into a column. As said, if we calculate that the width necessary to fit the text is 9, we will make the column 10.1 and so the text will fit anyway even if the resolution is different. 

But now, let's imagine that we want to autofit the row containing "Hello World". Same as with the column, we provide an adjustment, so the row will be a little larger than what it needs to be. But, at some resolutions "Hello World" might fit in one line inside the column:

<img alt = "hello world in one line" src = "../images/hello-world-in-one-line.png" width = "171" height = "57"/>

and at other resolutions it might break into "Hello" in the first line and "World" into the second line:

<img alt = "hello world in two lines" src = "../images/hello-world-in-two-lines.png" width = "169" height = "77"/>

It is a very small difference in the width of the text, but it causes the row height to double. We would need to have an adjustment of 2.0 to correctly display the text at any resolution. But an adjustment of 2.0 will make **all other lines twice as big as needed**. Adjustment alone is not a solution when fitting rows (as it is for fitting columns). 

To ensure the row with "Hello World" is always set to 2-line height, we need to reduce a little the effective width of the cell. 

Imagine for example that at resolution A "Hello World" is 9.9 inches long, but at resolution B it is 1.1 inches long. If the cell width is 10 inches, then at resolution A it will fit in one line, but at resolution B it will take 2 lines. But if we reduce the effective width of the cell from 10 inches to 9.8 inches, now no matter which resolution we use, it will always take 2 lines.

On the other hand, the text "Hello" is 0.5 inches long, so it fits always in one line at resolution A or B. We got what we wanted: "Hello" always fits in one line, "Hello World" always fits in 2 lines. 

In FlexCel, the way to reduce the effective width of the cell is using the property [TExcelFile.CellMarginFactor](~/api/FlexCel.Core/TExcelFile/CellMarginFactor.md)

So if you are having issues with autofitting rows at different resolutions, **you might want to set [TExcelFile.CellMarginFactor](~/api/FlexCel.Core/TExcelFile/CellMarginFactor.md) to a value like 1.1 before autofitting the rows**.

