
> [!IMPORTANT] Entidades
> Es la unidad de cómputo de ambiente informático distribuido.
> - Puede ser un [Proceso](Sistemas%20Operativos/Proceso.md), un procesador, etc.


> [!WARNING] Capacidades de las Entidades
- Acceso de lectura y escritura a una memoria local(no compartida con otras entidades):
	- Registro de estado: `status(x)`.
	- Registro de valor de entrada: `value(x)`.
- Procesamiento Local.
- Comunicación: Preparación, transmisión y recepción de mensajes.
- Setear y resetear un reloj local.


> [!NOTE] Eventos Externos
> - La entidad solamente responde a eventos externos(es reactiva).
> - Los posibles eventos externos son: Llegada de un mensaje, activación del reloj o un impulso espontáneo.
> - A excepción del impulso espontáneo, los eventos se generan dentro de los límites del sistema.

---

> [!IMPORTANT] Acción
> Secuencia finita e indivisible de operaciones. Es atómica porque se ejecuta sin interrupciones.


> [!IMPORTANT] Regla
> Es la relación entre el evento que ocurre y el estado en el que se encuentra la entidad cuando ocurre dicho evento, de modo tal que:
> `estado x evento -> acción`


> [!IMPORTANT] Comportamiento
> Es el conjunto `B(x)` de todas las reglas que obedece una entidad `x`. 
> - Para cada posible evento y estado debe existir una única regla `B(x)`.
> - `B(x)` se llama también protocolo o algoritmo distribuido de `x`.
> 
> Comportamiento colectivo del ambiente distribuido:
> `B(E) = B(X) para todo x perteneciente a E`


---

> [!IMPORTANT] Costo y Complejidad
> Son las medidas de comparación de los algoritmos distribuidos. Se tienen en cuenta:
> - Cantidad de actividades de comunicación: 
> 	- Cantidad de transmisiones o costo de mensajes M.
> 	- Carga de trabajo por entidad y carga de transmisión.
> - Tiempo:
> 	- Tiempo total de ejecución del protocolo.
> 	- Tiempo ideal de ejecución: Tiempo medido bajo ciertas condiciones, como delays de comunicación unitarios y relojes sincronizados.

