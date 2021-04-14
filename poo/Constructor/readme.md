#  constructores
##¿Que es un constructor?
Un constructor en programación orientada a objetos es un conjunto de instrucciones cuya misión es inicializar un objeto de una clase. Sintaxis:

```
<modificador> <nombre_clase> (<argumentos>)
{
  <instrucciones>
}

```

1. El **nombre del constructor** tiene que ser obligatoriamente el mismo que el de la clase. De esta manera, puedes distinguir entre los diferentes constructores que puedes tener en la clase con los otros métodos.

2. Los **modificadores** son los mismo que el de las funciones. Así, para los constructores pueden tener como modificadores **public, private, y protected**.

3. Pueden pasarse parámetros a un constructor, de la misma forma que una función.

4. Los **<argumentos>** se hace de la misma manera que con las funciones, poniendo su tipo de datos y el nombre del argumento a usar.

5. Dada su utilidad y lo común de su uso Dart tiene una forma compacta de constructor en la cual los argumentos del constructor se asignan a las variables de instancia:

```
class Point {
  num x, y;

  Point(num x, num y) {
    this.x = x; // 'this' se refiere a la instancia actual
    this.y = y;
  }
}

class Point {
  num x, y;

  // Forma compacta
  Point(this.x, this.y); // los argumentos 'x' e 'y' se asignan a las variables de instancia con el mismo nombre
}

```

###constructor por defecto
Cada clase tiene como mínimo un constructor. Si no escribimos un constructor en nuestro código fuente, el lenguaje de programación ofrece uno. Este constructor no tiene parámetros y tiene un cuerpo vacío, es decir, no tiene instrucciones.
El contructor por defecto se habilita cuando creamos instancias de los objetos.
Pero si a una clase le añadimos la declaración de un constructor, es decir, lo escribimos nosotros, el constructor por defecto se pierde.




###Constructores con nombre##
Los constructores con nombre se emplean para implementar múltiples constructores para una clase o para proporcionar mayor claridad. ejemplo:

      ```
void main() {

Animal dog = new Animal.dog();

}
class Animal {

  Animal(this.x, this.y);

  Animal.dog() ;

  Animal.cat();
      }
      ```

Para crear un bojeto en Dart no es necesario usar la palabra clave new. Esta palabra es opcional. Asi que podemos crear objetos a partir de clases de la siguiente manera.

```
void main() {

Animal dog = Animal.dog();

}
```
