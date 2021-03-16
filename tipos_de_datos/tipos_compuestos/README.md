# <p style="text-align: center;">**TIPOS COMPUESTOS**</p>

A veces, se necesita definir nuevos tipos de datos o tipos de datos estructurados por necesidades del diseño.
Para ello, la mayoria de lenguajes ofrecen tres posibilidades:
+ tipos propios
+ enumeraciones
+ estructuras

## **TIPOS PROPIOS**

En la mayoría de lenguajes podemos definir nuevos tipos.  
Por ejemplo, podriamos definir el tipo **ENTERO** para sustituir el tipo `int`.  
Anteriormente, se define que en C no existe el tipo `bool`, que si esta definido en C++ y redefinido en Java como `boolean`.  
Para definir este tipo en C se ha de usar la plabra reservada de C/C++ `typedef`.
La implementación seguiría como:
```C++
	// in bool.h
	#ifndef bool
		#define false 0
		#define FALSE false
		#define TRUE !FALSE
		#define true TRUE
		typedef unsigned short char bool;
	#endif
```

También se puede definir un tipo que se expanda en un array como:
```C++
	size_t size = 10;
	typedef int[size] arr;
```
Nota: Las directivas #ifndef, #endif, #define no se compilan, son sustituidas en el proceso previo de analisis del código. Si quieres saber más acerca del tema, en  [Wikipedia](https://es.wikipedia.org/wiki/Wikipedia:Portada) hay información bastante buena sobre el [preprocesador de C](https://en.wikipedia.org/wiki/C_preprocessor).

## **ENUMERACIONES**

Las enumeraciones son muy útiles para cuando existe una lista de cosas y se debennumerar.
Por ejemplo, si se hace un menú y se necesita listar las opciones, además de numerarlas, se debe usar un enum o enumeración.
Los `enum`, palabra reservada para usarlos, guardan los valores como un array, de 0 hasta n-1, conservando los nombres que les hemos dado.
```C++
	// así se declara un enum
	enum meses{
		enero,
		febrero,
		marzo,
		abril,
		mayo,
		junio,
		julio,
		agosto,
		septiembre,
		octubre,
		noviembre,
		diciembre}; 
	
	// así se declara una variable de un tipo enum
	enum meses este_mes = marzo;
	printf("%d", este_mes);

	// así también se declara una variable de un tipo enum
	enum bool{false, true} check;
```
Además se puede modificar los valores por defecto de un enum, si cuando estamos definiendolo, asignamos esos valores a los del enum.
```C++
	char doce[3]="12\0";
	enum meses{
		enero = 1;
		febrero = enero + 1;

			.	.	.
		
		diciembre = doce;
	};
```
Se puede combinar el uso de `typedef` para definir tipos enumerados.
Usando esto, definase el tipo `bool` como:
```c++ 
typedef enum{false=0,true=!false} bool;

	.	.	.

bool check = false;
if(nota >=5 ) check = true;
if(check) cout << "Has aprobado!" << endl;

```

Otro ejemplo más de como usar enums:
```C++
	typedef enum menu_opt{
		NaO = -1, // Not an Option
		help = 0,
		add_data,
		show_data,
		exit = 99,
	};

		.	.	.

	menu_opt opt = NaO;
	printf("Que quieres hacer? [Ayuda(0) Anyadir(1) Mostrar(2) Salir(99)]");
	scanf("%d", opt);
	switch(opt){
		case help:
			helpf();
			break;
		case add_data:
			add_dataf();
			break;
		case show_data:
			show_dataf();
			break;
		case exit;
			exitf();
			break;
		defalut:
			#error NO SE HA INSERTADO UNA OPCION VALIDA
	}
```

Un último ejemplo:
```C++
	typedef enum opt{RESTART, SHUTDOWN, SUSPEND, HIBERNATE, SAVE,HALT};
	void shutdown(opt flag){
		switch(flag){
			case SAVE + RESTART:
				save();
			case RESTART:
				restart();
				break;
			case SAVE + SHUTDOWN:
				save();
			case SHUTDOWN:
				__shutdown();
				break;
				.	.	.
			
			default:
				#error NO VALID OPTION
		}
	}

	.	.	.

	shutdown(SAVE | SUSPEND); // en este caso '|' hace que se sumen las opciones
```

## **ESTRUCTURAS**

