# Patrones de Diseño



> [!IMPORTANT] Patron Strategy
> Es un patron de comportamiento que permite definir una familia de algoritmos, colocar cada uno de ellos en una clase separada y hacer sus objetos intercambiables.
> - Se toma una clase que hace algo especifico de muchas formas diferentes, y se extraen todos esos algoritmos para colocarlos en clases separadas llamadas *estrategias*.
> - La clase original, llamada *contexto*, debe tener un campo para almacenar una referencia a una de las estrategias. El contexto delega el trabajo a un objeto de estrategia vinculado en lugar de ejecutarlo por su cuenta.
> - La clase contexto no es responsable de seleccionar un algoritmo adecuado para la tarea. En lugar de eso, el cliente pasa la estrategia deseada a la clase contexto. -> Funciona con todas las estrategias a través de la misma interfaz genérica, que sólo expone un único método para disparar el algoritmo encapsulado dentro de la estrategia seleccionada.
> - El contexto se vuelve independiente de las estrategias concretas, así que puedes añadir nuevos algoritmos o modificar los existentes sin cambiar el código de la clase contexto o de otras estrategias.


![](Ingeniería%20de%20Software%20I/img/Pasted%20image%2020241127181817.png)



> [!IMPORTANT] Factory Method
> Es un patron creacional que proporciona una interfaz para crear objetos en una superclase, mientras que permite a las subclases alterar el tipo de objetos que se crearan.
> - En lugar de llamar al operador `new` para construir objetos directamente, se invoque a un método *fabrica* especial. Los objetos se siguen creando a través del operador `new`, pero se invocan desde el método fabrica. Los objetos devueltos por el método fabrica a menudo se denominan *productos*.

![](Ingeniería%20de%20Software%20I/img/Pasted%20image%2020241127182244.png)