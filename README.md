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
