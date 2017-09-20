---
description: "Explanation of a currently unsupported set of language settings in OLAP PivotTable Extensions"
canonical_url: 'https://olappivottableextensions.github.io/Unsupported-Language-Configuration'
---
## Unsupported Language Configuration

Starting with OLAP PivotTable Extensions version 0.7.4, language configurations are handled properly. Unfortunately, there is one niche scenario which it is impossible for OLAP PivotTable Extensions to support. We are at the mercy of two conflicting limitations. On one hand, if you do not have the Office Language Pack installed for your Windows Language set in the regional settings, Excel API calls may encounter an [Old format or invalid type library](http://support.microsoft.com/kb/320369) error, and the workaround is to set the CurrentCulture to the Excel UI language before making the API call which OLAP PivotTable Extensions does. However, when the "Retrieve data and errors in the Office display language when available" setting on the connection is unchecked, the PivotTable connects to Analysis Services using the Windows Language. When both of these scenarios occur at once, OLAP PivotTable Extensions warns you that you are running an unsupported language configuration. It is impossible for Excel API calls to avoid both the "Old format or invalid type library" error and the [LocaleIdentifier error](http://support.microsoft.com/kb/931388). The following table summarizes the supported language configurations:

Has installed Office Language Pack matching Windows Regional Settings? | Connection has Retrieve in Excel UI checked | Supported configuration
-----|-----|----
Yes | Yes | Yes
Yes | No | Yes
No | Yes | Yes
No | No | No

Because you are on this page, you are probably running an unsupported configuration. The About tab lists your language configuration and shows if it's unsupported. For example, on this machine the two Office Language Packs installed are English and Spanish. Since the Windows Language is set to French and that Office Language Pack isn't installed, and since the connection has "Retrieve data and errors in the Office display language when available" unchecked, this language configuration is unsupported:

![](Unsupported%20Language%20Configuration_UnsupportedLanguageConfiguration.png)

### Solutions

If you want to use OLAP PivotTable Extensions without errors, you must do one of the following:

* Install the [Office Language Pack](http://office.microsoft.com/en-us/language/) matching your current "Windows Language" as identified in the About dialog.
* Change the Windows Regional settings to a language for which you have an Office Language Pack installed. To change this, see the instructions below.
* Check "Retrieve data and errors in the Office display language when available" on each PivotTable connection.
* Include [LocaleIdentifier](http://support.microsoft.com/kb/931388) on the connection string as described in the workarounds section of a that KB article. Note that Locale Identifier (with a space) does work for Excel, but isn't visible to OLAP PivotTable Extensions. So use LocaleIdentifier (without a space). A list of LocaleIdentifier values can be found in the "LCID Dec" column of this [table](http://msdn.microsoft.com/en-us/goglobal/bb964664).
* Use the xllex.dll trick mentioned in Kim A's [comment](http://blogs.msdn.com/b/vsto/archive/2009/07/06/bug-old-format-or-invalid-type-library-error-when-automating-excel-christin-boyd.aspx#10144460)

Windows Regional Settings can be changed from Start... Control Panel... Clock, Language, and Region... Region and Language:
![](Unsupported%20Language%20Configuration_WindowsRegionalSettings.png)

To see which Office Language Packs are installed, go to Start... All Programs... Microsoft Office... Microsoft Office 2010 Tools... Microsoft Office 2010 Language Preferences, then look under Display Languages. In this screenshot, English and Spanish Language Packs are installed:
![](Unsupported%20Language%20Configuration_OfficeLanguagePacks.png)

If this LocaleIdentifier errors happens to you frequently, vote for this [Connect issue](https://connect.microsoft.com/SQLServer/feedback/details/721372/locale-identifier-bug) so the Analysis Services team knows to prioritize a resolution for this issue.

