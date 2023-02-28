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

სურათებში მოცემულია აპლიკაციების ეს ელემენტები <br />

<img src="/screenshots/appbar.jpg" width=300><br /><br />
<img src="/screenshots/bottom.jpg" width=300><br /><br />
<img src="/screenshots/floating.jpg" width=300><br /><br />




## AppBar
AppBar ვიჯეტი აპლიკაციის ზედა ნაწილში მყოფი ნავიგაციის ელემენტია. როგორც წესი AppBar ვიჯეტი შედგება აპლიკაციის სათაურისა და ერთი ან მეტი ღილაკისაგან (actions). AppBar ვიჯეტს ასევე შეიძლება ჰქონდეს ვიჯეტი დასაწყისში(მარცხნივ) როგორც წესი აპლიკაციის ლოგო, რომელზე დაჭერისასაც გადავდივართ მთავარ გვერდზე. სურათზე ქვემოთ მოცემულია აპლიკაცია სადაც AppBar ვიჯეტი შედგება: leading ვიჯეტისაგან(Home Icon), title Text ვიჯეტისაგან და ორი action ღილაკისაგან (search და setting იქონები)<br />
<img src="/screenshots/appbarfull.jpg" width=300><br /><br />
AppBar ვიჯეტის შესაბამისი კოდი კი ასე გამოიყურება

```dart
home: Scaffold(
  appBar: AppBar(
    leading: IconButton(onPressed: () {}, icon: Icon(Icons.home,),),
    title: Text("My App"),
    actions: [
      IconButton(
        icon: Icon(Icons.search),
        onPressed: () {
          // Perform search operation
        },
      ),
      IconButton(
        icon: Icon(Icons.settings),
        onPressed: () {
          // Perform add operation
        },
      ),
    ],
  ),
),

```


## Text
Text ვიჯეტი ერთერთი ყველაზე მარტივი და ხშირად გამოყენებადი Flutter ვიჯეტია. Text ვიჯეტის დანიშნულებაა დაარენდეროს(ეკრანზე ასახოს) მოცემული string_ი. Text ვიჯეტს ასევე შეუძლია ამ string_ის ფერის, ფონტის, ზომის, და სხვა მახასიათებლების კონტროლი.
Text ვიჯეტი პირველად AppBar ვიჯეტში ვნახეთ, სადაც მას წინასწარ განსაზღვრული სტილი აქვს(ფონტის ზომა, ფერი). ახლა ვნახოთ როგორ გამოიყურება Text ვიჯეტი Scaffold ვიჯეტის body პარამეტრში:<br />
<img src="/screenshots/text.jpg" width=300><br /><br />
მოცემული Text ვიჯეტის კოდი ასე გამოიყურება:

```dart
home: Scaffold(
  appBar: AppBar(
    title: Text("My App"),

  ),
  body: Text("Hello World"),
),
```

Text ვიჯეტს აქვს ერთი უსახელო პარამეტრი რომელიც ელოდება String მნიშვნელობას. Text ვიჯეტს ასევ აქვს style პარამეტრი, რომლის დახმარებითაც შეგვიძლია ტექსტის ფონტსი, ფერის, ზომის და სხვა მრავალი მახასიათებლის შეცვლა. სურათზე მოცემულია Text ვიჯეტი, რომლის ფონტის ზომა არის 22, ფერი კი ღია ცისფერი.<br />
<img src="/screenshots/textstyled.jpg" width=300><br /><br />

სურათზე მოცემული Text ვიჯეტის კოდი კი ასე გამოიყურება 

```dart
home: Scaffold(
  appBar: AppBar(
    title: Text("My App"),
  ),
  body: Text(
    style: TextStyle(
      fontSize: 22,
      color: Colors.blue,
    ),
    "Hello World",
  ),
),
```

## Container

## Center

## Column

## Row

## StatelessWidget

## StatefulWidget

## TextButton  

## TextField