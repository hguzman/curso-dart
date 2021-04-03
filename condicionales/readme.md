# que es un condicional ?
 una sentencia condicional es una instrucción o grupo de instrucciones que se pueden ejecutar o no en función del valor de una condición.

 Los tipos más conocidos de sentencias condicionales son el SI..ENTONCES (if..then), el SI..ENTONCES..SI NO (if..then..else) y el SEGÚN (case o switch),
 aunque también podríamos mencionar al manejo de excepciones como una alternativa más moderna para evitar el "anidamiento" de sentencias condicionales.
 Una estructura condicional ejecuta ciertas líneas de código en función de una expresión booleana.

Hay 3 tipos de estructuras de control condicional.

de condición simple, la estructura if;

bicondicional, la estructura if-else; y

de condición múltiple, la estructura switch-case-default.

Mientras que en las estructuras if y if-else la expresión booleana condicional puede contener cualquier tipo de dato y puede intervenir cualquier tipo de operador condicional o booleano, la expresión condicional de la estructura switch-case es solo de comparación de igualdad y restringida a los tipos de datos int, char o String

Cualquiera de estas estructuras pueden estar anidadas en cualquier bloque del programa, donde se incluyen los bloques de las estructuras anidadas.

## Ejemplo

````
void main(){
    switch (r) {
      case 0:
        // do something
        break;
      case myPI: 
        // do something else
        break;
    }
}

````
## ejemplo de condicional si (if)

### condicional simple.

````
if (a != 0) {
    print("El cociente es: ");
    println(b/a);
}

````
### bicondicional

el siguiente codigo muestra un mensaje cuando un numero es negativo y cuando no lo es.

````
if (a < 0) {
    println("El número es negativo");
} else {
    println("El número es nulo o positivo");
}

````
### condicional multiple 

````
int dia;

switch (dia)
  {
   case 1 : println("lunes");
            break;
   case 2 : println("martes");
            break;
   case 3 : println("miércoles");
            break;
   case 4 : println("jueves");
            break;
   case 5 : println("viernes");
            break;
   case 6 : println("sábado");
            break;
   case 7 : println("domingo");
            break;
  default : println("¡ Día desconocido !");
            break;
  }
  
  ````
  
  # Generalidaes de un dependiendo d

## Diagrama de flujo
