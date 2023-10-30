# Futuros

Future es una de las APIs más básicas que Dart tiene para el manejo de async (asíncrono).
La mayoría de los lenguajes modernos tienen algún tipo de soporte para la programación asíncrona. Muchos ofrecen una API de futuros, y algunos los llaman Promesas. Y en su mayor parte, los Futuros de Dart son muy similares a las que se encuentran en otros lenguajes.

```dart
import 'package:flutter/material.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
@override
Widget build(BuildContext context) {
	return MaterialApp(
	title: 'GeeksforGeeks',

	// to hide debug banner
	debugShowCheckedModeBanner: false,
	theme: ThemeData(
		primarySwatch: Colors.green,
	),
	home: HomePage(),
	);
}
}

class HomePage extends StatelessWidget {
@override
Widget build(BuildContext context) {
	return SafeArea(
	child: Scaffold(
		appBar: AppBar(
		title: Text('GeeksforGeeks'),
		),
		body: Center(
		child: ElevatedButton(
			onPressed: () => Navigator.push(
			context,
			MaterialPageRoute(
				builder: (ctx) => FutureDemoPage(),
			),
			),
			child: Text('Demonstrate FutureBuilder'),
		),
		),
	),
	);
}
}

class FutureDemoPage extends StatelessWidget {
/// Function that will return a
/// "string" after some time
/// To demonstrate network call
/// delay of [2 seconds] is used
///
/// This function will behave as an
/// asynchronous function
Future<String> getData() {
	return Future.delayed(Duration(seconds: 2), () {
	return "I am data";
	// throw Exception("Custom Error");
	});
}

@override
Widget build(BuildContext context) {
	return SafeArea(
	child: Scaffold(
		appBar: AppBar(
		title: Text('Future Demo Page'),
		),
		body: FutureBuilder(
		builder: (ctx, snapshot) {
			// Checking if future is resolved or not
			if (snapshot.connectionState == ConnectionState.done) {
			// If we got an error
			if (snapshot.hasError) {
				return Center(
				child: Text(
					'${snapshot.error} occurred',
					style: TextStyle(fontSize: 18),
				),
				);

				// if we got our data
			} else if (snapshot.hasData) {
				// Extracting data from snapshot object
				final data = snapshot.data as String;
				return Center(
				child: Text(
					'$data',
					style: TextStyle(fontSize: 18),
				),
				);
			}
			}

			// Displaying LoadingSpinner to indicate waiting state
			return Center(
			child: CircularProgressIndicator(),
			);
		},

		// Future that needs to be resolved
		// inorder to display something on the Canvas
		future: getData(),
		),
	),
	);
}
}

```

[Futuros de Dart — Flutter en el Foco](https://medium.com/comunidad-flutter/futuros-de-dart-flutter-en-el-foco-24c3f8399e35)

## Ejemplo then

```dart
void main(){

  print('Primer mensaje');
  obtenerJson().then((data){
    print(data);
  });
  print('Ultima linea');
}



Future<String> obtenerJson(){
  return Future.delayed(new Duration(seconds: 4), (){
    return 'Hola Mundo';
  });
}
```

## Ejemplo async - await

```dart
void main() async {

  print('Primer mensaje');
  String data = await obtenerJson();
  print(data);
  print('Ultima linea');
}



Future<String> obtenerJson(){
  return Future.delayed(new Duration(seconds: 4), (){
    return 'Hola Mundo';
  });
}
```

## Librerias

| Nombre | Url | Descripción |
| --- | --- | --- |
| http | [https://pub.dev/packages/http](https://pub.dev/packages/http) | Permite consumir servicios http |


## contenido archivo pubspec.yaml

** En construcción **
[The pubspec file](https://dart.dev/tools/pub/pubspec)
## Servidor Dart

** En construcción **
[Write HTTP clients & servers](https://dart.dev/tutorials/server/httpserver)
