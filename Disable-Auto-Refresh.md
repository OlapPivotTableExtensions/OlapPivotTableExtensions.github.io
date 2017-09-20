---
description: "A feature to temporarily prevent PivotTables from refreshing every time you make a change in Power Pivot"
---
### Disable Auto Refresh

New to release 0.8.3 is a feature to help with heavy Power Pivot users in Excel 2013. After every minor change in Power Pivot, all PivotTables refresh. This can be a huge time waster if you intend to make several Power Pivot model changes in a row. This scenario is described more fully in a [blog post by Greg Galloway](http://www.artisconsulting.com/blogs/greggalloway/2014/4/2/wait-power-pivot-dont-refresh-yet-ive-got-more-changes). To avoid this delay after each Power Pivot change, right click on a PivotTable connected to Power Pivot (the built-in Excel Data Model) and choose Disable Auto Refresh:

![](Disable%20Auto%20Refresh_DisableAutoRefresh.png)

This feature disables auto refresh on all PivotTables connected to that Power Pivot model (until you re-enable refresh).

Starting with release 0.8.4, this feature also disables [DAX query tables](http://www.powerpivotblog.nl/implementing-histograms-in-excel-2013-using-dax-query-tables-and-powerpivot/) also known as [linkback tables](http://www.sqlbi.com/articles/linkback-tables-in-powerpivot-for-excel-2013) and sets the calculation mode to manual to disable refresh of all formulas, primarily CUBEVALUE type formulas that connect to Power Pivot.

Then make your batch of changes in Power Pivot. When you are done, right click the PivotTable again and choose Enable Auto Refresh:

!![](Disable%20Auto%20Refresh_EnableAutoRefresh.png)

Behind the scenes when you Enable Auto Refresh, it will trigger a refresh to PivotTables to update the field list and data in them. This could take some time if the model is complex, however this update was saved for the end of your batch of model changes.

While Auto Refresh is disabled, do use the Power Pivot window (the Manage button on the left of the Power Pivot tab) and do use the measures grid.
!![](Disable%20Auto%20Refresh_UseMeasuresGrid.png)

However, **avoid** attempting to add a new measure using the New Calculated Field dropdown:
!![](Disable%20Auto%20Refresh_DisableAutoRefreshAvoidCalcMenu.png)

If you attempt to use that New Calculated Field menu while Auto Refresh is disabled, you will get the error "Could not add the field 'Your calculation' to the PivotTable because the formula is invalid."
!![](Disable%20Auto%20Refresh_DisableAutoRefreshCalcMeasureError.png)

Note: This feature is only visible in Excel 2013 against PivotTables connected to the Excel Data Model (i.e. Power Pivot model).

Note: The December 2014 update of Excel 2013 includes some [significant stability improvements](http://blogs.msdn.com/b/powerbi/archive/2014/12/16/announcing-new-excel-2013-bi-stability-and-usability-improvements.aspx) and an enhancement that gets you about half of the way towards "Disable Auto Refresh" functionality. It disables auto-refresh of PivotTables while the Power Pivot window is in focus, but as soon as you remove focus from the Power Pivot window, it auto-refreshes. This improvement is a step in the right direction, but we still recommend using OLAP PivotTable Extensions Disable Auto Refresh functionality for very complex workbooks so that you can begin authoring a Power Pivot change, flip over to a PivotTable to double check the name of a measure or value (without waiting for the PivotTable to refresh) and then continue authoring the measure in Power Pivot.