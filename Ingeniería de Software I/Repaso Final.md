# Repaso Final


## Repaso Parcial 2C24
1. Refactorizar el siguiente fragmento de código:

```
…SomeClass…{
	…
	bool wasInitialized(){
		return…
	}
	
	someFunction… {
		if ((platform.toUpperCase().indexOf("MAC") > -1) 
			&& (platform.toUpperCase().indexOf("IE") > -1)
			&& wasInitialized() 
			&& resize > 0) {
		  someCode();
		} 
		otherCode();
		}
}
```
Este codigo viola el principio de Open Closed, debido a que si queremos agregar una nueva `platform`, tendremos que modificar el comportamiento interno de la clase. Ademas, si suponemos que el metodo `wasInitialized` nos devuelve un estado interno de la clase, estariamos tambien violando este principio, porque en un futuro podriamos querer agregar algun estado nuevo, y tendriamos que tocar de nuevo el codigo interno de la clase.

Se propone:
- Crear una abstracción para manejar la plataforma: de esta forma cada plataforma define su comportamiento interno, y `someFunction` simplemente debería llamar al método de la clase(obviamente, `SomeClass` ahora tendría que conocer su plataforma).
- Utilizar el patrón de diseño `State` para manejar el estado la clase(lo que corresponde con el método `wasInitialized`).

Con estos cambios no se viola el principio de Open Closed, y si en un futuro se quisiera extender a `SomeClass`, se podría hacerse sin tener que modificar su código interno.

2. Nombre las ceremonias de Scrum y detalle brevemente cada una.

![](Ingeniería%20de%20Software%20I/img%20is1/Pasted%20image%2020240925154736.png)


3. Explique las ventajas del uso del modelo de vistas de 4+1 para una arquitectura de software, haga un ejemplo de una posible vista de despliegue.

	Modelar nuestras arquitecturas con el Modelo de Vistas 4+1 nos da las siguientes ventajas:
	- Permite a través de diferentes vistas analizar distintas perspectivas del problema, focalizándose en el problema en cuestión.
	- Concentra en un único documento las principales decisiones tomadas sobre el sistema.
	- Permite a nuevos integrantes del equipo entender la arquitectura del sistema y ubicarse dentro de la solución.
	- Permite discutir con todos los stakeholders las distintas decisiones y validarlas en una etapa temprana.


4. ¿Qué es refactoring? Como se asegura de lograrlo. De un ejemplo simple con código.

	El Refactoring consiste en modificar el código interno de alguna clase, método o función, sin modificar su comportamiento interno. La idea de aplicar refactoring surge de la necesidad de mejorar la calidad del código, aplicando en lo posible buenas prácticas, y adecuándose a un mejor diseño siguiendo heurísticas y patrones de diseño. 
	
	Mediante el uso de tests unitarios de los fragmentos que vayamos a refactorizar, nos aseguramos de no modificar el comportamiento externo de lo que cambiemos.

5. ¿Qué es un code smell? Nombre dos, y ejemplifíquelos con código.

	Es cualquier característica en el código fuente de un programa que posiblemente indique un problema más profundo. Los code smell aparecen cuando al revisar fragmentos de código, se detectan malas prácticas tanto semánticas(por ejemplo un código con demasiados comentarios), como de diseño(por ejemplo si se viola algún principio SOLID, o si tenemos funciones con demasiados parámetros).


---
## Parcial Memo II 1C24
### Ejercicio 1
![](Ingeniería%20de%20Software%20I/img%20is1/Pasted%20image%2020241206175757.png)

1. Login de usuarios: 
	- Endpoint: `POST /api/v1/auth/login`
	- Body: `{"username": <username>, "password": <password>}`
	- Respuesta: `{"accessToken": <JWT_access_token>, "refreshToken": <refresh_token>}`
2. Renovación del token:
	- Endpoint: `POST /api/v1/auth/refresh`
	- Body: `{"refresh_token": <refresh_token>}`
	- Respuesta: `{"accessToken": <JWT_access_token>}`
3. Registro de Usuarios:
	- Endpoint: `POST /api/v1/user/register`
	- Body: `{"username": <username>, "password": <password>, "firstName": "Juan", "lastName": "Pérez", "dateOfBirth": "1990-01-01", "gender": "male", "avatarUrl": "https://example.com/avatar.jpg"}`
	- Respuesta: `201 Created`
