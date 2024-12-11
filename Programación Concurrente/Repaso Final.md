# Repaso Final

## Final 26/07/2022

![](Programación%20Concurrente/img%20concu/Pasted%20image%2020241209144800.png)

1. Un deadlock ocurre cuando dos o más procesos o hilos en un sistema no pueden continuar con su ejecución debido a que cada uno de ellos se queda esperando a que otro libere un recurso que necesita. Aquí se genera un ciclo, ya que los procesos no pueden avanzar: Cada uno está esperando a que el otro libere el recurso requerido. Al tener un sistema distribuido, se tiene la necesidad de coordinación para que las entidades entren en su sección crítica. 


![](Programación%20Concurrente/Pasted%20image%2020241209145440.png)

1. El robo de trabajo se da cuando un worker comienza a tomar tareas de otros, debido a que se terminaron su trabajo y quedaron libres. La idea de esto es seguir exprimiendo el uso de las CPUs al máximo. Cada thread va a tener una cola de tareas asignadas, y la idea es que se vayan partiendo las tareas en sub-tareas cada vez más pequeñas, y que el thread vaya ejecutando las tareas del final de su cola. Cuando un thread no tiene más trabajo en su cola, toma tareas del inicio de la cola de otro thread(este es elegido de forma random, y se toma del principio de su cola para evitar colisiones), de forma tal de balancear aún más las cargas de trabajo en los threads.
2. Lo que se genera al tener una única cola de tareas es que los threads van a estar constantemente haciendo `lock` de la cola, y agrandaríamos los tiempos de espera de ciertos threads para que se les asigne un trabajo. -> No estamos aprovechando el uso intensivo de la CPU.