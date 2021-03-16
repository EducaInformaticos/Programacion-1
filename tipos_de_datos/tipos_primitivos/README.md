
# <p style="text-align: center;">Tipos primitivos</p>

## Integer o Enteros

Representan números enteros, positivos o negativos.

## Floating-point o Coma flotante

Simple precisión: Representan números enteros o con decimales, positivos o negativos con 16 decimales.
Doble precisión: Representan números enteros o con decimales, positivos o negativos con 32 decimales.

## Character o Carácter

Representa un cáracter, sea un número, letra o carácter del sistema. Se puede consultar los valores válidos en las tablas [ASCII](https://www.asciitable.com/) o UTF-X[<sup>1</sup>](#notes) la tabla a usar dependerá de la configuración del compilador o intérprete.

## Boolean o Lógicos

Representan valores 0/1 o false/true.

---

## En C

### El modificador const

El modificador `const` hace que un valor con este modificador delante no se pueda modificar dentro de una función.

```C++
	const double FIEGENBAUM_THETA = 4.6695201609102990;
	const double FIEGENBAUM_ALPHA = 2.5029078750958928;
	const double PI = 3.14159265358979323846;
	const double e = 2.718281828459045235360;
```

### El modificador * y &

El modificador `*` hace que una variable copie la dirección de memoria de otra variable y la almacene, permitiendo copiar datos y modificar la copia y el originar de igual forma.
El modificador `&` permite hacer lo mismo, además de crear un "alias" al dato que apuntamos.

```C++
	int myVar = e; // copia el valor de e en myVar
	int *puntero_a_myVar = myVar;
	int direccion_memoria_myVar = puntero_a_myVar;
	int valor_que_hay_en_myVar = *puntero_a_myVar;

	int &myVar_otro_nombre = *myVar;
	myVar_otro_nombre++; // suma uno a myvar
	printf("%d", myVar);
```

### Enteros

Se escriben como `int`.  
Se puede modificar el espacio que ocupa en memória con los modificadores: `short | long | long long`  
Se puede modificar la presencia del signo con `unsigned`

```	C++
	unsigned int uno = 1;
	unsigned int diez = 10;
	unsigned int diez_mil = 10000;

	int menos_uno = -1;
	int menos_diez = -10;
	int menons_diez_mil = -10000;

	(unsigned) shot int s;		// es un número en 2bytes
	(unsigned) int i;		// es un número en 4bytes
	(unsigned) long int l;		// es un número en 8bytes
	(unsigned) long long int ll;	// es un número en 16bytes
```

### Carácteres

Se escriben como `char`.
Se expande en un `unsigned short short int`. Por tanto, los valores que toma solo son de 0 a 255 y lo que representan se puede consultar en las tablas [ASCII](https://www.asciitable.com/).

```C++
	// las comillas simples hacen que la variable a tome el valor del caracter a
	char a = 'a';
	char b = 'b';

	// en los caracteres especiales y los que usa el compilador, se ha de poner una barra invertida delante
	char salto_linea = '\n';
	char comillas = '\'';
	char barra_invertida = '\\';

	// también se puede asignar un número
	char alpha = 224;
	char bell = 7; // cuando se imprime, en los ordenadores antiguos hace un ruidito
```

### Booleanos

En otros lenguajes esta definido, pero en C no[<sup>2</sup>](#notes).  
Este tipo de variables toma 0 como false y 1 o mayor que 1 como true.  
Si quisieramos crear un tipo bool en C sería como:
```C++
	typedef enum { false = 0, true = !false } bool;
```
Mas adelante se trata que es un enum y como definir nuevos tipos.

### Números decimales

C nos brinda con `float` y `double`.
Ambos pueden contar con o sin signo, ser constantes o no.
float es de simple precisión (16bytes).
double es de doble precisión (32bytes).
```C++
	float PI = 3.1415926535;
	double PIPI = 3.14159265358979323846;
```

---

## <div id="notes">Anotaciones </div>

[1]: Existen varias variantes y muchas tablas de carácteres. Las más comunes son las Unicode [UTF-8](https://www.utf8-chartable.de/) y [UTF-16](https://www.fileformat.info/info/charset/UTF-16/list.htm) en Windows.  

[2]: Estos tipos de datos se conservan igual en todos los lenguajes.
A diferencia de C, en la mayoría de lenguajes si está definido el tipo bool o boolean pero se extiende en una implementación como la que hemos realizado.

--> [INDEX](/PAGEMAP.md)