4. Listar eventos: 
	- Endpoint: `GET /api/v1/events`
	- Query Parameters: `name, date, location`(todos opcionales).
	- Respuesta: `{ "currentPage": 1, "pageSize": 10, "totalPages": 5, "totalItems": 50, "events": [{ "id": 1, "name": "Maratón Bogotá", "date": "2024-01-20", "location": "Bogotá", "details": "Evento anual de running.", "photoUrl": "https://example.com/photo.jpg" }]}
`
### Ejercicio 2
![](Ingeniería%20de%20Software%20I/img%20is1/Pasted%20image%2020241206175101.png)

Un atributo de calidad es una medida o propiedad testeable que tiene un sistema, y sirve para indicar cómo satisface las necesidades de sus stakeholders. 


> [!NOTE] Disponibilidad
> Capacidad del sistema para estar en funcionamiento y accesible cuando se lo necesita.
> Es esencial para garantizar que los sistemas de software cumplan con las expectativas de los usuarios y las necesidades del negocio.
> Se deben implementar estrategias para mitigar fallos y garantizar la continuidad del servicio.


> [!NOTE] Performance
> Tiempos de respuesta de la aplicación en relación a las funcionalidades o actividades soportadas por la misma.
> Se consideran dos métricas para medir el rendimiento de una aplicación:
> 	- **Latencia**: Tiempo dedicado a responder un evento.
> 	- **Capacidad**: El número de eventos que pueden ocurrir en un tiempo determinado.

Si desarrollamos interfaces muy poco usables(difíciles de usar, incomprendibles, ...), los usuarios pueden llegar a ignorar la protección de sus datos y cuentas. Es primordial desarrollar aplicaciones que sean usables para una amplia cantidad de usuarios, y que además les permita adoptar medidas de seguridad de una manera sencilla para proteger sus datos.

### Ejercicio 3
![](Ingeniería%20de%20Software%20I/img%20is1/Pasted%20image%2020241206104043.png)

Code Smells:
1. Uso excesivo de getters(viola Tell, Don't Ask). 
2. Viola encapsulamiento -> El método accede a los datos de otro objeto.
3. Long Method y Message Chains.

Principios SOLID que se violan:
1. Single responsibility: porque si el día de mañana se agrega mas comportamiento cuando se envía un sendSMS o un sendDiscord, el método tendría mas de una razón de cambio, y por lo tanto viola el principio. 
2. Open Close: Booleanos por parámetro -> El día de mañana quiero enviar mensajes por otro medio y debería agregar otro parámetro y otro condicional más, haciendo mas difícil mantener el código. 

### Ejercicio 4
1. Explique las ventajas y desventajas del flujo de trabajo Trunk-Based en Git, en el cual se trabaja en un único branch principal.

	La ventaja principal de este flujo de trabajo es su simpleza, debido a que solo se maneja un único branch, y el equipo de desarrollo no maneja múltiples branches. El código está en el último commit de esta branch, y eso puede ser una desventaja muy grande porque es muy complicado separar líneas de trabajo, y si tenemos un equipo que cada vez es más grande, terminamos teniendo muchos conflictos para manejar el entorno. Esto tiene como causa principal de que Git además de ser distribuido, es concurrente: tenemos que asegurarnos de que varias personas pueden trabajar en un mismo espacio de trabajo a la vez(concurrentemente), y justamente este flujo de trabajo trae muchos problemas para trabajar concurrentemente. Se vuelve inmanejable si tenemos un equipo grande.


2. Escriba los comandos y el comentario del commit asociado a una tarea para realizar el cambio de pasar como dato obligatorio a la fecha de nacimiento ya que solo se podrán registrar personas de más de 16 años.

	`git branch` -> Con esto vemos la branch actual.
	`git checkout [-b] <nombre_de_la_nueva_branch>` -> En caso de querer hacer el commit en otra branch, se hace checkout a la branch deseada.
	`git status` -> Con esto detectamos los archivos que fueron cambiados, para que al hacer `add` solamente agreguemos los que nos interesan para el commit.
	`git add <archivos_que_interesan>` -> Con esto agregamos para el commit los archivos que nos interesan. Si hacemos `git add .`, puede pasar que agreguemos archivos "de más" para nuestro commit(La idea es que los commits sean atómicos y acordes a lo que se va a especificar en el comentario del commit, no tiene sentido agregar otras cosas).
	`git commit -m <mensaje_del_commit>` -> Con esto se realiza el commit a la branch actual.

	Mensaje del commit: "feat: se pasa como dato obligatorio a la clase Registrador la fecha de nacimiento del nuevo usuario, debido a que solo se pueden registrar personas de más de 16 años.".