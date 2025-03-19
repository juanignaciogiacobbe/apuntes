# Multitasking y Comunicación
muchos programas a la vez en ejecucion
la idea es elegir el modelo que corresponda*(hay ventajas y desventajas en cada caso)



## Multithreading
- Recursos compartidos:
	- Heap.
	- Data Segment.
	- File Descriptors.
	- Code Segment(read-only). -> Se levanta y corre el mismo programa.
- Sincronización:
	- Soporte threading del SO(pthread-mutex, etc).
	- Soporte threading del runtime(threads Java, .NET, etc.).
	- Inter Process Communication(IPC). 
- Características clave:
	- Sencillo compartir información entre threads.
	- Alto acoplamiento entre componentes del sistema.
	- Escasa estabilidad -> 1 thread defectuoso afecta a todo el sistema.
	- Escalabilidad muy limitada. La memoria es unica, el procesador es unico, y no le puedo dar mas potencia a menos que frene todo y mejore la compu

## Multiprocessing
- Recursos compartidos:
	- Code Segment(read-only). -> Cada proceso tiene su propia memoria.
- Sincronización:
	- Inter Process Communication(IPC).
		- Signals
		- Shared memory
		- Sockets
		- Pipes/ FIFOs
		- Semáforos
		- Queues.
		- Locks
- Características clave:
	- No es trivial compartir información entre procesos.
	- Componentes separados, en general simples.
	- Más escalable y más estable que multithreading.
	- Sin tolerancia a fallos de hardware, sistema operativo, etc.
	- Los problemas los tiene el proceso consigo mismo(No comparte nada con nadie). Se gana performance(Paralelismo).


![[Sistemas Distribuidos I/img/Pasted image 20250313195631.png]]

---
## Propiedades de Sistemas Distribuidos
- Safety Properties(Siempre verdaderas)
	- Exclusión Mutua.
	- Ausencia de Deadlocks.
- Liveness Properties(Eventualmente verdaderas)
	- Ausencia de Starvation.
	- Fairness.

- Asegurar el estado safety de propiedades de un sistema se transforma en un pilar de la teoría de concurrencia.


| Basada en Algoritmos                                                                  | Basada en Abstracciones                                                  |
| ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------ |
| Sin existencia de abstracciones especiales.                                           | Basada en abstracciones provistas por el SO.                             |
| Condiciones lógicas simples para asegurar el cumplimiento de cierta Critical Section. | Permite construir mecanismos compuestos por combinaciones de las mismas. |

### Basados en Algoritmos
- Busy-Waiting: Responsable de la mayoría de los problemas de performance en sistemas concurrentes.
- Spin-Lock: Caso más simple de Busy-Wait(`while(flag)`).
- Algoritmos de Espera: Dekker, Lamport(del panadero), Peterson, etc.
- Operaciones Atómicas: Mecanismos provistos por un lenguaje para actualizar variables/objetos sin utilizar mecanismos de sincronización
	- Contadores atómicos de tipos POD(int, char, double, etc.).
	- CAS(Compare and Swap): Operación por excelencia para actualizar contenedores forma segura en ambientes multithreading.


---
## Inter-Process Communication(IPCs)
- Permiten la comunicación entre dos o más procesos.
- Provistos por el SO.
- Creación y destrucción exceden la vida del proceso
	- Usuario es responsable de la vida de los mismos.
	- Proceso `Launcher` y `Terminator` para administrar la vida de los mismos.
- Usualmente identificados por nombre.
- En Linux todos los IPCs son vistos como diferentes tipos de archivos.

![[Sistemas Distribuidos I/img/Pasted image 20250313181057.png]]

### Signals
- Existen 31 tipos distintos(`kill -l`).
- Cada proceso decide cuales handlear. `SIGSTOP` y `SIGKILL` son la excepción.
- Ejemplos de signals estándar:
	- `SIGINT` y `SIGTERM`: Graceful Quit.
	- `SIGSEGV`: Problemas en la memoria.
	- `SIGABRT`: Code assertions.
- Propagación de signals en threads.

### Shared Memory
- Mecanismo provisto por el SO(Linux) para compartir recursos.
- Abstracción inexistente en threads: Heap entre dos threads de un mismo proceso es compartido.
- Su tamaño se define al ser creada.
- Mutex es necesario solo si dos procesos no pueden acceder a la memoria al mismo tiempo(e.g. shared counter).

![[Sistemas Distribuidos I/img/Pasted image 20250313181527.png]]

### File Locks
- Control de acceso a un file descriptor
	`int flock(int fd, int operation);`
- Existen dos tipos
	- Shared Lock(R): Read only lock.
	- Exclusive Lock(W): RW lock. -> Sólo un exclusive lock por File.


### Pipes y FIFOs
- Pasaje de información directa entre 2 procesos.
- Linux provee una API de un archivo para la escritura/lectura.
- Unnamed Pipes(Pipes)
	- Comunicación entre procesos padre e hijo.
	- Dejan de existir al finalizar el proceso.
- Named Pipes(FIFO)
	- Comunicación entre dos procesos cualesquiera.
	- Viven en el SO por lo cual excede la vida del proceso.

![[Sistemas Distribuidos I/img/Pasted image 20250313181830.png]]


### Message Queues(System V)
- Procesos escriben/reciben bloques de bytes.
- Campo `mtype`
	- Identifica el tipo de mensaje.
	- Sender debe enviar mensajes con `mtype > 0`.
	- Receptor con `mtype = 0` recibe mensajes sin importar el `mtype`.
	- Caso esotérico: Receptor con `mtype < 0`.
- Mensajes leídos son removidos de la cola.
- Buffer size definido durante la creación.

![[Sistemas Distribuidos I/img/Pasted image 20250313182115.png]]

