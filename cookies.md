## Introducción

Las cookies son cadenas de datos que almacenamos directamente en el navegador.

Por lo general se establecen directamente por el servidor web, a través de una cabecera en la respuesta HTTP. Por ejemplo cuando iniciamos sesión se setea una cookie a través de la cabecera Set-Cookies y ya todas las peticiones que se hagan a ese servidor llevan la cabecera Cookie que sirve para que el navegador conozca quien hizo la solicitud.

A nivel de cliente también podemos trabajar con cookies. Tenemos que entenderlas como cadenas que tienen parámetro y valor y están separadas por ; 


```jsx
nombre=<valor>; expires=<fecha>; max-age=<segundos>; path=<ruta>; domain=<dominio>;
```


**Parámetros**

- **nombre=<valor> :** Requerido. **<nombre>** es el nombre (key) que identifica la cookie y **<valor>** es su valor.
- **expires=<fecha> y max-age=<segundos>** : Opcional. Ambos parámetros especifican el tiempo de validez de la cookie. **expires** establece una fecha (ha de estar en formato UTC) mientras que **max-age** establece una duración máxima en segundos.
- **path=<ruta> :** Opcional. Establece la ruta para la cual la cookie es válida. Si no se especifica ningún valor, la cookie será **válida para la ruta la página actual**.
- **domain=<dominio> :** Opcional. Dentro del dominio actual, subdominio para el que la cookie es válida.
- **secure :** Opcional. Parámetro sin valor. Si está presente la cookie sólo es válida para **conexiones encriptadas** (por ejemplo mediante protocolo HTTPS).

 

## document.cookie

Es con lo que tenemos que quedarnos a nivel de javascript pudiendo desde el lado del cliente, crear, leer, modificar o eliminar cookies.


### CREAR

 
```bash
document.cookie = "cookie1=valorcookie; max-age=3600; path=/";
document.cookie = "usuario=Edu"; 
```


Recuerda que las cookies se envían en las cabeceras HTTP y, por tanto, deben estar correctamente codificadas. Puedes utilizar **encodeURIComponent()**, acostúmbrate a utilizarlo siempre para evitarte sorpresas.

A nivel de parámetro expires, tenemos que tener en cuenta que la fecha tiene que estar en formato UTC por lo que nos será de gran ayuda el **Date.toUTCString().**


```bash
let fecha = new Date("2027-01-26");
document.cookie = "cookie3=1;expires="+fecha.toUTCString();
```
 

### MODIFICAR COOKIE

Para modificar el valor solo hay que sobrescribirla.

```bash

document.cookie = "cookie3=2";
```


Hay que tener en cuenta que si hemos establecido un path específico tenemos que volver a ponerlo porque si no será una nueva cookie.


### ELIMINAR COOKIE

Utilizaremos el expires o el max-age


```jsx
document.cookie = "nombre=; expires=Thu, 01 Jan 1970 00:00:00 UTC";
document.cookie = "nombre=; max-age=0";
```
 

### OBTENER VALOR

Tenemos que tener en cuenta que no hay un método de lectura para cada cookie a nivel individual por lo que se muestra un string con todas las cookies creadas y los valores.

```jsx
console.log(document.cookie)
```

Solo aparecerán las cookies del dominio en el que estemos.