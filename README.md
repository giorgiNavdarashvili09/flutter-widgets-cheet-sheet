# flutter-widgets-cheet-sheet

## რა არის ვიჯეტი?
Flutter_ში ვიჯეტი არის ის ელემენტები, რომლითაც "ვაშენებთ" მომხმარებლის ინტერფეისს (UI). ვიჯეტი შეიძლება იყოს მარტივი ვიზუალური ეფექტი (მაგალითად Text ვიჯეტი) ან შედარებით კომპლექსური ლეიაუთ-ვიჯეტი, რომელიც სხვა ვიჯეტების ეკრანზე სპეციფიურ განლაგებაში გვეხმარება(მაგალითად Column ვიჯეტი)<br /><br />


იმისათვის რომ აქ მოცემული მაგალითების ემულატორზე/ტელეფონზე გატესტვა შევძლოთ შექმენით Flutter პრექტი და საწყისი კოდი main.dart ფაილში შეცვალეთ შემდეგით:


```dart
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
      home: // მაგალითის კოდი,
    );
  }
}


```

## Scaffold

პირველი ვიჯეტი რომელსაც ჩვენ განვიხილავთ არის Scaffold ვიჯეტი. Scaffold ვიჯეტი არის Flutter გუნდის მიერ შექმნილი ვიჯეტი, რომელიც საშვალებას გვაძლევს ხშირად გამოყენებადი User Interface_ის ელემენტები მარტივად შევიტანოთ ჩვენს აპლიკაციაში. მაგალითად: <br />
1. AppBar - როგორც წესი აპლიკაციის ზედა ნაწილში მოთავსებული ელემენტი, რომელიც გვეხმარება : აპლიკაციის სათაურის ჩვენებაში, სხვადასხვა აპლიკაციის ძირითადი ფუნქციონალის მარტივად გამოსახვაში(notifications, messages, და სხვა...)
2. BottomNavigationBar - როგორც წესი მოცემულია აპლიკაციის ქვედა ნაწილში და გვაძლევს ნავიგაციის საშვალებას აპლიკაციის სხვადასხვა გვერდზე.
3. FloatingActionButton - როგორც წესი მოთავსებულია აპლიკაციის ქვედა მარჯვენა ნაწილში და მოცემული გვერდის მთავარ ფუნქციონალზე გვაძლევს სწრაფ წვდომას.(მაგალითად Gmail_ის აპლიკაციაში ახალი მეილის შექმნა)
4. Body - აპლიკაციის მთავარი ნაწილი სადაც სხვა ვიჯეტების დახმარებით ვაწყობთ User Interface_ს
<img src="/screenshots/appbar.jpg" width=300><br /><br />
<img src="/screenshots/bottom.jpg" width=300><br /><br />
<img src="/screenshots/floating.jpg" width=300><br /><br />

სურათებში მოცემულია აპლიკაციების ეს ელემენტები 


## AppBar

## Text

## Container

## Center

## Column

## Row

## StatelessWidget

## StatefulWidget

## TextButton  

## TextField