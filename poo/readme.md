# Programación Orientada a objetos

## que es la programacion orientada a objetos o (poo) ?
La Programación Orientada a Objetos (POO) es un paradigma de programación, es decir, un modelo o un estilo de programación que nos da unas guías sobre cómo trabajar con él. Se basa en el concepto de clases y objetos. Este tipo de programación se utiliza para estructurar un programa de software en piezas simples y reutilizables de planos de código (clases) para crear instancias individuales de objetos. 

## porque se utiliza la (poo) ?
La Programación Orientada a objetos permite que el código sea reutilizable, organizado y fácil de mantener. Sigue el principio de desarrollo de software utilizado por muchos programadores DRY (Don’t Repeat Yourself), para evitar duplicar el código y crear de esta manera programas eficientes. Además, evita el acceso no deseado a los datos o la exposición de código propietario mediante la encapsulación y la abstracción, de la que hablaremos en detalle más adelante.

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
