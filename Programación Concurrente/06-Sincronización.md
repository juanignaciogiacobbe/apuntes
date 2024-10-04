
> [!IMPORTANT] Semáforos
> Es un mecanismo de sincronizacion, implementado como una construcción de programación concurrente de mas alto nivel.
> Es un tipo de dato compuesto por dos campos:
> - Un entero no negativo llamado *V*.
> - Un set de procesos llamado *L*.

 ## Inicialización de semáforos
 - Se inicializan con un valor $k \geq 0$ y con el conjunto vacío $\emptyset$.
 - Se definen dos operaciones atómicas sobre un semáforo S:
	 - `wait(S)` también llamada `p(S)`.
	 - `signal(S)` también llamada `v(S)`.
- Un semáforo debe inicializarse con un valor entero no negativo.
- La instrucción `signal()` debe despertar a uno de los procesos suspendidos, pero no esta definido cual de todos los procesos debe despertarse.


## Sincronismo de acceso a un recurso
- Un semáforo es un contador:
	- Si contador $> 0$ -> Recurso disponible.
	- Si contador $\leq 0$  -> Recurso no disponible.
	- El valor del semáforo representa la cantidad de recursos disponibles.
	- Si el valor es 0 o 1, se llaman semáforos binarios y se comportan igual que los [Locks](Programación%20Concurrente/05-Locks.md) de escritura(También conocidos como `Mutex`).
- `p (wait)`: Resta 1 al contador.
- `v (signal)`: Suma 1 al contador.

## Semáforos en Rust
- Obtener el acceso(wait):

```
fn acquire(&self)
```

- Liberar el semáforo(signal):

```
fn release(&self)
```



> [!IMPORTANT] Barreras en Rust
> Permiten sincronizar varios threads en puntos determinados de un calculo o algoritmo.
> Son reutilizables automáticamente.
