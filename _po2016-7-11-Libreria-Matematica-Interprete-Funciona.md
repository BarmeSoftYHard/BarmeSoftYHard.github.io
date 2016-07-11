---
layout: post
title: Nueva Actualizacion de la Libreria Matematicca
---
# El interprete Matematico ya funciona
He seguido el pensamiento de divide y venceras, de forma que empieza creando las operaciones de sumas y luego las de multiplicaciones. 
Aunque parezca algo descabellado y sin sentido, por la forma de trabajar si que lo tiene y simplifica mucho el codigo.
De esta forma el codigo:


```
[a,b] = x + pepe(2,3) + miFuncion(miFuncion2(),6+7);
Primero crearia la operacion de linea limpia ";" (No imprimir nada por pantalla) y pasaria a analizar:
[a,b] = x + pepe(2,3) + miFuncion(miFuncion2(),6+7)
Ahora asignaria a las variables "a" y "b" el resultado de 
x + pepe(2,3) + miFuncion(miFuncion2(),6+7)
Ahora crearia una suma con los operandos: "x" y "pepe(2,3) + miFuncion(miFuncion2(),6+7)"
Despues, por un lado analizaria el valor de x y por el otro crearia otra suma con los operandos:
"pepe(2,3)" y "miFuncion(miFuncion2(),6+7)"
Y asi seguiria dividiendo los codigos en operaciones sencillas.
```
Con este sistema se crea un vector de operaciones sencillas y sin referencias de java pues los operandos se obtienen haciendo 
llamadas a la misma funcion de forma recursiva y obteniendo un ID que indica la posicion de dicha operacion dentro del vector.
Esto nos permite almacenar la lista de operaciones en disco (Ya implementado) y poder recuperarlas sin tener que reinterpretar el script.
Ademas estas operaciones no estan ligadas a ningun contexto matematico ni a ningun interprete.
[Link del Proyecto](https://github.com/IngenieroFiestero/EngineeringMathTool)

Saludos
[IngenieroFiestero](https://github.com/IngenieroFiestero)
