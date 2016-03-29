---
layout: post
title: Actualización de la libreria matemática
---
# Reconstrucción
Estoy reconstruyendo desde cero la libreria, ahora solo permite trabajar con complejos y utilizando directamente double y no BigDecimal, 
lo cual conlleva una serie de problemas como por ejemplo que se pierda cierta precision al dividir. Para solucionar esto último he añadido una tercera variable
para permitir almacenar un denominador, de esta forma la operación:

```
(4-2.5i)/(6i) deberia darnos 0.4166666666666667 0.6666666666666666i
Pero si nos fijamos en su representación interna vemos:
Numerador: 15.0 +24.0i
Divisor:36.0
Con lo que todavía no hemos perdido ningún tipo de precision pues no hemos "dividido" 
solo multiplicado y sumado que son operaciones donde no se pierde precisión.
```
[Link del Proyecto](https://github.com/IngenieroFiestero/EngineeringMathTool)
