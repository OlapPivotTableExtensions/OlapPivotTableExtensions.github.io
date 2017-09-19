### Filter List

A common scenario is having a list of items you wish to research in a PivotTable. You have this list of items in your clipboard, so instead of manually checking each item in the filter dropdown, you can use the Filter List feature from OLAP PivotTable Extensions.

If a field is on rows or columns in the PivotTable, you can right click on one of the members, look under the Filter menu, then select Filter List (a new command added by OLAP PivotTable Extensions):

![](Filter%20List_FilterListMenu.png)

Then the dialog comes up where you can paste in a list of items and filter that field to that list of items:

![](Filter%20List_FilterListDialog.png)

If a field contains a large number of members, then it may be very slow to drop it onto rows unfiltered. Instead, drop the field onto the PivotTable filters section, right click on the PivotTable, choose the OLAP PivotTable Extensions menu option, then flip to the Filter List tab and select the name of the field in question. Filter to a list. Then move that field to rows. It will maintain the filter you just set and will perform better than showing all members before filtering the PivotTable.

You are limited to filtering fields that are currently in the PivotTable on rows, columns, or filters.

Starting with release 0.7.2, clicking the Show Current Filters button will retrieve the current filters for that field. This is a great way to start from the current set of filters then add or remove a few selections.