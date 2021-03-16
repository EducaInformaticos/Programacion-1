## Ejercicios sobre los tipos de datos

### Datos primitivos

1- Dado el siguiente código, corrigelo para que compile y ejecute correctamente:
```C++
	#include <stdio.h> //librería fundamental de C

	int main(){

		int 9 = 9;

		int diezyocho = 18;

		int suma = diezyocho + 9;

		printf("%d", suma);

		return 0;
	}
```

2- Cual es la salida de este fragmento?
```C++
	// intenta realizarlo sin usar el ordenador, pero consultando las tablas ascii
	char a = 48
	char b = 'b'
	int suma = a + b
	cout << suma;

```

3- Cual es la salida de este fragmento?
```C++
	// intenta realizarlo sin usar el ordenador, pero consultando las tablas ascii
	char a = 48
	int b = '0'
	float f = 2.333;
	double d = f/2;
	double dd = 51/2;
	unsigned int i = -3;
	unsigned float ff = a/b;
	cout << d << dd << i << ff << a << b << f;

```

### Datos simples
1- Dado el siguiente código, corrigelo para que compile y ejecute correctamente:
```C++
	#include <stdio.h> //librería fundamental de C

	int main(){

		int *p = 19;
	
		int suma = p + 9;

		printf("%d", suma);

		return 0;
	}
```

2- Cual es la salida de este fragmento?
```C++
	// intenta realizarlo sin usar el ordenador, pero consultando las tablas ascii
	char *a = new char;
	*a = 'a';
	char b = 'b';
	int suma = a + b;
	cout << suma;

```

3- Cual es la salida de este fragmento?
```C++
	// intenta realizarlo sin usar el ordenador, pero consultando las tablas ascii
	char a = 'a';
	char *b = a;
	*b++;
	cout << a << b;

```

### Datos compuestos

1- Crea un tipo de dato que sea una cadena de caracteres de 20 elementos.

2- Crea un tipo enumerado con los 7 primeros platos de comida que más te gusten e imprime por pantalla el plato número 6.

3- Crea un puntero del tipo Autobús. Tendrás que crear el tipo estructurado TAutobús que tendrá como campos: el número de ruedas, el número de pasajeros, el nombre del conductor, y la matrícula.