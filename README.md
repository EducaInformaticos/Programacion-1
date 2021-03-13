# <p style="center">Bases de la programación</p>  

---

## La programación.

Existen muchos campos bajo este nombre.

Aquí nos centramos en las bases de la programación y conocimiento geneérico y básico de lo que es la programación.

---

## Los lenguajes

Existen tantos lenguajes como se pueda imaginar.  
Pero se agrupan en 3 grandes tipos:  
+ Ensamblados (bajo nivel)
+ Compilados (nivel alto)
+ Interpretados (nivel alto)


### Ensamblados

Existen tantos lenguajes como familias de procesadores.  
Es una traducción directa de los '1s y 0s' que entiende el ordenador.
Cuentan con un corpus de instrucciones reducido y tienen control directo sobre todo el computador.  
Algunos son:  
+ [MIPS](https://es.wikipedia.org/wiki/MIPS_(procesador) "La Nintendo64 usa estos procesadores, si aprendes a manejarte, puedes o piratearla o hacer juegos")
+ [PS/2 PC](https://es.wikipedia.org/wiki/IBM_Personal_System/2 "Este lenguaje lo desarrollo IBM y durante una época hubo muchos intentos de piratearlo")
+ [x86](https://es.wikipedia.org/wiki/Lenguaje_ensamblador_x86 "INtel - in intel - in in intel - con MIPS tienes mas libertad")

Estos son los lenguajes denomidados de bajo nivel. Se llaman así por la interfaz que ofrece al programador. Estos lenguajes dejan la máquina entera en manos de quien la programa, se puede modificar cada valor existente en la memória. En los lenguajes de más alto nivel, no permiten la modificación directa de la memória del computador, pero a cambio, son más amigables con el programador.  
Habitualmente se programa con lenguajes de nivel alto.



### Compilados

Los lenguajes compilados son, por lo general, los más rápidos, después de los ensamblados.  
Estos lenguajes tienen 2 fases en su funcionamiento:  
+ Tiempo de compilación: Cuando se esta compilando un programa pueden surgir problemas como no haber escrito bien el nombre de una función o un tipo de un dato. En esta fase, se esta convirtiendo lo que se ha escrito de un lenguaje a un lenguaje ensamblado.
+ Tiempo de ejecución: Una vez compilado, se ejecuta el programa y durante este tiempo pueden ocurrir problemas como el uso de variables mal inicializadas o inputs incorrectos. En esta fase, el procesador esta interpretando el código transformado.

Estos lenguajes son más rápidos ya que se han convertido en lenguaje máquina o ensamblador y no necesitan de volver a ser convertidos cada vez que se ejecutan.  
Suelen ser, por lo general, lenguajes que ofrecen mayor seguridad a las aplicaciones que los usan, ya que el código fuente no queda expuesto si no se hace una lectura de memoria en ensamblador para hacer ingenieria inversa u otros métodos; sin embargo, la seguridad depende del programador, no del lenguaje.  
Sin los conocimientos necesarios, el desarrollo de aplicaciones se ralentiza.  
Además, estos lenguajes suelen depender del sistema operativo para ser compilados de una forma u otra.

Algunos lenguajes son:  
+ [FORTRAN](https://fortran-lang.org/)
+ [C](https://www.iso.org/standard/74528.html)
+ [C++](https://isocpp.org/)



### Interpretados

Los lenguajes interpretados son los más lentos.  
Estos lenguajes funcionan sobre un intérprete que hace a la vez de compilador y de entorno de ejecución, esto hace que se ralentice el proceso entero ya que se hace cada vez que se ejecuta.  
Solo tienen errores de ejecución, e inherente a su condición de lenguaje, también de sintaxis.  

Lo bueno de estos lenguajes es que no es necesario especificar el tipo de los datos antes de ejecutar el código.  
Son multiplataforma y no dependen del sistema operativo siempre y cuando el intérprete se encargue de gestionar las interacciones.
Como dejan expuesto el código fuente, suelen ser más inseguros.
Permiten desarrollar más rápidamente a costa de la velocidad de la propia aplicación.

Los más conocidos son:
+ [JavaScript](https://www.javascript.com/)
+ [TypeScript](https://www.typescriptlang.org/)
+ [Python](https://www.python.org/)
+ [Lua](https://www.lua.org/)
+ [C#](https://docs.microsoft.com/en-us/dotnet/csharp/)
+ [Java](https://www.java.com/es/)(Se compila y se interpreta, tiene todo lo malo de los 2)


#### Clasificaciones adicionales

Todos estos lenguajes además se separan en débil y fuertemente tipados.
Los fuertemente tipados son aquellos que se define el tipo de dato antes de compilarlo o interpretarlo(C/C++, C#, TypeScript).
Los débilmente tipados son aquellos que se define el tipo de dato mientras se compila o interpreta(JavaScritp, [PHP](https://www.php.net/)).
