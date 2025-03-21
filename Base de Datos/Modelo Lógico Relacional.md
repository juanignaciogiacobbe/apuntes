# Modelo Lógico Relacional


> [!IMPORTANT] Modelo Lógico Relacional
> Se vincula con la representación de los datos(en tablas).
> Es una formalización matemática basada en el concepto de Relación.

### Definiciones importantes
- <span style="color:#ffff00">Dominio</span>: Es el conjunto de valores homogéneos. Ejemplo: $D = \{Bs As, Sevilla, Cordoba\}$.
- <span style="color:#ffff00">Producto cartesiano</span>: A x B se define como el conjunto de pares (a, b) que cumplen que $a \in A$ y $b \in B$.
- <span style="color:#ffff00">Relacion</span>: Es un subconjunto de un producto cartesiano. Las funciones de matemática son relaciones :D. Se las representan en tablas. 
- <span style="color:#ffff00">Esquema de Relacion</span>: Cuando se tiene una relación R y una lista de atributos. Se denota como $R(A_{1}, A_{2}, ..., A_{n})$ . Cada uno de los atributos esta asociado a un dominio particular. Los atributos representan en las columnas de las tablas.
- <span style="color:#ffff00">Tupla</span>: Un elemento de una relación. Son las filas de las tablas.



> [!WARNING] Restricciones
> Representan generalmente entidades o interrelaciones de nuestro modelo de datos.


### Restricciones de Dominio
- Especifican que dado un atributo A de una relación R, <span style="color:#ffff00">el valor de A en una tupla t debe pertenecer al dominio Dom(A)</span>.
- Se puede permitir los valores <span style="color:#ffff00">NULL</span>.
- Los <span style="color:#ffff00">atributos</span> deben ser <span style="color:#ffff00">atomicos</span>(no se permiten compuestos o multivaluados).

### Restricciones de Unicidad
- No pueden existir dos tuplas distintas que coincidan en los valores de todos sus atributos.
- Existe un conjunto SK del conjunto de atributos de R que cumple la condición de que dadas dos tuplas $s, t \in R$, las mismas difieren en al menos uno de los atributos de SK. SK se la llama <span style="color:#ffff00">superclave</span> de R.
- Las superclaves minimales se las llaman <span style="color:#ffff00">claves candidatas</span>.
- De entre todas las claves candidatas elegiremos una como <span style="color:#ffff00">clave primaria</span> de R.

### Restricciones de Integridad
- Se tienen en cuenta para Esquemas de Base de Datos Relacional.
- <span style="color:#ffff00">Restriccion de Integridad de Entidad</span>: La PK de una relación no puede ser NULL.
- <span style="color:#ffff00">Restriccion de Integridad Referencial</span>: Cuando un conjunto de atributos FK de una relación R hace referencia a la clave primaria de otra relación S, entonces para toda tupla de R debe existir una tupla de S cuya PK sea igual al valor de FK, a menos que todos los atributos de FK sean NULL. Entonces, FK se la llama <span style="color:#ffff00">Clave Foranea</span>.  


> [!WARNING] Algunas reglas a tener en cuenta al pasar del Modelo Conceptual al Modelo Relacional
- Cada entidad del modelo ER producirá generalmente una relación del modelo relacional.
- Atributos multivaluados: Se crea una tabla para el atributo.



> [!WARNING] Problemas que se presentan en esquemas defectuosos
> Se pueden evitar utilizando los criterios de un buen [[Diseño Relacional]].

- Incapacidad para almacenar ciertos hechos.
- Redundancias -> inconsistencias.
- Ambigüedades.
- Perdida de información y dependencias funcionales.
- Existencia de valores nulos.
- Aparición, en la DB, de estados que no son validos en el mundo real.