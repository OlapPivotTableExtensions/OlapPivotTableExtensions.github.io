---
description: "An installation troubleshooting guide for the OLAP PivotTable Extensions add-in for Excel"
---
### Troubleshooting Installation and Connections

This page is the guide for troubleshooting installation and connection issues with OLAP PivotTable Extensions.

**Restarting Excel After Installation**

The first thing to try is to restart Excel. If you install OLAP PivotTable Extensions while Excel is open, it must be restarted. Close all Excel documents and close Excel. Then open Excel again to see if that solves the problem.


**Is Your PivotTable an OLAP PivotTable?**

If you click on the PivotTable then press Alt-F11 then Ctrl-G then paste the following into the Immediate window and press enter:

`?ActiveCell.PivotTable.PivotCache().OLAP`

Does it say True?

If not, then you PivotTable is a native PivotTable that's summarizing some table or other data in the spreadsheet or SQL table. You have to have an OLAP PivotTable (that is, one connected to an Analysis Services server) for my add-in to work.


**Repairing the OLAP PivotTable Extensions Installation**

Starting with Release 0.7.0, the installer should fix all of the issues listed below. (Update: Release 0.9.0 does not yet properly repair all of these problems listed below.) So if OLAP PivotTable Extensions is not working, try to repair the installation as follows, and that should fix the problem.

On Windows XP, go to Start... Settings... Control Panel... Add or Remove Programs. Click on OLAP PivotTable Extensions and click Change, on the next screen choose to Repair OLAP PivotTable Extensions, and click Finish.

On Windows 2003, go to Start... Control Panel... Add or Remove Programs. Click on OLAP PivotTable Extensions and click Change, on the next screen choose to Repair OLAP PivotTable Extensions, and click Finish.

On Windows Vista or Windows 2008, go to Start... Control Panel... Classic View... Programs and Features. Right click on OLAP PivotTable Extensions and click Change, on the next screen choose to Repair OLAP PivotTable Extensions, and click Finish.

On Windows 7, go to Start... Control Panel... Uninstall a program. Right click on OLAP PivotTable Extensions and click Change, on the next screen choose to Repair OLAP PivotTable Extensions, and click Finish.


**Manual Troubleshooting**

If you prefer to troubleshoot the installation manually, then use the following information and screenshots.


**Is It Disabled?**

The first thing to check is whether OLAP PivotTable Extensions is disabled. Click on the File button (in the top left) and choose Options. Click on the add-ins tab, then scroll down and see if OLAP PivotTable Extensions is disabled:

![](Troubleshooting%20Installation_AddInsDialog.png)

If it is disabled, then select "Disabled Items" from the Manage dropdown at the bottom and click Go. Then enable the add-in using this dialog:

![](Troubleshooting%20Installation_DisabledItems.png)

Then check whether the add-in is inactive using the following instructions.


**Is It Inactive?**

Then check whether OLAP PivotTable Extensions is inactive. Click on the Office button (in the top left in Excel) and choose Excel Options. Click on the add-ins tab, then scroll down and see if OLAP PivotTable extensions is in the inactive list:

![](Troubleshooting%20Installation_InactiveAddInsDialog.png)

If it is inactive, then select "COM Add-ins" from the Manage dropdown at the bottom and click Go. Then check OLAP PivotTable Extensions and click OK.

![](Troubleshooting%20Installation_ComAddInsDialog.png)

Then repeat the instructions above making sure it is now active, not inactive.



**Troubleshooting Connections**

* [Azure Analysis Services](https://docs.microsoft.com/en-us/azure/analysis-services/analysis-services-connect-excel) - OLAP PivotTable Extensions will strip User ID="" and Password="" from the connection string. It is OK if the User ID connection string property has your email address or UPN. It's OK if the Password connection string property has your password. But neither User ID or Password are required. OLAP PivotTable Extensions will popup a sign-in dialog if needed.
* [Power BI Analyze in Excel](https://docs.microsoft.com/en-us/power-bi/collaborate-share/service-analyze-in-excel) - OLAP PivotTable Extensions will popup a login dialog to allow you to sign into Power BI. Then it will use the resulting access token for connections to Analyze in Excel.
* [Power BI XMLA endpoints](https://docs.microsoft.com/en-us/power-bi/admin/service-premium-connect-tools) - A User ID must be specified. If the connection string says User ID="" then OLAP PivotTable Extensions will prompt you for your email address or UPN and add this to the connection string and then prompt for authentication to Power BI.
* All HTTP-type connections force use of TLS 1.2 as of OLAP PivotTable Extensions v0.9.6 but properly implemented to fully use TLS1.2 in v0.9.7
