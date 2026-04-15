# How to get the hyperlink in a given cell?

Different from other cell properties like the background color, Excel hyperlinks are not stored tied to any cell. In fact, hyperlinks can cover more than one cell: you might have a hyperlink covering a range from A1 to C2 and the link will trigger if any of those cells is clicked.

So hyperlinks are stored in a list, and in FlexCel you have methods to know the number of hyperlinks ([TExcelFile.HyperLinkCount](~/api/FlexCel.Core/TExcelFile/HyperLinkCount.md)), to retrieve the range of cells one hyperlink in the list applies to ([TExcelFile.GetHyperLinkCellRange](~/api/FlexCel.Core/TExcelFile/GetHyperLinkCellRange.md)) and of course to get the information on the link like the url where it goes ([TExcelFile.GetHyperLink](~/api/FlexCel.Core/TExcelFile/GetHyperLink.md))

If you wanted to know if say cell A3 has a hyperlink, a way to find out would be to loop from 1 to HyperLinkCount and call GetHyperLinkCellRange in each entry of the list. If the range contains A3, you have found the hyperlink, and you can now call GetHyperLink to get the url of it.

But of course, this can be very slow, if you have thousands of links and you want to get the links in cell A2, A3, A4... For each one of the cells, you would be looping over all the list to find the correct links.

What we need here is an indexed search, so you spend O(Ln) instead of O(n) in each search. But as the search is in 2 dimensions (rows and columns) we need spatial indexing. Luckily, FlexCel offers a method [TExcelFile.LoopHyperLinks](~/api/FlexCel.Core/TExcelFile/LoopHyperLinks.md) that will do just that.

LoopHyperLinks will search for the links that apply to a range of cells, then call an anonymous method for every one of the links that apply. This will be much more efficient than a dumb loop over all links, since LoopHyperLinks internally holds a spatial index to locate the links efficiently.

Take a look at [TExcelFile.LoopHyperLinks](~/api/FlexCel.Core/TExcelFile/LoopHyperLinks.md) for a code example on how to get the links to a cell.
