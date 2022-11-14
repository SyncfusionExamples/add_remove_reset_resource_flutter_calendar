# How to add, remove, update the resources in the Flutter Calendar (SfCalendar)?

This example demonstrates how to add, remove, update the resources in the Flutter Calendar (SfCalendar).

In the Flutter event calendar, you can dynamically insert, remove, and reset the resource by using the insert(), remove(), and reset() methods.

## Add, remove and updating the resources in the calendar

By using the button click, you can use the insert(), remove(), and clear() methods to add, delete, and reset resources to the resource collection. You can also use the notifyListeners to notify the calendar UI of any changes.

```

TextButton(child: const Text('Insert resource'),onPressed: ()
{
final CalendarResource resource = CalendarResource(
displayName: 'Sophia',
color: Colors.red,
id: '0004',
);
_employeeCollection.insert(2, resource);
_events!.notifyListeners(
CalendarDataSourceAction.addResource,
<CalendarResource>[resource]);

},),

TextButton(child: const Text('Remove resource'),onPressed: ()
{
final CalendarResource resource = _employeeCollection[0];
_employeeCollection.remove(resource);
_events!.notifyListeners(
CalendarDataSourceAction.removeResource,
<CalendarResource>[resource]);

},),
TextButton(child: const Text('Reset resource'),onPressed: ()
{
_employeeCollection = <CalendarResource>[];
_events!.resources!.clear();
_employeeCollection.add(CalendarResource(
displayName: "Sophia",
id: '0004',
color: Colors.green

));

_events!.resources!.addAll(_employeeCollection);
_events!.notifyListeners(
CalendarDataSourceAction.resetResource,
_employeeCollection);

},),

```

You can also refer our UG documentation to know more about [Resource](https://help.syncfusion.com/flutter/calendar/resource-view) support in the Flutter calendar.


## Requirements to run the demo
* [VS Code](https://code.visualstudio.com/download)
* [Flutter SDK v1.22+](https://flutter.dev/docs/development/tools/sdk/overview)
* [For more development tools](https://flutter.dev/docs/development/tools/devtools/overview)

## How to run this application
To run this application, you need to first clone or download the ‘create a flutter maps widget in 10 minutes’ repository and open it in your preferred IDE. Then, build and run your project to view the output.

## Further help
For more help, check the [Syncfusion Flutter documentation](https://help.syncfusion.com/flutter/introduction/overview),
 [Flutter documentation](https://flutter.dev/docs/get-started/install).