# Programación Orientada a objetos

[Constructores](constructores/readme.md)
[Clases abstractas](clases-abstractas/readme.md)

## Herencia
Es la base de la reutilización del código, mediante la herencia se pueden crear relaciones entre objetos que extienden a objetos padres, heredando su comportamiento y estructura interna.


## Atributos
- **-privados:** Son atributos que solo pueden ser accedidos dentro de la clase
- **+publicos:** Atributos que pueden ser accedidos desde fuera de la clase
- **#protegidos:** Solo pueden ser accedidos desde la propia clase y sus hijos

## Getters Setters
Los métodos que permiten acceder al valor de un atributo se denominan "getters" (del verbo inglés "get", obtener) y los que fijan el valor de un atributo se denominan "setters" (del verbo inglés "set", fijar).

Ejemplo:

```dart
class Cuadrado{

  double _lado;

  set lado(double valor){
    if (valor <= 0 ){
      throw('El lado no puede ser menor o igual a 0');
    }
    _lado = valor;
  }

  double get area{
    return _lado * _lado;
  }
}
```
