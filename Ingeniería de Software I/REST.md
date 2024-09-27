> [!NOTE] Representational State Transfer(REST)
> Utiliza estándares existentes como HTTP.
> Comunicación Client-Server.

## Características del REST
- Arquitectura Client-Server.
- Stateless.
- Cacheable.
- Expone recursos(URIs)
- Usa explicitamente los verbos HTTP.
- Navegable.


> [!WARNING] Stateless

- Cada request se ejecuta de forma independiente al resto.
- Cada request contiene toda la información necesaria para completarse.
- La API no mantiene ningún tipo de sesión.
- Se promueve el uso de tokens para el manejo de la seguridad.


> [!WARNING] Cacheable
- Es la capacidad de estos sistemas para etiquetar de alguna forma las respuestas para que otros mecanismos intermedios funcionen como un cache.
- Estos sistemas o mecanismos intermedios deben ser por lo general transparentes para los desarrolladores, no deben afectar la manera en que los servidores se consumen.
- Reduce el ancho de banda usado.
- Reduce la latencia.
- Reduce la carga en servidores.
- Oculta fallos de red.

![](../img/Pasted%20image%2020240927083631.png)

> [!WARNING] Compresion
> Las APIs suelen retornar representaciones en varios formatos, entre ellos el formato plano, XML, JSON, etc, y estos formatos pueden ser comprimidos para ahorrar ancho de banda sobre la red.

![](../img/Pasted%20image%2020240927083809.png)



> [!WARNING] Uniform Resource Identifier(URI)

- Identificacion univoca de recursos con cadenas de caracteres.
- Identifica los recursos por clase o tipo.
- Uso de sustantivos en plural por convención. **NO verbos**.
- Distinción de recursos principales y subordinados.

![](../img/Pasted%20image%2020240927084054.png)


# HTTP Requests

> [!WARNING] Verbos HTTP - Requests

- **GET**: Solicita una representacion de un recurso especifico.
- **POST**: Se utiliza para enviar una entidad a un recurso en especifico.
- **DELETE**: Borra un recurso en especifico.
- **PUT**: Reemplaza todas las representaciones actuales del recurso de destino con la carga util de la petición.
- **PATCH**: Aplica modificaciones parciales a un recurso(A diferencia de PUT).
- **OPTIONS**: Es utilizado para describir las opciones de comunicación para el recurso de destino.


> [!WARNING] HTTP Status Codes - Responses

- 1XX: Informational.
- 2XX: Success.
- 3XX: Redirection.
- 4XX: Client Error.
- 5XX: Server Error.

![](../img/Pasted%20image%2020240927084517.png)