Las estructuras permiten crear datos con propiedades especiales llamadas campos, no existe límite para el número de campos.
Supongamos que se quiere definir un coche. Lo más óptimo es crear una clase llamada coche que tenga métodos y atributos definiendo el comportamiento de un coche.
Las estructuras permiten hacer lo mismo pero sin métodos.
Las estructuras se definen usando la palabra reservada `struct`, y al igual que los enums pueden ser definidas como un tipo.
Es importante remarcar que las estructuras, una vez instanciadas (cuando se crea una variable), los campos no tienen valores predeterminados y pueden tener cualquier valor, tampoco se puede asignar un valor por defecto en la declaración de la estructura, aunque si se pueda declarar el tamaño de los arrays.
```C++
	struct SChapa{
		char *modelo;
	};
	struct SMotor{
		char *modelo;
	};
	struct coche{
		unsigned int ruedas;
		unsigned int puertas; // esto se llama campo, es el equivalente a un atributo en objetos
		unsigned int espejos;
		SChapa chapa;
		SMotor motor;
		char modelo[SIZE_MAX]; // Existen máximos ya definidos en algunas librerias, en la stdint.h viene el maximo para un tipo size_t
	};
	typedef struct automovil{
		struct coche c; // para crear una variable del tipo struct , se ha de poner siempre struct [estructura_creada] [nombre_variable]
	}am; // esto último se llama alias, se usa para llamar al tipo definido sin sobreescribir el nombre del struct
```

Para darle valores a los campos, se usa o bien un '.' o bien '->' en caso de que sea un puntero.
```C++

	// sea am tuCarro o struct am tuCarro todas las operaciones son iguales, sea un puntero o no

	// variable de tipo automovil
	am miCarro;
	miCarro.coche.ruedas = 4;
	miCarro.coche.puertas = 5;
	miCarro.coche.espejos = 3;
	miCarro.coche.chapa.modelo = malloc(SIZE_MAX);
	strcpy(miCarro.coche.chapa.modelo, "ALUMINIO NEGRO MATE"); // esta función se encarga de copiar lo que hay escrito a la derecha en el array de caracteres de la izquierda
	miCarro.coche.motor.modelo = malloc(SIZE_MAX);
	strcpy(miCarro.coche.motor.modelo, "V12 de 190 CV DIESEL");
	miCarro.coche.modelo[0] = 'f';
	miCarro.coche.modelo[1] = 'o';
	miCarro.coche.modelo[2] = 'r';
	miCarro.coche.modelo[3] = 'd';
	miCarro.coche.modelo[4] = '\0';

	// variable del tipo struct coche
	struct coche c;
	c.ruedas = 4;
	c.puertas = 5;
	c.espejos = 3;
	c.chapa.modelo = malloc(SIZE_MAX);
	strcpy(c.chapa.modelo, "ALUMINIO NEGRO MATE"); // esta función se encarga de copiar lo que hay escrito a la derecha en el array de caracteres de la izquierda
	c.motor.modelo = malloc(SIZE_MAX);
	strcpy(c.motor.modelo, "V12 de 190 CV DIESEL");

	// puntero del tipo struct coche
	struct coche *cc;
	cc = (struct coche*)malloc(sizeof(struct coche));
	cc->ruedas = 4;
	cc->puertas = 5;
	cc->espejos = 3;
	cc->chapa.modelo = malloc(SIZE_MAX);
	strcpy(cc->chapa.modelo, "ALUMINIO NEGRO MATE"); // esta función se encarga de copiar lo que hay escrito a la derecha en el array de caracteres de la izquierda
	cc->motor.modelo = malloc(SIZE_MAX);
	strcpy(cc->motor.modelo, "V12 de 190 CV DIESEL");

```

### Curiosidades

Java permite que los enum tengan métodos internos ya que los considera objetos pero con propiedades especiales y un constructor predefinido que asigna un valor numérico a cada un de los valores del enum.

Los punteros apuntan a secciones de memória. Bajo este lema se puede considerar la idea de crear punteros que apunten a funciones y al incluirlos dento de una estructura, podríase crear un redumentario ecosistema de objetos. Sin embargo, eso no se trata en esta guía.

C++ permite el uso de constructores(funciones que se llaman cuando se instancia una variable del mismo tipo) para darle valores predeterminados a los campos de la estructura. C++ añade un puntero a función para realizar este constructor.
```C++
	typedef struct coche{
		int puertas;
		int ruedas;
		int luces;
		char matricula[SIZE_MAX];
		coche(int p, int r, int l, char msg[SIZE_MAX]) : puertas(p), ruedas(r) // se puede especificar así
		{
			// o se puede especificar así
			luces = l;
			strncpy(matricula, msg, 7); // copia los 7 primeros caracteres
		}
	};
```

--> [INDEX](/PAGEMAP.md)