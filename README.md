//TASK NO.1:

import 'package:flutter/material.dart';

void main() {

runApp(const MyApp());

}

class MyApp extends StatelessWidget {

const MyApp({super.key});

@override

Widget build(BuildContext context) {

return MaterialApp(

home: ChessBoard(),

);

}

}

class ChessBoard extends StatelessWidget {

@override

Widget build(BuildContext context) {

return Scaffold(

appBar: AppBar(

backgroundColor: Colors.red,

title: const Text("ChessBoard"),

),

body: Center(

child: ChessGrid(),

),

);

}

}

class ChessGrid extends StatelessWidget {

@override

Widget build(BuildContext context) {

return GridView.builder(

gridDelegate: SliverGridDelegateWithFixedCrossAxisCount(
crossAxisCount: 8,

crossAxisSpacing: 0,

mainAxisSpacing: 0,

),

itemCount: 64,

itemBuilder: (context, index) {

//check the row and column of the square

int row = index ~/ 8;

int col = index % 8;

// check if the square should be light or dark

bool isDarkSquare = (row + col) % 2 == 1;

return Container(

margin: EdgeInsets.all(0),

color: isDarkSquare ? Colors.black : Colors.white,

);

});

}

}
