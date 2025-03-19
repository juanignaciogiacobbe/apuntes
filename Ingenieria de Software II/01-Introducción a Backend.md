# Introducción a Backend

## Arquitecturas de aplicaciones

![[Ingenieria de Software II/img/Pasted image 20250317121236.png]]

### Monolithic Architecture
- Diseño tradicional de software.
- Toda la aplicación es una sola unidad. ->Todo el negocio esta dentro de una misma aplicación/solución.
- En general, se mantiene una sola tecnología para el desarrollo(solemos hacer trampas no muy elegantes y que no siguen buenas practicas).

#### Características
- **Escalabilidad**: Todo como una única unidad(Complicado escalar una sola parte del negocio).
- **Deployment**: Única unidad deployable -> Downtime para todo el sistema.
- **Proceso de Desarrollo**: No requiere demasiado expertise del equipo. Todos van a estar modificando la misma solución, distintos módulos, en la misma tecnología.
- **Troubleshooting**: "Mas sencillo de testear/debuggear".

![[Ingenieria de Software II/img/Pasted image 20250317122227.png]]

---
### Microservice Architecture
- Separación del negocio en distintos servicios "mas chicos" e "independientes"("Paralelismo").
- Cada servicio puede ser programado con distintos stacks.
- Cada servicio puede ser testeando independientemente del resto(No nos salvamos de los integration tests).

#### Características
- **Escalabilidad**: Cada servicio puede escalar independientemente.
- **Deployment**: Independencia entre servicios -> Downtime para el/los servicios que se deployen.
- **Proceso de Desarrollo**: Curva de aprendizaje para el equipo moderada/alta -> Romper con el paradigma monolito. La division de negocio es lo mas importante(y difícil también).
- **Troubleshooting**: "Mas complejo de testear/debuggear".

![[Ingenieria de Software II/img/Pasted image 20250317122243.png]]


---

## Arquitectura de Soluciones
- Existen muchas maneras de diseñar como va a ser creado el código en una solución. Algunos diseños posibles son:
	- No layers -> "Hacemos lo que podemos".
	- Package by layer -> "Multi-layer".
	- Package by feature -> Parecido al anterior pero agrupando por features.
	- Onion architecture -> Usada en microservicios.
	- Hexagonal architecture -> Usada en microservicios.

![[Ingenieria de Software II/img/Pasted image 20250317122614.png]]

## Package by Layer
- Separar el código en capas desde donde va a ser llamado. La capa superior conoce a la inferior, pero no se cumple la opuesta.
	- **Controller**: Recibe el cuerpo de la pegada y lo modifica para que el servicio opere cómodamente con instrucciones especificas.
	- **Servicio**: Contiene la lógica central de la aplicación, donde se implementan las reglas de negocio. Los servicios suelen coordinar entre controladores y repositorios.
	- **Repository**: Se encarga de la conexión con la base de datos. Abstrae lo mas posible al storage que se usa por debajo y se encarga de escribir y leer allí.
	- **Configuration**: Encargado de crear las configuraciones que van a ser usadas por las otras layers.

![[Ingenieria de Software II/img/Pasted image 20250317123353.png]]


## Stateless VS Stateful
- **Estado**: Condición o calidad de estar en un punto dado en el tiempo.
- **Stateful**: Retiene información sobre sesiones anteriores(Server-side generalmente).
	- Reaccionan en base al estado previo(sesión).
- **Stateless**: No retiene información sobre sesiones anteriores(Client-side generalmente).
	- Reaccionan a operaciones para modificar recursos. El estado esta en el cliente. 