### Main

```dart
import 'package:flutter/material.dart';

import 'home_page.dart';

void main(){
  runApp(Miclase());
}
class Miclase extends StatelessWidget{
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'My App',
      debugShowCheckedModeBanner: false,
      home: HomePage(),
    );
  }
      

}

```

### Home

```dart
import 'package:flutter/material.dart';
import 'package:http/http.dart' as http;
import 'package:senapp2/modelos/user.dart';

import 'widgets/carga_page.dart';
import 'widgets/datos_page.dart';
import 'widgets/error_page.dart';

class HomePage extends StatelessWidget {
  const HomePage({
    Key? key,
  }) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Titulo')),
      body: FutureBuilder(
        builder: (context, snapshot) {
          if (snapshot.connectionState == ConnectionState.done) {
            if (snapshot.hasError) {
              return ErrorPage();
            }else if (snapshot.hasData) {
              return DatosPage(
                user: snapshot.data as User
                );
            }
          }
          return CargaPage();
        },
        future: getData(),
      )
    );
  }

  Future<User> getData() async {
    final url = Uri.https('reqres.in','/api/users/4');
    final response = await http.get(url);
    if (response.statusCode == 200){
      return User(response.body);
    }else{
      throw 'Error en la peticion';
    }
  }
}

```


### carga

```dart
import 'package:flutter/material.dart';

class CargaPage extends StatelessWidget {
  const CargaPage({
    Key? key,
  }) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return Center(child: CircularProgressIndicator());
  }
}
```

### datos

```dart

import 'package:flutter/material.dart';

import '../modelos/user.dart';

class DatosPage extends StatelessWidget {
  final User user;
  
  const DatosPage({
    Key? key, required this.user,
  }) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return Column(
      children: [
        Text(user.id.toString()),
        Text(user.email!),
      ],
    );
  }
}
```

### Error

```dart

import 'package:flutter/material.dart';

class ErrorPage extends StatelessWidget {
  const ErrorPage({
    Key? key,
  }) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return Center(child: Text('ERROR'));
  }
}

```

### User

```dart

import 'dart:convert';

class User{
  int? id;
  String? email;

  User(String jsonString){
    Map body =jsonDecode(jsonString);
    Map data = body['data'];
    this.id = data['id'];
    this.email = data['email'];
  }
}
```

