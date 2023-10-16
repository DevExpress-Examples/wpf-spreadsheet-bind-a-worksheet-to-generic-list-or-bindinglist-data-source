<!-- default badges list -->
![](https://img.shields.io/endpoint?url=https://codecentral.devexpress.com/api/v1/VersionRange/128612819/21.1.5%2B)
[![](https://img.shields.io/badge/Open_in_DevExpress_Support_Center-FF7200?style=flat-square&logo=DevExpress&logoColor=white)](https://supportcenter.devexpress.com/ticket/details/T484261)
[![](https://img.shields.io/badge/📖_How_to_use_DevExpress_Examples-e9f6fc?style=flat-square)](https://docs.devexpress.com/GeneralInformation/403183)
<!-- default badges end -->

# WPF Spreadsheet: How to Bind a Worksheet to a Generic List or a BindingList Data Source

This example demonstrates the use of **List<T>**, **BindingList<T>**, and **ReadOnlyCollection<T>** objects as data sources to bind data to the worksheet range.

![image](./media/fcc6c28f-f517-11e6-80bf-00155d62480c.png)

## Implementation Details

The [WorksheetDataBindingCollection.BindToDataSource](https://docs.devexpress.com/OfficeFileAPI/devexpress.spreadsheet.worksheetdatabindingcollection.bindtodatasource.overloads) method is called to create the binding.

The [ExternalDataSourceOptions](https://docs.devexpress.com/OfficeFileAPI/DevExpress.Spreadsheet.ExternalDataSourceOptions) object specifies various data binding options. A custom converter with the [IBindingRangeValueConverter](https://docs.devexpress.com/OfficeFileAPI/DevExpress.Spreadsheet.IBindingRangeValueConverter) interface converts weather data between the data source and a worksheet. 

If the data source does not allow modification (`ReadOnlyCollection<T>`), the binding worksheet range also prevents modification. To modify the data obtained from the read-only data source, use the [WorksheetExtensions.Import](https://docs.devexpress.com/OfficeFileAPI/devexpress.spreadsheet.worksheetextensions.import.overloads) method instead of data binding.

> [!note]
> The use of the `WorksheetExtensions.Import` method in production code (and referencing the **DevExpress.Docs** assembly) requires a license to the DevExpress Document Server or the DevExpress Universal Subscription.

Data binding error fires the `WorksheetDataBinding.Error` event and cancels the data update. The event handler in this example displays a message containing the error type.

## Files to Review


| C# | Visual Basic |
|---------|----------|
| [MainWindow.xaml](./CS/DataBindingToListExample/MainWindow.xaml) | [MainWindow.xaml](./VB/DataBindingToListExample/MainWindow.xaml) |
| [MainWindow.xaml.cs](./CS/DataBindingToListExample/MainWindow.xaml.cs) | [MainWindow.xaml.vb](./VB/DataBindingToListExample/MainWindow.xaml.vb) |
| [MyConverter.cs](./CS/DataBindingToListExample/MyConverter.cs) | [MyConverter.vb](./VB/DataBindingToListExample/MyConverter.vb) |
| [WeatherReport.cs](./CS/DataBindingToListExample/WeatherReport.cs) | [WeatherReport.vb](./VB/DataBindingToListExample/WeatherReport.vb) |

## Documentation

* [Data Binding in Spreadsheet for WPF](https://docs.devexpress.com/WPF/117685/controls-and-libraries/spreadsheet/data-binding)
