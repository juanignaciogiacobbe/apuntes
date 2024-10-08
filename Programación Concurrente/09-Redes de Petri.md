# Red Ordinaria de Petri
- Es un grafo dirigido bipartito que cumple con:

$$
PN = (T, P, A)
$$

- $T = t_1, t_2, ..., t_n$ es un conjunto de nodos llamados transiciones.
- $P = p_1, p_2, ..., p_n$ es un conjunto de nodos llamados lugares.
- $A \subseteq (T x P) \cup (P x T)$ es un conjunto de arcos. 

![](img%20concu/Pasted%20image%2020241004163711.png)

- $p_i$  son los estados del sistema.
- $t_i$ son los eventos que ocasionan los cambios de estado.


## Función de Marca
$$
M: P \rightarrow N \cup 0
$$

- Cuando el token está en el lugar $p_1$, entonces $M(P_1) = 1$ y $M(p_2) = 0$. Por lo tanto $M_0 = (1, 0)$.

## Funciones de Entrada y Salida
- Sea $t \in PN(T, P, A)$ una transición $t$, se definen las funciones:
	- $I(t) = p/ p \in P/ (p, t) \in A \subset P$ es la entrada o *input* de la transición $t$.
	- $O(t) = p/ p \in P/ (t, p) \in A \subset P$ es la salida o *output* de la transición $t$.