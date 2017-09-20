---
description: "The OLAP PivotTable Extensions About tab tells the user which version of OLAP PivotTable Extensions they are using and whether Excel is 32-bit or 64-bit. It also displays some troubleshooting information around Windows and Excel languages in use. If you want to report bugs or feature suggestions, follow the link provided, and be sure to include the version and language information in your bug report."
canonical_url: 'https://olappivottableextensions.github.io/About-Tab'
---
### About Tab

The About tab tells the user which version of OLAP PivotTable Extensions they are using and whether Excel is 32-bit or 64-bit. It also displays some troubleshooting information around Windows and Excel languages in use. If you want to report bugs or feature suggestions, follow the link provided, and be sure to include the version and language information in your bug report.

![img1](About%20Tab_AboutTab1.png)

The About tab also tells the user the PivotTable version and, if not the latest version, gives instructions on how to upgrade.

![img2](About%20Tab_AboutTab2.png)

#### Background on PivotTable Versions

As [this article](http://office.microsoft.com/en-us/excel-help/working-with-different-pivottable-formats-in-office-excel-HA010167298.aspx) describes, different functionality is available with different PivotTable versions. For example, some of the Excel APIs used by the Search tab are not supported on PivotTable versions older than 2007. This [article](https://blogs.office.com/en-us/2008/02/06/common-questions-around-excel-2007-olap-pivottables/) describes some specific functionality differences with calculated dimension members that depend on the PivotTable version.

If a PivotTable was created under an old version of Excel, or if a PivotTable was created in Excel 2007/2010/2013 while compatibility mode was on (i.e. when File... Options... Save files in this format... .xls is set), then a PivotTable may not be the current version. Upgrading generally involves saving the workbook as .xlsx and then refreshing the PivotTable, but the About tab will display any other atypical instructions about other scenarios (like if UpgradeOnRefresh has been disabled, etc.)
