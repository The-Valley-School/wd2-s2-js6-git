En este video vamos a trabajar con circunstancias que se pueden dar a la hora de trabajar con git y veremos como solucionarlas.


### git reset - quitando ficheros de fase stage

Comando que nos ayuda a quitar ficheros que tenemos en fase stage y queremos sacar porque no queremos que vayan a commit


```bash
git reset HEAD path/fichero
```


### git checkout - restaurando un fichero

Comando que nos ayuda a volver al estado inicial de un fichero.


```bash
git checkout -- path/fichero
```
  

### git reset - eliminando un commit

Para eliminar un commit y no subirlo al repositorio remoto hacemos:


```bash
git reset HEAD~1
```
  

### git log / git checkout - moverse por los commits

Podemos movernos por los commits y revisar como estábamos en un momento específico

El comando git log nos permite ver los commits realizados:


```bash
git log
```
   

Para movernos al commit que queramos usamos: 


```bash
git checkout referencia-commit
```
   

Y para volver a la posición donde estamos
 

```bash
git checkout main
```