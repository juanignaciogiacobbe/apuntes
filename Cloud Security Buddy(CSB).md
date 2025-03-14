# Pitch: Cloud Security Buddy

## Contexto
- ¿Cómo surge Cloud Security Buddy?
- Hoy en día muchas empresas están decidiendo migrar a la nube de AWS, atraídas por las bondades y servicios que ofrece, como puede ser el costo "on-demand"(solo pago por lo que uso), alta disponibilidad y el alto rendimiento que se puede obtener.
- Al tener infraestructuras muy complejas, muchas veces quedan muy expuestas a posibles ciberataques. Es por esto que AWS propone su modelo de madurez de seguridad: un camino que las empresas pueden seguir para asegurar sus infraestructuras en la nube.

## Problema
- Con infraestructuras muy complejas, y con necesidades y políticas muy marcadas, muchas veces esta adaptación al modelo propuesto de AWS se vuelve muy complicado, tanto para la empresa, como para el equipo encargado de desplegar la infraestructura.

## Solución
- Cloud Security Buddy es una herramienta que monitorea constantemente la infraestructura en AWS que posee el cliente, y en base a sus necesidades y a su "hambre de riesgo", acompaña de una manera personalizada al cliente para desplegar su infraestructura de forma automatizada. Todo esto siguiendo el estándar del modelo de madurez de seguridad de AWS.
- Este sistema realiza las tareas de un equipo completo de seguridad, de una manera rápida y altamente customizable, en un solo lugar(nuestra web).

## Modelo de Negocio
- El usuario contrata al servicio, y linkea su cuenta de AWS a Cloud Security Buddy(otorga permisos necesarios)
- Este va a monitorear la infraestructura y va a ayudar al usuario con recomendaciones de seguridad.
- Por último, se encarga de desplegar la infraestructura de manera automatizada.



---


## Proceso principal de CSB

### Relevamiento de infraestructura
1. necesito una entidad que se encargue de leer los permisos sobre aws generados por el cliente, y que comience a extraer data de ahi(por ejemplo, que sea capaz de traernos datos de cloudtrail). -> EXTRACT
2. los datos traidos de esta entidad debe estar estandarizada(tiene que estar organizada) para futuro relevamiento.
3. Necesito otra entidad que entienda estos datos traidos por la anterior, y de esta forma generar el relevamiento(y estadisticas) y poder comparar contra el modelo de madurez. -> COMPARE
4. Generacion de recomendaciones para la infra -> El cliente decide que quiere agregar, editar o borrar -> RECOMMEND
5. Realizamos los cambios (otra entidad) -> DEPLOY
