# Introducción a las Bases de Datos

> [!IMPORTANT] Base de Datos
> Un conjunto de datos interrelacionados.


> [!IMPORTANT] Dato
> Es un hecho que puede ser representado y almacenado de alguna forma, y que tiene un sentido implícito.


> [!IMPORTANT] Base de Datos Tradicionales
> Solo almacenan datos de texto o numéricos, que pueden enunciarse a través de *proposiciones* -> Un conjunto de proposiciones que tienen la misma estructura puede tipificarse a través de un *predicado*.


> [!IMPORTANT] Predicado
> Es una función que toma uno o más argumentos y devuelve un valor de verdad.
> - Las Bases de Datos sólo almacenan proposiciones verdaderas.

---

## Arquitectura de 3 Capas ANSI/SPARC
- Es una arquitectura en 3 niveles de abstracción para la descripción/representación de los Datos en una Base de Datos.
- Asegura la independencia de datos, tanto física como lógica.

![](Base%20de%20Datos/img/Pasted%20image%2020241205084445.png)


> [!IMPORTANT] Modelo Interno
> Representa la forma en que los datos se almacenan utilizando estructuras de datos y organizaciones de archivos. Representa cómo perciben los datos los [[Sistemas Operativos]] y el [[02-Database Management System(DBMS)]].


> [!IMPORTANT] Modelo Conceptual
> Describe la semántica de los Datos, incluyendo sus características tanto estáticas como dinámicas.
> [[03-Diseño Conceptual de Bases de Datos]]


> [!IMPORTANT] Modelo Lógico Relacional
> Es un paso intermedio entre el modelo conceptual y el modelo interno, que formaliza las descripciones del modelo conceptual.
> [[Modelo Lógico Relacional]]


> [!IMPORTANT] Modelo Externo
> Representa la forma en que los usuarios perciben los datos.


---
## ¿Cómo interactuamos con los modelos?
- Lo hacemos a través de un <span style="color:#ffff00">lenguaje</span>.
- Los <span style="color:#ffff00">lenguajes de manipulacion de datos</span>(DML) nos permiten extraer información de un modelo de datos.

![[Pasted image 20241218160503.png]]

- Los <span style="color:#ffff00">lenguajes procedurales</span>(de bajo nivel) indican un propósito a seguir, utilizando operaciones que indican como manipular los datos. Ejemplos:
	- [[Álgebra Relacional]]
- Los <span style="color:#ffff00">lenguajes declarativos</span> indican que resultado se quiere obtener, sin especificar como hacerlo.