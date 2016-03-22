---
layout: post
title: Nuevo Proyecto
---

Estoy trabajando ahora en una simple libreria matemática con un interprete matemático con una sintaxis similar a MATLAB, que permita cierta flexibilidad para poder crear Funciones personalizadas.

De momento el objetivo a corto plazo es generar una clase ValorNumerico que contenga un vector de bits , un entero que represente el tipo, otro entero que represente la posición de la coma flotante,un booleano que indique si el tamaño del vector puede crecer y un booleano que inidca si es con signo o sin signo.

Los tipos podrán ser Boolean (longitud 1 del vector), integer (cualquier longitud y el primer bit representa positivo "0" o negativo "1"),double (primer bit positivo o negativo, y una variable extra que indique la posición de la coma flotante) y complejo que será el doble de longitud que el anterior (double real y double imaginario).
En un futuro se puede añadir más tipos como por ejemplo racionales de forma que un valor represente el numerador y otro el denominador para no perder precision en las divisiones o incluso si me apuras poder llegar a los hipercomplejos.

Otro objetivo será la clase Operando que contiene un array de objetos de la clase ValorNumerico, un objeto de clase Variable (Implementación de sistema de resolución de ecuaciones). Este objeto es bastante flexible pues cada ValorNumerico del array puede ser de distinto tipo y en el momento que lo necesitemos para operar se harán autocast directamente desde la clase ValorNumerico de forma que el casteo se haga hacia arriba (si es posible, si no hay forma de que se pueda hacer saltara una excepcion): Boolean>Entero>Racional>Real>Complejo>HiperComplejo. Los irracionales se autocastearan a reales con una precisión fijada en una clase que defina opciones de configuración de la libreria.

Despues ya vendra el interprete, habiendo hecho previamente la implementación de operaciones basicas (suma resta multiplicacion division modulo conjugado elevacion etcetc)

Saludos
[a IngenieroFiestero](https://github.com/IngenieroFiestero)
