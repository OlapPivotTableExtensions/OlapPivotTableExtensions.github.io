---
description: "Excel 2013 improvements and what remaining OLAP PivotTable Extensions functionality is still useful. Describes the Excel Data Model and click-to-run installation"
canonical_url: 'https://olappivottableextensions.github.io/Excel-2013'
---
## Excel 2013

#### MDX Calculation GUI

Excel 2013 is the first version to support a GUI built by Microsoft for managing MDX calculated measures and members in a PivotTable. After clicking on a PivotTable, these features can be found under the PivotTable Tools... Analyze tab and under the OLAP Tools menu:

![](Excel%202013_Excel2013MDXMenu.png)

The MDX Calculated Measure dialog looks like:

![](Excel%202013_Excel2013CalculatedMeasure.png)

The MDX Calculated Member dialog lets you add a calculated dimension member:

![](Excel%202013_Excel2013CalculatedMember.png)

Finally, the Manage Calculations dialog looks like:

![](Excel%202013_Excel2013ManageCalculations.png)

The Excel Blog also covered this feature [here](http://blogs.office.com/b/microsoft-excel/archive/2012/10/15/calculated-member-and-measures-in-excel-2013.aspx).


#### Why Continue Using OLAP PivotTable Extensions?

As you can see, it greatly improves upon the calculation management UI from the OLAP PivotTable Extensions add-in by adding a very nice field list and function list. So why would you continue using OLAP PivotTable Extensions? Starting with release 0.8.0, OLAP PivotTable Extensions adds support for Excel 2013. The add-in also offers these other features:

* View PivotTable MDX
* [Filter PivotTable to a List](Filter-List)
* [Search](Search)
* Change PivotTable Defaults
* [Clear PivotTable Cache](Clear-PivotTable-Cache)
* [Show Property as Caption](Show-Property-As-Caption)
* [About Tab](About-Tab)
* [Upgrade PivotTable](About-Tab)
* [View #VALUE! Error Message](View-Error-Message)
* [Disable Auto Refresh](Disable-Auto-Refresh)
* [Choose Fields To Show](Choose-Fields-to-Show)


#### Excel Data Model

Excel 2013 natively integrates the xVelocity engine behind PowerPivot and allows loading multiple tables into what's known as the Excel Data Model. This is a built-in in-memory Analysis Services database which is deeply integrated into Excel 2013. Teo Lachev wrote up a good [overview](http://prologika.com/CS/blogs/blog/archive/2012/07/22/what-s-new-in-office-2013-bi-part-1-personal-bi-with-excel.aspx).

OLAP PivotTable Extensions v0.8.0 adds support for the Excel Data Model. (Disclaimer: The ability to connect to the Excel Data Model and/or PowerPivot from OLAP PivotTable Extensions is using unsupported APIs and as such the behaviour may change or stop working without notice in future releases. This functionality is provided on an "as-is" basis.) All OLAP PivotTable Extensions features are supported except:

* MDX calculated measures and members (as the Excel Data Model doesn't support this). Use PowerPivot to create DAX measures instead of using OLAP PivotTable Extensions to create MDX members.
* Clear PivotTable Cache (since the data is local and this feature doesn't make sense for the Excel Data Model)
* Change PivotTable Defaults (since "refresh on open" will cause Excel to reconnect to the SQL sources behind the Excel Data Model, potentially causing long delays upon workbook open. If you want to enable this option manually, the native Excel PivotTable Options dialog allows you to set this)
* Show Property as Caption (currently the Excel Data Model doesn't provide support for member properties)


#### Click-to-Run Support

Office 365 as part of the Office 2013 release supports a new install approach called [Click-to-Run](http://technet.microsoft.com/en-us/library/jj219420(v=office.15).aspx) (more information [here](http://blogs.office.com/b/office-next/archive/2012/08/27/click-to-run-and-office-on-demand.aspx)). OLAP PivotTable Extensions works in this scenario as soon as streaming installation is complete.
