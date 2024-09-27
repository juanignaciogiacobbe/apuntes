# REST Security Design Principles
- Least Privilege: Tener el menor privilegio requerido para hacer las acciones.
- Fail-Safe Defaults: Por defecto no tener acceso a los recursos.
- Complete Mediation: El sistema debe validar los permisos de acceso a todos los recursos.
- KISS.
- Uso de HTTPS.
- Password Hashes.
- Never expose information on URLs.
- Considerar agregar Timestamp en los requests.
- Validación de los parámetros de entrada.


> [!WARNING] Monitorizacion de transacciones sospechosas

- Cantidad de requests por IP o por token/JWT/user para evitar problemas de DoS, o simplemente controlar o reducir el uso excesivo que puede bajar la performance de la API en general.
- Limitación de velocidad, o tiempos de demora agregados entre requests para ciertos casos, ayuda a reducir las solicitudes excesivas que ralentizarían la API, ayuda a lidiar con llamadas/ejecuciones accidentales y monitorea e identifica de manera proactiva una posible actividad maliciosa.


## Authentication y Authorization