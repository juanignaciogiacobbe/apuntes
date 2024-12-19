# Modelo Conceptual

> [!IMPORTANT] Diseño Conceptual de Bases de Datos
> Un modelo de Datos debe incluir los siguientes elementos:
> - Un conjunto de objetos, sus propiedades e interrelaciones entre ellos, que representa la estructura.
> - Un conjunto de operaciones, o lenguaje que permita manipular los datos.
> - Restricciones sobre los objetos, las interrelaciones y las operaciones.

## Modelo Entidad-Interrelación
- Está basado en entidades, interrelaciones y atributos para el modelado semántico de datos.
- <span style="color:#ffff00">Tipo de Entidad</span>: Tipo o clase de objeto en particular. **PROTOTIPO**
- <span style="color:#ffff00">Entidad</span>: Instancia de un tipo de entidad. **INSTANCIA**
- <span style="color:#ffff00">Atributo</span>: Una propiedad que describe a la entidad.
- <span style="color:#ffff00">Tipo de Interrelacion</span>: Definición de un conjunto de relaciones o asociaciones similares entre dos o mas tipos de entidades.


> [!IMPORTANT] Atributos
> Cada entidad tendrá valores particulares para cada uno de los atributos del tipo de entidad al que corresponde.
- <span style="color:#ffff00">Dominio de un atributo</span>: Conjunto de valores que el mismo puede tomar.
- En ciertos casos puede permitirse que un atributo de un tipo de entidad no tome ningún valor concreto de ciertas instancias. En este caso toma un valor **NULL**. 


> [!IMPORTANT] Entidades
> Al conjunto de ocurrencias o instancias de un determinado tipo de entidad en un estado determinado de la DB se lo denomina <span style="color:#ffff00">conjunto de entidades</span> de ese tipo de entidad.
- Todo tipo de entidad debe tener un subconjunto del conjunto de atributos, cuyos valores sean necesariamente distintos para cada una de las entidades en el conjunto de entidades. Estos atributos son los <span style="color:#c00000">atributos clave o identificadores unicos</span>. Me aseguran que no hayan dos filas con los mismos valores.
- El conjunto de atributos clave debe ser <span style="color:#ffff00">minimal</span>, es decir que ningún subconjunto del mismo sea capaz de identificar unívocamente a las entidades.


> [!IMPORTANT] Interrelaciones
> La aridad o grado de un tipo de interrelación es la cantidad de tipos de entidad que coparticipan del mismo.
- La <span style="color:#ffff00">cardinalidad</span> es la maxima cantidad de instancias de cada tipo de entidad que pueden relacionarse con una instancia concreta de los tipos de entidades restantes.
- La <span style="color:#ffff00">participación</span> es la mínima cantidad de instancias de cada tipo de entidad que deben relacionarse con una instancia concreta de los tipos de entidades restantes.
- Cuando requerimos que cada instancia de $E_1$ participe de alguna instancia de $r_1$ para poder subsistir, diremos que $E_1$ tiene participación total o dependencia existencial en $r_1$. En caso contrario diremos que tiene participación parcial.

### Entidades Fuertes y Débiles
- Cuando un tipo de entidad depende de otro para ser identificado, se dice que es un tipo de entidad débil.
- La clave de una entidad débil se compone de la clave de su entidad identificadora, más algún/os atributos propios, que se denominan discriminantes, y se indican con líneas punteadas.
- Un tipo de entidad débil siempre tiene participación total en el tipo de interrelación que la vincula con su tipo de entidad identificadora.

### Generalización y Especialización
- Permiten representar relaciones de tipo “es un” en el modelo de datos.
- Los subtipos de entidad son subclases del tipo de entidad padre.
- A través de la especialización se heredan atributos del tipo de entidad padre, al igual que los tipos de interrelación de los que la misma participa.
- Pero a su vez, los subtipos de entidad pueden tener atributos propios.
- Toda instancia de un subtipo de entidad debe corresponderse necesariamente con una y sólo una instancia del tipo de entidad padre.
- <span style="color:#ffff00">Superposición</span>: Los subtipos de entidad pueden ser disjuntos o superpuestos. En caso de ser superpuestos, una instancia del tipo de entidad padre puede corresponderse con instancias de varios subtipos de entidad.
- <span style="color:#ffff00">Completitud</span>: Los subtipos de entidad pueden cubrir a todo el tipo de entidad padre (total), o no (parcial). En caso de no cubrirlo, puede ocurrir que algunas instancias del tipo de entidad padre no se correspondan con ningún subtipo de entidad.