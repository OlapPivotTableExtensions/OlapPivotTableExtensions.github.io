---
description: "A feature which retrieves the detailed error message behind #VALUE! in a PivotTable"
---
## View #VALUE! Error Message

A PivotTable may contain one or more cells which contain error messages. Unfortunately, Excel does not expose the error message causing the error. OLAP PivotTable Extensions version 0.8.1 adds a feature which allows you to see the error message:

![](View%20Error%20Message_ViewError.png)

Behind the scenes, an MDX query is constructed to query that one cell and the error message is capture. Then the error message is displayed:

![](View%20Error%20Message_ValueErrorMessage.png)

#### Cell Error Mode Connection String Property Alternative
An alternative to using OLAP PivotTable Extensions is to use the Cell Error Mode connection string property which works with Analysis Services 2008 R2 and newer. This connection string property is described [here](http://www.powerpivot-info.com/post/411-changing-how-powerpivot-handles-dax-errors) and applies to PowerPivot, Multidimensional models, and Tabular models. For example, changing the connection string and adding the following will display the error message inline in the PivotTable:

`;Cell Error Mode=TextValue`