# Tips and Tricks

An assorted list of small and interesting stuff to help you get the most out of FlexCel.

We will be adding new tips regularly here, so make sure to check this page from time to time.

## In this section:

#### [Avoiding "Too many rows" error messages](avoiding-too-many-rows.md)



Sometimes you can get a "too many rows" error when inserting a couple or rows in an empty file. We learn how this might happen.


#### [Font licensing](font-licensing.md)



Why is FlexCel complaining that I don't have the permissions to embed a font?

#### [Localized month names](localized-month-names.md)



Why you are not getting the same date strings as Excel. And while we are at it, we tell you what's a "genitive month name"

#### [Cloud fonts](cloud-fonts.md)



Excel is moving more and more to cloud fonts, and why that is bad news for the rest of us.


#### [VCL.FlexCel.Core vs FlexCel.VCLSupport](vcl-flexcel-core-vs-flexcel-vclsupport.md)



The same, yet different.

#### [Painting a full sheet black](painting-a-full-sheet-black.md)



Paint the columns, not the cells.


#### [Running FlexCel inside Docker containers](running-flexcel-inside-docker-containers.md)



A Docker container needs fonts!

#### [Text rotation in shapes inside xls and xlsx files](text-rotation-in-xls-and-xlsx.md)



Do we rotate the text first and then align it, or do we align it first?

#### [SVG files inside xlsx files](svg-files-inside-xlsx-files.md)



Modern Excel versions allow SVG as a file format for images inside. In this tip we explore the FlexCel support for the feature.

#### [The maximum used column on a sheet](the-maximum-used-column-on-a-sheet.md)



It all depends on what we define by "used column"

#### [Finding the actual fonts used when exporting to PDF](finding-the-actual-fonts-used-when-exporting-to-pdf.md)



When exporting to PDF, you need to find out which fonts are actually used.

#### [Scalable images in your documentation](scalable-images-in-your-documentation.md)



Did you know that you can use FlexCel's "Export as SVG" feature to get scalable images of your spreadsheets?


#### [Using Tokens to get information from formulas](using-tokens-to-get-information-from-formulas.md)



Let's imagine that you want to manually modify all formulas that refer to A1 to refer to A2. You could try some manual regex to search and replace all occurrences of "A1" by "A2" into the formula string. But of course this would replace also A11 by A21 and also do replacements in things that aren't references. Luckily FlexCel's Tokens provide a much more elegant and reliable solution to do it.

#### [Semi-absolute references](semi-absolute-references.md)



You know that a cell reference like "A4" is relative, while "$A$4" is absolute. But is there a way to have a reference be absolute when it is outside the range copied, and relative if it is inside?

#### [References in conditional formats and data validations](references-in-conditional-formats-and-data-validations.md)



Formulas inside conditional formats or data validations apply to a range of cells instead of a single cell. This makes them behave differently from regular cell formulas in ways that might not be obvious.

#### [Replacing a font by another in an Excel file](replacing-a-font-by-another-in-an-excel-file.md)



If you want to replace for example all Calibri fonts with a different font in a file, you can use the code in this tip.

#### [Finding out how many pages will be exported](finding-out-how-many-pages-will-be-exported.md)



Sometimes you want to know the number of pages needed for a report, before actually exporting or printing it.

#### [Fine-tuning row autofitting](fine-tuning-row-autofitting.md)



When autofitting rows, you might want to use [TExcelFile.CellMarginFactor](~/api/FlexCel.Core/TExcelFile/CellMarginFactor.md) besides adjustment.

#### [Understanding CSV files](understanding-csv-files.md)



There is no such thing as a "Universal CSV" which everyone can understand. To create a CSV file, you need to know who will be reading it.


#### [Embedding Excel files in your application](embedding-excel-files-in-your-application.md)



Don't use APIMate for this.


#### [Internal numeric formats](internal-numeric-formats.md)



Excel has some numeric formats that vary from locale to locale. Let's get a more in depth look under the covers.

#### [How to change the FlexCel locale](how-to-change-the-flexcel-locale.md)



Some numeric formats in Excel change depending on your machine locale. FlexCel will by default pick your locale from the machine configuration too, but you can change those without modifying the machine settings.

#### [Using barcodes](using-barcodes.md)



Here we discuss the different ways to embed a barcode in your file using FlexCel.

#### [How to get the hyperlink in a given cell?](how-to-get-the-hyperlink-in-a-given-cell.md)



Hyperlinks in a cell aren't as straightforward as other cell properties. Here we discuss how they work and how to get the link in some specific cell.

#### [Why are xlsx files generated by FlexCel smaller than the same files generated by Excel?](why-are-files-generated-by-flexcel-smaller.md)



You open an existing file with FlexCel and save it. Now the file is some kilobytes smaller. What is happening?

#### [Automatically opening generated Excel files](automatically-open-generated-excel-files.md)



Sometimes you might want to open the generated files directly in Excel without asking the user where to save them first. While this is not technically possible, in this tip we show a way to simulate it.

#### [Using strict xlsx files](using-strict-xlsx-files.md)



FlexCel supports both normal and strict xlsx files. Which one should you use?

#### [Finding out which FlexCel version you are using](finding-out-the-flexcel-version.md)



A simple code snippet to find out the version of FlexCel that you are using from inside your application.

#### [Sign your PDF files](sign-your-pdfs.md)



You are creating documents. How do you ensure that nobody alters the data on them?

#### [Conditionally format all things!](prefer-conditional-formats.md)



Whenever you need change the format of a cell depending on its value, conditional format is here to help.

#### [Expanding formulas in consecutive cells](expanding-formulas.md)


If there only was a simple way to enter "=B1" in A1 and "=B2" in A2...

We also tell you about a simple way to check if all the formulas in a range have consistent values (so the formula in A1 refers to B1, and the formula in A2 refers to B2 and so on)

#### [Changing the font name](changing-the-font-name.md)



Excel 2007 made changing the font name in a cell a little more complex than what it should be.

#### [Entering multiple lines of text inside a cell](multi-line-cells.md)



You can enter multiple lines of text inside a single cell, but there are a couple of things to be aware of.

#### [Understanding Excel measurement units](understanding-excel-measurement-units.md)



What does a column width of 8.44 actually mean?

#### [Dumping a Dataset into Excel](dumping-a-dataset.md)



I have my data in this dataset. How do I export it to Excel?

#### [Reading only the first row of a file](reading-first-row.md)



If you have lots of big files to analyze, you might not want to load the full files into memory just to check if you need to process them.



