# Programación Orientada a objetos

## Getters Setters
Los métodos que permiten acceder al valor de un atributo se denominan "getters" (del verbo inglés "get", obtener) y los que fijan el valor de un atributo se denominan "setters" (del verbo inglés "set", fijar).

Ejemplo:

```
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
