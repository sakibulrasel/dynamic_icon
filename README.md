<!-- 
This README describes the package. If you publish this package to pub.dev,
this README's contents appear on the landing page for your package.

For information about how to write a good package README, see the guide for
[writing package pages](https://dart.dev/guides/libraries/writing-package-pages). 

For general information about developing packages, see the Dart guide for
[creating packages](https://dart.dev/guides/libraries/create-library-packages)
and the Flutter guide for
[developing packages and plugins](https://flutter.dev/developing-packages). 
-->

Insert Material Icon and FontAwesome icons dynamically in Flutter app when the icons are not known at compile time.

The version of font_awesome icons is: 6.1.0

## Features

<!-- TODO: List what your package can do. Maybe include images, gifs, or videos. -->

## Getting started

<!-- TODO: List prerequisites and provide or point to information on how to -->
<!-- start using the package. -->

## Usage

Add dynamic_icons to pubspec.yaml
All icons namse should be in the same format you can find on https://api.flutter.dev/flutter/material/Icons-class.html and fontawesome.com  (e.g. add)

```dart
import 'package:flutter/material.dart';
import 'package:dynamic_icons/dynamic_icons.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({Key? key}) : super(key: key);
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Dynamic Icon',
      theme: ThemeData(

        primarySwatch: Colors.blue,
      ),
      home: const MyHomePage(title: 'Dynamic Icon Example'),
    );
  }
}

class MyHomePage extends StatefulWidget {
  const MyHomePage({Key? key, required this.title}) : super(key: key);

  @override
  State<MyHomePage> createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {


  @override
  Widget build(BuildContext context) {


    var iconList = [
      {
        "title":"Help",
        "iconName":"help"
      },
      {
        "title":"Search",
        "iconName":"search"
      },
      {
        "title":"Account",
        "iconName":"account_balance"
      },
      {
        "title":"Add",
        "iconName":"add"
      },
      {
        "title":"Alarm",
        "iconName":"alarm"
      },
      {
        "title":"Apps",
        "iconName":"apps"
      },
      {
        "title":"Bike",
        "iconName":"bike_scooter"
      },
      {
        "title":"Call",
        "iconName":"call"
      },
      {
        "title":"Camera",
        "iconName":"camera_rear"
      }
    ];
    return Scaffold(
      appBar: AppBar(
        title: Text("Dynamic Icons"),
      ),
      body: ListView.builder(
        itemCount: iconList.length,
          itemBuilder: (ctx,index){
            return Card(
              child: ListTile(
                title: Text(iconList[index]['title']??""),
                leading: DynamicIcons.getIconFromName(iconList[index]['iconName']??""),
              ),
            );
          }
      ),

    );
  }
}
```

## Additional information

References
  https://pub.dev/packages/font_awesome_flutter


