---
uid: APIDocumentation
---

# API Documentation

In this section you can find a list of all the classes, methods and properties
available in FlexCel.


Below is a list of all the *namespaces* that you can use. Each namespace contains a list of the classes it contains, 
and each class contains a list of its members.

> [!Note]
> 
> We define *namespace* in Delphi
> as a collection of units which you can use with a single line. So for example, to use any of the types
> in the namespace `FlexCel.Core` you would write `uses unit1, unit2, ..., FlexCel.Core, ...`


## In this section:

#### [FlexCel.AddinFunctions](FlexCel.AddinFunctions/index.md)
The functions in this namespace are implementation of standard Addin functions included with FlexCel\. They are used by the recalculating engine, and while you could use them on their own, they are designed to be called by FlexCel\.


#### [FlexCel.Core](FlexCel.Core/index.md)
Core types and utilities used by FlexCel\.


#### [FlexCel.Pdf](FlexCel.Pdf/index.md)
This is a low level PDF engine\. It provides an API similar to GDI\+ to generate pdf files\. isn't Excel related and you can use it on its own\. It is used by FlexCel\.Render to convert xls/x files into PDF\.


#### [FlexCel.Preview](FlexCel.Preview/index.md)
This unit implements a viewer for xls or xlsx files\. The viewer is similar to the one in Excel's "Print Preview" and will show a list of the pages to be printed\. This unit is used automatically when you drop a [TFlexCelPreviewer](FlexCel.Preview/TFlexCelPreviewer/index.md) component\.


#### [FlexCel.Render](FlexCel.Render/index.md)
This is the rendering engine\. It can render an xls or xlsx file into an image, pdf or html files\.


#### [FlexCel.Report](FlexCel.Report/index.md)
This is the FlexCel reporting engine\. You need to use this unit when using the class TFlexCelReport\.


#### [FlexCel.XlsAdapter](FlexCel.XlsAdapter/index.md)
This is the Engine to natively generate and read xls or xlsx files\. You will normally want to use this file\.






> [!Note]
> 
> Every public type and method is documented, so if you are looking for a method and can't find it here,
> it is likely a method for internal use only.

