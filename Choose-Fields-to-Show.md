---
description: "A feature which lets you quickly choose which levels to show in an OLAP PivotTable"
---
### Choose Fields to Show

In a PivotTable, Excel allows the user to hide or show individual levels from a multi-level hierarchy. However, hiding multiple levels can be a slow process since you must uncheck levels one at a time and the PivotTable refreshes after each level individually is hidden. The Choose Fields to Show feature of OLAP PivotTable Extensions was added in release 0.8.4 to address this pain point. It allows showing or hiding multiple fields at once.

To launch this feature, right click on a member of a hierarchy which is on rows or columns of a PivotTable, choose Show/Hide Fields... Choose Fields to Show...

![](Choose%20Fields%20to%20Show_ShowHideFields.png)

Then a dialog will pop up and allow you to check or uncheck multiple fields (levels) at once:

![](Choose%20Fields%20to%20Show_ChooseFieldsToShow.png)

Compared to the native Excel feature, not only is this feature fewer clicks, but performance is optimized to refresh the PivotTable as few times as possible.