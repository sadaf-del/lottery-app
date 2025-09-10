# lottery-app
import 'package:flutter/material.dart';
import 'dart:math';

void main() {
runApp(MyApp());
 }

   class MyApp extends StatefulWidget {
   const MyApp({Key? key}) : super(key: key);

 @override
   State<MyApp> createState() => _MyAppState();
  }

class _MyAppState extends State<MyApp> {
Random random = Random();
int x = 0;

@override
Widget build(BuildContext context) {
  return MaterialApp(
    debugShowCheckedModeBanner: false,
    home: Scaffold(
      appBar: AppBar(
        title: Text('Lottery App'),
        backgroundColor: Colors.blue,
      ),
      body: Column(
        mainAxisAlignment: MainAxisAlignment.center,
        crossAxisAlignment: CrossAxisAlignment.center,
        children: [
          Center(child: Text('Winning number is $x')),
          SizedBox(height: 10),
          Container(
            height: 250,
            decoration: BoxDecoration(
              color: Colors.grey.withOpacity(0.3),
              borderRadius: BorderRadius.circular(10),
            ),
            child: Padding(
              padding: const EdgeInsets.all(15.0),
              child: Column(
                children: [
                  SizedBox(height: 30),
                  Icon(Icons.error, size: 35, color: Colors.red),
                  SizedBox(height: 30),
                  Text('Better luck next time!\nYour number is $x.\nTry again.', textAlign: TextAlign.center,),
                ],
              ),
            ),
          ),
        ],
      ),
      floatingActionButton: FloatingActionButton(
        onPressed: () {
          setState(() {
            x = random.nextInt(10);
            print(x);
            setState(() {});
          });
          },
        backgroundColor: Colors.blue,
        child: Icon(Icons.refresh),
      ),
    ),
  );
}
}
