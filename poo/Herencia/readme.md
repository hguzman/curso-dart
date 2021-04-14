# Herencia
La herencia es una de las premisas y técnicas de la POO la cual permite a los programadores crear una clase general primero y luego más tarde crear clases más especializadas que re-utilicen código de la clase general. La herencia también le permite escribir un código más limpio y legible.

## jerarquía de herencia
La relación padre-hijo entre clases puede representarse desde un punto de vista jerárquico, denominado vista de clases en árbol. La vista en árbol comienza con una clase general llamada superclase (a la que algunas veces se hace referencia como clase primaria, clase padre, clase principal, o clase madre; existen muchas metáforas genealógicas). Las clases derivadas (clase secundaria o subclase) se vuelven cada vez más especializadas a medida que van descendiendo en el árbol. Por lo tanto, se suele hacer referencia a la relación que vincula una clase secundaria con una clase primaria mediante la frase es una x o y.

![](C:\Users\Admin\Pictures\poo-images-animaux.gif){width='313px'  height='150px'}


La herencia es siempre transitiva: una clase puede heredar características
de superclases que se encuentran muchos niveles más arriba en la jerarquía
de herencia.Ejemplo: si la clase Perro es una subclase de la clase Mamífero, y la clase Mamífero
es una subclase de la clase Animal, entonces el Perro heredará atributos tanto de
Mamífero como de Animal.

En dart para que una clase herede los atributos y métodos de otra clase usamos la palabra reservada extend de la siguiente forma.

```
class Empleado{
  var id;
  var name;
  double salario;

  void calcularSalario(){
    print('El salario de $name es $salario');
  }
}

// Hereda de Empleado
class Chofer extends Empleado{
  String vehiculoAsignado;
  void manejar(){
    print('Manejar vehiculo');
  }
}

```

Luego de aplicar herencia cuando creamos una instancia del objeto hijo podremos utilizar los métodos y variables de la clase padre.

```
main(){
  Chofer chofer = Chofer();
  chofer.id = 1;
  chofer.name = 'Andy';
  chofer.salario = 11.00;
  chofer.vehiculoAsignado = 'Toyota Supra';
  chofer.calcularSalario();
  chofer.manejar();
}

```
## Herencia y modificadores de acceso
Los modificadores de acceso definen qué clases pueden acceder a un atributo o método. esto podría servir por ejemplo para ser usados para proteger la información o mejor dicho definir cómo nuestro programa accede a ella. Es decir, los modificadores de acceso afectan a las entidades y los atributos a los que puede acceder dentro de una jerarquía de herencia.

Aunque así de pronto esto pueda parecer complejo lo mejor, para entenderlo, es resumir sus características en una descripción general rápida de los diferentes modificadores:

* Solo se puede acceder a los atributos o métodos privados (private) dentro de la misma clase.
* Se puede acceder a los atributos y métodos sin un modificador de acceso dentro de la misma clase, y por todas las            demás clases dentro del mismo paquete.
* Se puede acceder a los atributos o métodos protegidos (protected) dentro de la misma clase, por todas las clases dentro del  mismo paquete y por todas las subclases.
* Todas las clases pueden acceder a los atributos y métodos públicos.

![](C:\Users\Admin\Pictures\tabla-herencia-programacion.png){width='597px'  height='130px'}

## Constructores y herencia
A diferencia de lo que ocurre con los métodos y atributos no privados, los constructores no se heredan. Además de esta característica, deben tenerse en cuenta algunos aspectos sobre el comportamiento de los constructores dentro del contexto de la herencia, ya que dicho comportamiento es sensiblemente distinto al del resto de métodos.

Cuando existe una relación de herencia entre diversas clases y se crea un objeto de una subclase S, se ejecuta no sólo el constructor de S sino también el de todas las superclases de S. Para ello se ejecuta en primer lugar el constructor de la clase que ocupa el nivel más alto en la jerarquía de herencia y se continúa de forma ordenada con el resto de las subclases

### Invocar un constructor de superclase no predeterminado
Por defecto, un constructor en una subclase llama al constructor sin nombre de la superclase, sin argumentos. El constructor de la superclase es llamado al principio del cuerpo del constructor. Si también se está utilizando una lista de inicializadores, se ejecuta antes de que se llame a la superclase. En resumen, el orden de ejecución es el siguiente:

* lista de inicializadores
* el constructor de superclases sin argumentos
* constructor sin argumentos de la clase principal

Si la superclase no tiene un constructor sin nombre y sin argumentos, se debe llamar manualmente a uno de los constructores en la superclase. Para llamar a un constructor de la superclase se usa `:super()` justo antes del cuerpo del constructor si lo hay.

```
class Persona {
  String nombre;
  String apellido;
  int _edad;

  Persona(edad) {
    this._edad = edad;
  }
}

class Estudiante extends Persona {
  /*para llamar el constructor principal */
  Estudiante(edad) : super(edad);
}

void main() {
  Estudiante estu = new Estudiante(21);
}
```
