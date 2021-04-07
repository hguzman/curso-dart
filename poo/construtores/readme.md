# Constructores

## Ejemplo constructor

```dart
void main(){
  Letra letra = new Letra(texto: 'BARRANQUILLA');
  print('Cantidad de caracteres => ${letra.cantidadCaracteres()}');
  letra.textoContrario();
}

class Letra{
  String texto;
  
  Letra({String this.texto}){}
  
  int cantidadCaracteres() => texto.length;
  
  
  void textoContrario(){
    
    int i = cantidadCaracteres() -1;  
    String respuesta = '';
  
    for (i; i>= 0; i = i -1){
      respuesta = respuesta + this.texto[i];
    }
    
    print('El texto contrario es => $respuesta');
    
  }
}
```
