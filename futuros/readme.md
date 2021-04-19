# Futuros

Future es una de las APIs más básicas que Dart tiene para el manejo de async (asíncrono).
La mayoría de los lenguajes modernos tienen algún tipo de soporte para la programación asíncrona. Muchos ofrecen una API de futuros, y algunos los llaman Promesas. Y en su mayor parte, los Futuros de Dart son muy similares a las que se encuentran en otros lenguajes.

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
