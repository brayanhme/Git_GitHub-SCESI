			README.md
#Trabajo Individual

Brayan Herland Mancilla Escalera

##Clase 1
### Que es GIT ?

Es un controlador de versiones, util para guardar versiones a medida que 
un proyecto avanza.

### Origen de GIT

El mismo creador de Linux, Linus Torvalds desarrollo GIT. 
Li hizo ya que BitKeeper decidio quitar su acceso a Linus y su comunidad.
Entonces Linus se enojo y dijo: Si no puedo tenerlo, lo creare yo mismo 
y mejor.
Asi en 2 semanas, creo GIT que ahora es estandar para control de versiones.

### Intalar GIT
Hay que ir a la pagina oficial de GIT y seguir pasos segun el sistema 
operativo que usas.

### Configuraciones iniciales
Se debe crear usuario y email, con los que se te asociaran.
Comandos:

```
git config --global user.name ¨Nombre¨
git config --global user.name ¨email¨
```
Crear una carpeta para el Trabajo Personal.
Y colocar en terminal estando en la carpeta creada:

```
git init
git add README.md
git status
git commit -m ¨Primer commit¨
```

## Clase 2

### ESTADOS DE GIT

### 1ra Estado: Directorio del Trabajo

Puede estar en 2 estados:
Untracked: Si recien se creo
Modified: Si ya existia y se modificaste o eliminaste

Si quieres que lo modificado vuelva a su estado previo y borra lo que
se modifico. 
```
git restore <nombre archivo>
```
Y para que Git no vea ciertos archivos, solo se agrega al 
archivo .gitignore, escribiendo su nombre 

### 2do Estado: Stage (casi listo)
Es previo a confirmar el guardado de commit.
Para mover algo al stage se debe poner
```
git add <archivo>
git add . --> esto pone todos los archivos en etapa previa a stage
```
Para sacar de este estado y poner al estado previo, se usa
git restore --staged <fileName>

### 3er Estado: Confirmacion
Aqui se guarda los cambios con el nombre del commit, se usa
```
git commit -m <commitName>
```

### BUENAS PRACTICAS DE GIT

1.- Usa verbos como add, change, fix, remove
2.- No terminar commits con puntos ni puntos suspensivos
3.- Ser claro y usar max. 50 caracteres. Si es largo el nombre del commit,
seguramente es un cambio grande y se debe dividir en commits mas pequeños
4.- Usar prefijos para hacer al commit mas legible y claro
Segun corresponda prefijos como: feat, fix, perf, docs, ci, build, refactor,
style, test
Ejemplo: docs: Se usa al hacer cambios a la documentacion
Estructura ideal de un commit
```
git commit -m ¨<tipo de commit>: <descripcion>¨
```
5.- En caso se necesite una descripcion larga al commit, se usa otra estructura para
crear el commit
```
git commit
    prefijo: Titulo de commit
    descripcion del commit
```
6.- Escribir todas los commits en ingles, la mayoria lo hace y se recomienda


## Clase 3

### TU CUENTA EN GITHUB

### Como crear tu cuenta?

Ingresar a la pagina oficial de GitHub y crear una cuenta, no se recomienda con correo
instituacional y debes usar un username facil de recordar
### Crea tu 1er repositorio
Apretar la opcion crear nuevo repositorio y darle un nombre.
Una vez hecho, 
### Configura tu GitHub para conectar a tu repositorio local
Debes generar tu llave personal para trabajar con SSH, 
Ingresa:
```
ssh-keygen -t ed25519 -C ¨<correo usado en GitHub>¨
```
Copia la llave generada, ve a GIthub, en configuraciones y a Keys.
Crea una nueva llave, dale un nombre y pega la llave que generaste
antes en la 3ra seccion.
Finalmente click en ¨crear llave¨

Vuelve a la terminal e ingresa:
```
ssh -T git@github.com 
```
Despues ingresar yes, a la pregunta que aparezca. AL final, se te muestra un mensaje
que la autenticacion fue exitosa.

### Sube tu repositorio local

