# <p style="text-align: center;">**TIPOS SIMPLES**</p>

Más allá de los tipos de datos simples, existen maneras de agruparlos o definir formas de almacenar estos datos.
+ punteros
+ arrays

!Importante! No todos los lenguajes permiten usar punteros y arrays, muchos de ellos tienen definidos un tipo vector que sustituye el funcionamiento de los arrays. Python por ejemplo, hace uso de la clase vector de C++ para construir los arrays en su máquina virtual.

---

## **Punteros**

Los punteros son, a efectos prácticos, flechas que apuntan a un sitio en la memória del ordenador, haya lo que haya en esa sección de memória.
Para que hayan datos en memória se ha de reservar esa memória para ese dato.

!Importante! Tanto en C como en C++ se usa `*` para indicar que es un puntero. En Java, todas las variables que no sea de [tipos simples](/tipos_de_datos/tipos_simples) son punteros. En la documentación de los lenguajes indica como funcionan en cada lenguaje.

```C++
	int dato = 10; // esto es un dato normal
	int *puntero = NULL; // esto es un puntero y se tiene que reservar memória

	//C++
	cout << dato << endl; // 10
	// El asterísco indica que es un puntero, con él indicamos que queremos el valor del puntero; sin él, indicamos que queremos la dirección de la memória reservada
	cout << puntero << " - " << *puntero << endl; // (dirección de memória aletoria) - NULL(o el valor de la posición de memória)

```

```C++
	// En C++ se usa la palabra reservada 'new'
	void *p = new int; // p apunta a un hueco de tamaño de un entero
	// En C se usan las instrucciones malloc, calloc y realloc, cada una tiene una función.
	void *p = malloc(sizeof(int)); // p apunta a un hueco del tamaño de un entero
```

Siempre se puede reservar más memória para expandir los datos o guardar muchos datos

```C++
	// En C++ existe la wildcard [] que otorga propiedades de tipo lista a nuestro puntero
	char *str = new char[];
	// En C no existe esta propiedad, a cambio hemos de usar la función realloc 
	char *str = (char*)malloc(sizeof(char)); // malloc devuelve un puntero de tipo void
	str = realloc(str, sizeof(str)+sizeof(char)); // esto aumenta en 1 el tamaño de una lista de chars
```

Todos los punteros tienen la propiedad de sumarle un entero para acceder a las posiciones de memória siguientes o anteriores.

```C++
	int i = p[0]; // p + 0 === p
	int j = p[1]; // p + 1 === siguiente numero en la lista

	int *lista = new int[]; // esto es un array
	lista[0] = 0;
	lista[1] = 1;
	lista[2] = 2;
	if(lista[-1] == lista[2]) // en C/C++ no es necesario encerrar entre llaves la siguiente sentencia a un if pero solo si es una sola sentencia
		cout << "El número que va entre corchetes se llama índice. En los punteros en C los índices negativos no devuelven el último elemento, en otros lenguajes como Python, Lua o Erlang si." << endl;

```

Cuando se reserva memória para datos del mismo tipo de manera contigua, se forma un array.

## **Arrays**

Los arrays almacenan una lista **FINITA** de datos del mismo tipo.
Internamente el compilador genera un puntero al primer elemento, a partir de ahí va incrementando en 1 el índice hasta llegar al tamaño definido.
Tiene todas las propiedades de un puntero. En materiales tiene un código de ejemplo para probar los arrays.
Los índices siempre van de 0 hasta el tamaño del arrya menos 1.

En C/C++:
```C++
	int arr[] = {0,1,2,3,4}; // asi puedes declarar los valores de array. este array tiene 5 elementos y las posiciones 0 a 4

	size_t size = 10; // size_t es un unsigned long long int especial para tamaños
	int arr[size]; // este array reserva 10 posiciones con índices 0 a 9, pero sin valores
	int arr[3] = 70; // ahora la 3 posición tiene el valor 70
	int arr[5] = size; // ahora la posición 5 tiene el valor 10

```

--> [INDEX](/PAGEMAP.md)