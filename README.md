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
Container ვიჯეტი გამოიყენება ოთკუთხედი ფორმის ვიზუალური ეფექტის შესაქმნელად. Container ვიჯეტის საშვალებით ასევე შეგვიძლია სხვა ვიჯეტებს მივცეთ უკანა ფონი (background color), მარჯინები, პადინგები, სურათი უკანა ფონად, და ა.შ. სურათზე მოცემულია ყვითელი Container ვიჯეტი. Container ვიჯეტის ზომები დამოკიდებულია მის შვილ ვიჯეტზე ან/და Container ვიჯეტის width და height პარამეტრებზე.
იმ შემთხვევაში თუ კი Container ვიჯეტს არ ყავს შვილი ვიჯეტი და არ აქვს გაწერილი width და height პარამეტრი იგი იკავებს თავისუფალ ადგილს სრულად. თუკი Container ვიჯეტს გაწერილი აქვს შვილი ვიჯეტი და არ აქვს გაწერილი width და height პარამეტრი Container ვიჯეტი დაიკავებს იმხელა ადგილს რამხელაც მის შვილ ვიჯეტს სჭირდება. Container ვიჯეტის width და height პარამეტრებით შეგვიძლია მას მივანიჭოთ ჩვენთვის სასურველი ზომები იმის მიუხედავად ყავს თუ არა მას შვილი ვიჯეტი. ქვემოთ მოცემულია ვარიანტები სადაც
1. Container ვიჯეტს არ ყავს შვილი ვიჯეტი და არ აქვს გაწერილი width და height პარამეტრები<br />
<img src="/screenshots/contnosizenochild.jpg" width=300><br /><br />

```dart
home: Scaffold(
  appBar: AppBar(
    title: Text("My App"),
  ),
  body: Container(
    color: Colors.yellow,
  ),
),
```

2. Container ვიჯეტს არ აქვს გაწერილი width და height პარამეტრები თუმცა ყავს შვილი ვიჯეტი (Text ვიჯეტი)<br />
<img src="/screenshots/contchild.jpg" width=300><br /><br />

```dart
home: Scaffold(
  appBar: AppBar(
    title: Text("My App"),
  ),
  body: Container(
    color: Colors.yellow,
    child: Text("Flutter"),
  ),
),
```

3. Container ვიჯეტს ყავს შვილი ვიჯეტი თუმცა ასევე გაწერილი აქვს width და height პარამეტრები<br />

<img src="/screenshots/contchildandsize.jpg" width=300><br /><br />

```dart
home: Scaffold(
  appBar: AppBar(
    title: Text("My App"),
  ),
  body: Container(
    color: Colors.yellow,
    width: 100,
    height: 100,
    child: Text("Flutter"),
  ),
),
```

Container ვიჯეტი Flutter_ში გამოიყენება შვილი ვიჯეტებისათვის მარჯინებისა და პადინგების მისანიჭებლად. გვაქვს შესაბამისად margin და padding პარამეტრები.
მოცემულ სურათზე გვაქვს Text ვიჯეტი, რომელსაც Container ვიჯეტის დახმარებით გავუწერეთ 16 პადდინგი და 16 მარჯინი ოთხივე მხარეს.<br />
<img src="/screenshots/marginspaddings.jpg" width=300><br /><br />
მოცემული სურათის შესაბამისი კოდი ასე გამოიყურება

```dart
body: Container(
    color: Colors.yellow,
    margin: EdgeInsets.all(16),
    padding: EdgeInsets.all(16),

    child: Text("Flutter"),
  ),
),
```

Container ვიჯეტის margin და padding პარამეტრები "ელოდება" EdgeIsets. რომელიც გვაძლევს რამდენიმე ფუნქციაზე წვდომას .(წერტილი) ოპერატორის მეშვეობით.
ეს ფუნქციებია:

1. EdgeIsets.all(10) - all ფუნქცია მარჯინს (ან პადინგს) ამატებს ოთხივე მხარეს ფრჩხილებში მოცემული რიცხვის შესაბამისად. (10 ჩვენს მაგალითში).
2. EdgeIsets.only(left: 10, right: 20, top: 30, bottom: 40) - only ფუნქცია მარჯინს (ან პადინგს) ამატებს ერთ, ორ, სამ, ან ოთხივე მხარეს შესაბამისი მნიშვნელობით(ჩვენს მაგალითში - მარცხნივ: 10, მარჯვნივ - 20, და ა.შ.)
3. EdgeIsets.symmetric(horizontal: 10, vertical: 20) - symmetric ფუნქცია მარჯინს (ან პადდინგს) ამატებს ღერძებზე(ჰორიზონტალურზე ან ვერტიკალურზე). ჩვენს მაგალითში symmetric ფუნქცია დაამატებს 10 მარჯინს ან პადინგს მარჯვნივ და მარცხნივ. ხოლო ზემოთ და ქვემოთ 20_ს.
4. EdgeIsets.fromLTRB(10,20,30,40) - fromLTRB ფუნქცია საშვალებას გვაძლევს გვერდის სახელის მითითების გარეშე გავუწეროთ მარჯინი ან პადინგი. თუმცა ამ შემთხვევაში პარამეტრების მიმდევრობა მნიშვნელოვანია. პირველი პარამეტრი შეესაბამება left_ს, მეორე შეესაბამება top_ს, მესამე right_s და მეოთხე bottoms.

## Center

## Column

## Row

## StatelessWidget

## StatefulWidget

## TextButton  

## TextField