En GitHub, crea un nuevo repositorio y dale un nombre.
Luego de crearla ve a a terminal y ejecuta este comando para conectar de forma remota
y subir tu repositorio local al repositorio creado en GitHub:
```
git remote add origin git@github.com:TuUser/TuRepo.git
git branch -M main git push -u origin main
```
### Descarga un repositorio de GitHub 

En caso haya repositorios que quieras decargar en tu PC o estas en otra computadora
y quieres descargar uno de tus repositorios.

Abre tu terminal e ingresa este comando:
```
git clone “git@github.com:TuUser/TuRepo.git”
```
O mas facil ir al repositorio en GItHub y copiar el comando ya listo para SSH.

### Cambios a tu repositorio de GitHub 

Si quieres subir cambios nuevos que hiciste localmente, se usa:
```
git push origin <rama>
```
En caso quieres bajar los cambios que hiciste en el repositorio, se usa:
```
git pull origin <rama>
```

## CLASE 4 – RAMAS Y GITFLOW  

### ¿Qué son las ramas?
Al trabajar en equipo no conviene hacer todo directo en la rama main,ya que si algo sale mal se puede afectar todo el proyecto.

Por eso existen las ramas.

Las ramas son caminos alternos dentro del proyecto. Donde se puede trabajar en nuevas funciones o pruebas sin tocar directamente la rama main. Entonces, si algo falla, no se daña la versión principal del proyecto.

### Comando git branch
Uno de los comandos principales es git branch, que sirve para gestionar ramas.

### Ver ramas existentes
Con el comando:
```
git branch
```
se pueden ver todas las ramas que existen y también en cuál se está ahora.

### Crear una nueva rama
Con:
```
git branch <nombre-rama>
```
se crea una nueva rama.

### Eliminar una rama
Con:
```
git branch -D <nombre-rama>
```
se elimina una rama que ya no se necesita.


### git checkout enfocado en ramas
Aparte de revisar commits antiguos, también sirve para cambiar entre ramas.

### Cambiar de rama
Con:
```
git checkout <rama>
```
se cambia de una rama a otra.

### Crear rama y cambiar directamente
Con:
```
git checkout -b <rama>
```
se crea la rama y se cambia directamente a ella.

Antes de cambiar de rama no se deben tener archivos modified, staged o untracked 
porque puede causar conflictos.

### git checkout vs git switch
Antes todo se hacía con checkout, pero como servía para demasiadas cosas 
(ramas, commits y archivos), Git creó switch para hacerlo más claro.

### git checkout
Sirve para:
* cambiar ramas
* volver a commits antiguos
* restaurar archivos

Es más completo, pero también puede generar confusión.

### git switch
Sirve solamente para moverse entre ramas.
Es más claro, más moderno y ayuda a evitar errores con mayor facilidad.

### ¿Qué es Gitflow?
Es una forma de organizar el trabajo con ramas para que el proyecto tenga más orden,
 cuando varias personas trabajan en conjunto.

Sin Gitflow hay desorden porque todos crean ramas sin estructura clara.
Pero, ya con Gitflow existe una forma clara de trabajar.

### Ramas principales
### main
Es la rama principal y tiene el código estable, el que ya está listo para producción.
Aquí no se debe trabajar directamente.

### develop
Es la rama de pre-producción.
Aquí se desarrolla las nuevas funciones antes de pasar a main.
Es donde más se trabaja con los cambios.

### Ramas de apoyo
Hay ramas de apoyo donde se puede trabajar en tareas específicas.

