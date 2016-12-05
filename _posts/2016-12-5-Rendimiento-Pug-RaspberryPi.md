---
layout: post
title: Rendimiento PUG (Jade) en RaspberryPi
---

Para los interesados desarrollando algun proyecto con raspberrypi y nodejs que esten utilizando como motor de plantillas PUG antes conocido como Jade,
les puede interesar saber el rendimiento real que provee.
#### Codigo de prueba:


```
router.get('/', function(req, res, next) {
    console.log("Tiempo en / pre: "+ process.hrtime());
    res.render('index', {});
    console.log("Tiempo en / post: "+ process.hrtime());
});
```


### Modo desarrollo
En un primer momento utilice response-time (npm install response-time) para medir por medio de cabeceras el tiempo que tardaba en ser procesada una peticion.
Para mi sorpresa en un PC normal no notas nada (0.2 segundos) pero en una raspberry el tiempo crecia hasta los 5 segundos. 
Tras comprobar posibles problemas de rendimiento con mongodb y demas probe como ultima posibilidad que fuera del motor de plantillas.

El resultado en modo **desarrollo**:

Tiempo en / pre: 3435,818894232
Tiempo en / post: 3440,426644061

Como podemos ver hay una diferencia de casi 5 segundos que tarda en procesar un template.

### Modo produccion
Añadiendo las siguientes lineas en app.js:


```
app.locals.compileDebug = false;
app.locals.cache = true;
```

Obtenemos como resultado

Tiempo en / pre: 6156,717597260

Tiempo en / post: 6156,728755599

O lo que es lo mismo un tiempo de respuesta de **0.1 segundo** una mejora bastante notable que nos muestra la potencia que tiene realmente pug cuando trabaja en modo produccion.

Saludos
[IngenieroFiestero](https://github.com/IngenieroFiestero)
