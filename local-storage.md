Es muy interesante conocer esta funcionalidad que nos permite guardar información en forma de clave-valor en el navegador.

- **Local storage**: Guardamos información que se mantendrá hasta borremos los datos de navegación.
- **Session Storage**: Guardamos información que se mantiene hasta que cerremos la pestaña.


### Guardar datos

**setItem(clave, valor)** – almacenar un par clave/valor. 


```jsx
localStorage.setItem('usuario', 'edu');
sessionStorage.setItem('usuario', 'edu');
```


### Obtener datos

**getItem(clave)** – obtener el valor por medio de la clave.


```jsx
localStorage.getItem('usuario');
sessionStorage.getItem('usuario');
```


### Eliminar datos

**removeItem(clave)** – eliminar la clave y su valor. 


```jsx
localStorage.removeItem('usuario');
sessionStorage.removeItem('usuario');
```


### Borrar por completo

**clear()** – borrar todo.


```jsx
localStorage.removeItem('usuario');
sessionStorage.removeItem('usuario');
```
  

### Accediendo a las claves

- **key(índice)** – obtener la clave de una posición dada.
- **length** – el número de ítems almacenados.


```jsx
for(let i=0; i<localStorage.length; i++) {
  let key = localStorage.key(i);
  console.log(`${key}: ${localStorage.getItem(key)}`);
}
```


### GUARDAR OBJETOS


```jsx
localStorage.user = JSON.stringify({name: "Edu", lastName: "Cuadrado"});

let user = JSON.parse( localStorage.user );
console.log( user.name ); 