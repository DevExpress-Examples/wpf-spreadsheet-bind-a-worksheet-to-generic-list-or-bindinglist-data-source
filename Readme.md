<!-- default badges list -->
![](https://img.shields.io/endpoint?url=https://codecentral.devexpress.com/api/v1/VersionRange/128612819/21.1.5%2B)
[![](https://img.shields.io/badge/Open_in_DevExpress_Support_Center-FF7200?style=flat-square&logo=DevExpress&logoColor=white)](https://supportcenter.devexpress.com/ticket/details/T484261)
[![](https://img.shields.io/badge/📖_How_to_use_DevExpress_Examples-e9f6fc?style=flat-square)](https://docs.devexpress.com/GeneralInformation/403183)
<!-- default badges end -->
<!-- default file list -->
*Files to look at*:

* [MainWindow.xaml](./CS/DataBindingToListExample/MainWindow.xaml) (VB: [MainWindow.xaml](./VB/DataBindingToListExample/MainWindow.xaml))
* [MainWindow.xaml.cs](./CS/DataBindingToListExample/MainWindow.xaml.cs) (VB: [MainWindow.xaml.vb](./VB/DataBindingToListExample/MainWindow.xaml.vb))
* [MyConverter.cs](./CS/DataBindingToListExample/MyConverter.cs) (VB: [MyConverter.vb](./VB/DataBindingToListExample/MyConverter.vb))
* [WeatherReport.cs](./CS/DataBindingToListExample/WeatherReport.cs) (VB: [WeatherReport.vb](./VB/DataBindingToListExample/WeatherReport.vb))
<!-- default file list end -->
# WPF Spreadsheet: How to bind a worksheet to a generic list or a BindingList data source


This example demonstrates the use of a <strong>List<T></strong>, <strong>BindingLIst<T></strong> and <strong>ReadOnlyCollection<T></strong> objects as data sources to bind data to the worksheet range. The <a href="http://help.devexpress.com/#CoreLibraries/DevExpressSpreadsheetWorksheetDataBindingCollection_BindToDataSourcetopic">WorksheetDataBindingCollection.BindToDataSource</a> method is called to create binding. <br>The <a href="http://help.devexpress.com/#CoreLibraries/clsDevExpressSpreadsheetExternalDataSourceOptionstopic">ExternalDataSourceOptions</a> object specifies various data binding options. A custom converter with the <a href="http://help.devexpress.com/#CoreLibraries/clsDevExpressSpreadsheetIBindingRangeValueConvertertopic">IBindingRangeValueConverter</a> interface converts weather data between the data source and a worksheet. <br>If the data source does not allow modification (ReadOnlyCollection<T>), the binding worksheet range also prevents modification. To modify the data obtained from the read-only data source, use the <a href="http://help.devexpress.com/#DocumentServer/DevExpressSpreadsheetWorksheetExtensions_Importtopic">WorksheetExtensions.Import</a> method instead of data binding. Note that the use of the <strong>WorksheetExtensions.Import</strong> method in production code (and referencing the <strong>DevExpress.Docs</strong> assembly) requires a license to the DevExpress Document Server or the DevExpress Universal Subscription.<br>Data binding error fire the <strong>WorksheetDataBinding.Error</strong> event and cancels data update. The event handler in this example displays a message containing the error type.<br><img src="https://raw.githubusercontent.com/DevExpress-Examples/wpf-spreadsheet-how-to-bind-a-worksheet-to-a-generic-list-or-a-bindinglist-data-source-t484261/16.2.5+/media/fcc6c28f-f517-11e6-80bf-00155d62480c.png">

<br/>


