> [!IMPORTANT] Arquitectura de Software
> Estructura o las estructuras de un sistema, que consta de componentes de software, las propiedades visibles externamente y las relaciones entre ellas.
> "Son aquellas decisiones que son importantes y difíciles de cambiar".


> [!IMPORTANT] Decisiones de Arquitectura
> Decisiones de Diseño que abordan requisitos significativos desde el punto de vista arquitectónico.
> Se perciben como difíciles de hacer y/o costosos de cambiar.
> Estas decisiones son importantes de guardarlas y conocerlas. Conocer el motivo por el cual se tomó dicha decisión en la arquitectura o diseño.

# Modelo de Vistas 4 + 1
- Permite a través de diferentes vistas analizar distintas perspectivas del problema, focalizándose en el problema en cuestión.
- Concentra en un único documento las principales decisiones tomadas sobre el sistema.
- Permite a nuevos integrantes del equipo entender la arquitectura del sistema y ubicarse dentro de la solución.
- Permite discutir con todos los stakeholders las distintas decisiones y validarlas en una etapa temprana.

![](../img/Pasted%20image%2020240925163648.png)


> [!IMPORTANT] Vista Lógica
> Apoya principalmente los requisitos funcionales.
> Se aplican los principios de abstracción, encapsulamiento y herencia.
> Esta descomposición no sólo hace para potenciar el análisis funcional, sino también sirve para identificar mecanismos y elementos de diseño comunes a diversas partes del sistema.


> [!IMPORTANT] Vista de Procesos
> Toma en cuenta algunos requisitos no funcionales como el rendimiento y la disponibilidad.
> Se enfoca en asuntos de concurrencia y distribución, integridad del sistema, y de la tolerancia a fallas.


> [!IMPORTANT] Vista de Desarrollo(o Componentes)
> Se centra en la organización real de los módulos de software en el ambiente del desarrollo de software.
> Tiene en cuenta los requisitos internos relativos a la facilidad de desarrollo, administración del software, reutilización y elementos comunes, y restricciones impuestas por las herramientas o el lenguaje de programación que se use.


> [!IMPORTANT] Vista Física(o de Despliegue)
> Toma en cuenta primeramente los requisitos no funcionales del sistema tales como la disponibilidad, confiabilidad, rendimento y escalabilidad.


> [!IMPORTANT] Vista de Escenario
> Los escenarios son de alguna manera una abstracción de los requisitos más importantes.
> Sirven como una guía para descubrir elementos arquitectónicos durante el diseño de arquitectura.
> Sirven como un rol de validación e ilustración después de completar el diseño de arquitectura, en el papel y como punto de partido de las pruebas de un prototipo de la arquitectura.




