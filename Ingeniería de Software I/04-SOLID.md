# Principios S.O.L.I.D.

> [!IMPORTANT] Single Responsibility Principle
> There should never be more than one reason for a class to change.
> - In this context, we define a responsibility to be “a reason for change.”
> - If a class has more then one responsibility, then the responsibilities become coupled.

![](img/Pasted%20image%2020240925152028.png)


> [!IMPORTANT] Open-Closed Principle
> **Software entities should be open for extension, but closed for modification.**
> - When a single change to a program results in a cascade of changes to dependent modules, that program exhibits the undesirable attributes that we have come to associate with “bad” design.
> - This principle says that you should design modules that never change. 
> - It requires a dedication on the part of the designer to apply abstraction to those parts of the program that the designer feels are going to be subject to change.


> [!WARNING] OCP Heuristics
> 1. Make all member variables private.
> 2. No Global Variables.
> 3. Runtime type identification is dangerous.

![](img/Pasted%20image%2020240925152349.png)