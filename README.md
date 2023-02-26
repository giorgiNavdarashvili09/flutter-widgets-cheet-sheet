# flutter-widgets-cheet-sheet

იმისათვის რომ აქ მოცემული მაგალითების ემულატორზე/ტელეფონზე გატესტვა შევძლოთ შექმენით Flutter პრექტი და საწყისი კოდი main.dart ფაილში შეცვალეთ შემდეგით:

```
import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      home: ,
    );
  }
}


```
