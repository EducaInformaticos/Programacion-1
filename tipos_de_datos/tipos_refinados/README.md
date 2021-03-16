# <p style="text-align: center;">**TIPOS REFINADOS**</p>

Los tipos refinados se resumen en:
+ Clases
+ Interfaces
+ Abstracciones

## **Clases**

Las clases son una generalización de un concepto.  
Por ejemplo, la clase silla tiene que tener defindo un numero de patas, una altura, un ancho, una profindidad, un volumen, y un material.  
Un objeto es una instancia de la clase silla en concreto, por ejemplo un taburete. 

A efectos prácticos, un objeto es una estructura con funciones dentro.  
Los campos de un objetos pasan a llamarse atributos.  
Las funciones de un objeto se llaman métodos.  
Heredan todo el comportamiento de las estructuras, se sigue accediendo con `.` o `->`.  
A diferencia de las estructuras si que pueden tener valores por defecto.  
Pueden tener multiples constructores y de diversos tipos.
Además, sus atributos y métodos pueden ser visibles para otras clases o no.
Tienen la propiedad de heredar, es decir, tomar atributos y métodos de otras clases para usarlos o modificarlos e incluso implementarlos si no lo estan ya.

## **Abstracciones**

Un objeto abstracto o clase abstracta es aquella que generaliza un conjunto muy extenso.  
Por ejemplo, la clase animal declara generalmente como ha de ser un animal; y la clase perro, que debe heredar de animal, implementará lo necesario para concretizar un perro.

## **Interfaces**

Las interfaces ocupan el lugar de las abstracciones cuando es necesario generalizar múltiples cosas en una sola.  
Por ejemplo, las interfaces CamaraFotos, Radio, Ordenador, Televisor y Telefono podrian estar unidas ofreciendole soporte a una clase SmartPhone que contaria con las propiedades básicas de cada una de las interfaces; cosa que no es tan factible si se usan Abstracciones.

---

### <p style="text-align: center;">**FIN DE LOS TIPOS DE DATOS**</p>

Hasta aquí estan definidos los tipos de datos que se pueden encontrar en la programación.  
Los objetos se trabajarán más en detalle en otra guía ya que conllevan muchos más conceptos de los que esta ofrece.

--> [INDEX](/PAGEMAP.md)