Estas son:
* feature/*
* release/*
* hotfix/*

### Rama feature/*
Se usa cuando se trabaja en una nueva funcionalidad.

Ejemplos:
* feature/login
* feature/add-search-bar
* feature/new-form-user

Estas ramas nacen de develop y vuelven a develop.

### Rama release/*
Se usa cuando ya casi se va a lanzar una nueva versión.
Aquí se realizan pruebas finales y últimos ajustes.

Ejemplo:
* release/v1.0.0

Nacen de develop y vuelven a main y develop.

### Rama hotfix/*
Se usa cuando aparece un problema urgente en producción, como errores de login,
 fallos de pagoc, etc.

Ejemplos:
* hotfix/login-error
* hotfix/security-patch

Estas ramas nacen de main porque el problema está en producción y luego vuelven a
 main y también a develop.

### Aspectos extra a tomar en cuenta
No se recomienda trabajar directamente en main.
El flujo normal sería:
    main ----> develop ----> feature
y luego seria el regresar en reversa.

Esto ayuda a tener el proyecto limpio, más claro y seguro cuando varias personas
trabajan juntas.



## CLASE 4 – MERGE, FETCH, PULL y PUSH

###Git merge

Sirve para fusionar una rama con otra. En pocas palabras, une los cambios de una 
rama dentro de otra para que todo quede en un solo historial.

Cuando se usa `--no-ff`, Git no hace una fusión “rápida” y en su lugar deja un commit
 visible de la unión. Eso es útil porque permite ver claramente que esa rama existió
 y que fue fusionada.

La idea importante es esta: `--no-ff` ayuda a no perder el rastro del trabajo hecho en
 la rama.

### `Git fetch`
```
git fetch
```
Sirve para revisar si hubo cambios en el repositorio remoto. No mezcla nada todavía,
 solo informa y actualiza la referencia local de lo que existe en remoto.

Es como mirar primero qué cambió antes de traerlo al proyecto.

### `Git pull`
```
git pull
```
trae los cambios del repositorio remoto a la rama local.

La forma más clara de usarlo es:

```
git pull origin develop
```

Eso trae lo último que existe en `develop` desde el remoto.

### `Git push`
```
git push
```
sube los cambios locales al repositorio remoto.

La forma más común es:

```
git push origin rama
```

Si es la primera vez que se sube esa rama y el repositorio no es propio, se usa `-u` para
 dejarla vinculada al remoto:

```
git push -u origin rama
```

### Flujo de trabajo sin Pull Requests

El flujo que se explicó fue este:

1. Ir a `develop`
2. Hacer `git fetch`
3. Hacer `git pull origin develop`
4. Ir a la rama de trabajo
5. Fusionar `develop` en la rama si hace falta
6. Trabajar en la rama
7. Subir cambios con `git push origin rama`
8. Volver a `develop`
9. Hacer `git fetch`
10. Hacer `git pull origin develop`
11. Fusionar la rama con `git merge --no-ff rama`
12. Resolver conflictos si aparecen
13. Hacer `git add .`
14. Hacer `git commit`
15. Borrar la rama que ya no sirve con `git branch -D rama`
16. Subir `develop` con `git push origin develop`

### Caso 1: merge limpio

Si nadie tocó lo mismo y no hay conflictos, la fusión sale normal.

En ese caso:

* se hace `git merge --no-ff`
* Git crea el commit de la fusión
* se mantiene el historial visible
* luego se borra la rama ya terminada

### Caso 2: merge con conflictos

Si dos personas modificaron los mismos archivos o las mismas líneas, Git no sabe cuál
 cambio dejar.

Ahí aparece el conflicto.
En ese caso se debe abrir el archivo, revisar lo que Git marca con símbolos especiales
 y decidir manualmente qué se queda:

* solo lo de una rama
* solo lo de la otra
* o una mezcla de ambas

Después de corregirlo:

* se guarda el archivo
* se hace `git add .`
* se hace `git commit`
* se termina la fusión

La idea clave es que Git no “adivina” qué cambio es correcto; la persona debe decidirlo.

### Caso 3: trabajar sin desactualizarse

Este fue el consejo más útil de la clase.

Antes de hacer merge en `develop`, conviene traer los cambios nuevos de `develop` a la rama
 propia para no quedarse muy atrasado. Así se reducen conflictos grandes al final.

La lógica es esta:

* si la rama está muy vieja, se puede romper más al fusionar
* si se actualiza seguido, el merge final suele ser más fácil

Lo importante, es mejor no dejar la rama demasiado desactualizada.

Y como buena práctica, siempre que una rama ya terminó de usarse, se debe borrar para
 mantener orden en el proyecto.
