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

 
