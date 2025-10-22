# Prueba-Inicio.Repo
Creación de repositorio de prueba <br>
Estoy creando este repositorio para práctica

# Comienzo del Readme

Hemos comenzado con el repositorio, les voy a dejar los comandos que utilicé:

Vimos cómo he creado el repositorio en la nube de GitHub
Es importante saber que antes de todo esto se deben tener todos los pasos de ingreso y seguridad
Cuando hablo de seguridad y conectividad se trata de la ssh, es la clave pública y privada
Cómo se copia la ssh

* Abrimos la terminal de Git bash como administrador
* Ingresamos al área de trabajo donde queremos agregar el repo
* Voy ingresando a la carpeta Documentos y luego Repositorios
  
```sh
cd Documents/Repositorios
mkdir Proyectos
cd Proyectos
git clone git@github.com:LivaMolina/Prueba-Inicio.Repo.git
cd Prueba-Inicio-Repo
git pull origin main
git status
git branch -M main   # Vemos que la rama main por defecto
touch README.md      # Creamos el readme
git status
git add .
git commit -m "Creamos el readme.md"
git status
git push origin main
```

## Agregamos este trabajo en el readme online

< ¿Cómo hacemos esto?

Ingresamos al repositorio y luego solo presionamos punto <br>
```sh
  .
```
Ingresamos toda esta información y terminamos<br>
## CLASE 02 MIÉRCOLES 20 DE AGOSTO DEL 2025 -
Para cargar la llave SSH publica en GitHub, se puede copiar la llave publica, desde el archivo .ssh, allí encontrarás el archivo .pub lo podes abrir con el txt, luego copiar el contenido que esta dentro.<br>
> Desde Git Bash colocamos → ls -al ~/.ssh<br>

Este comando listará los archivos en el directorio .ssh. Si ves archivos como:<br>
•	id_rsa (clave privada)<br>
•	id_rsa.pub (clave pública)

... entonces ya tienes una clave SSH generada.<br>
Para ver el contenido de tu clave pública (que es la que se comparte, por ejemplo, con GitHub), usa:<br>

> cat ~/.ssh/id_rsa.pub

Desde allí puedes copiar la clave ssh
Si no tienes una clave generada, puedes crear una nueva con:<br>
>  ssh-keygen -t ed25519 -C "tu-email@ejemplo.com"
Es hoy la forma moderna, más segura y recomendada de crear tu clave SSH.

* ed25519 = tipo de cifrado para tu clave SSH
* Es más seguro, más rápido y más moderno que RSA
* Es el formato recomendado oficialmente por GitHub

🔹 -t → type (tipo de clave)

Significado:
-t viene de type. Le dice a ssh-keygen qué tipo de algoritmo usar para la clave.

Ejemplo:

-t ed25519 → usa el algoritmo Ed25519 (moderno y seguro)

-t rsa → usa el algoritmo RSA (más viejo, pero compatible)

-t ecdsa → usa ECDSA (otra variante de curvas elípticas)

👉 En tu caso,
-t ed25519 = “quiero que mi clave SSH sea del tipo Ed25519”.

🔹 -C → comment (comentario)

Significado:
-C agrega un comentario identificatorio a la clave pública.
No afecta la seguridad, solo sirve para reconocerla fácilmente.

Por ejemplo:

ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAA... tu-email@ejemplo.com


La parte final (tu-email@ejemplo.com) se genera por el -C
→ así sabés después de quién es esa clave (útil si tenés varias, en distintas máquinas).<br>
<br>
Copiar la llave publica #Ir a GitHub, vamos a setting, vamos a SSH and GPG keys
crear una nueva #New SSH key poner nombre y pegar la ssh publica, con esto esta listo.<br>

```sh
git branch #Vemos en que rama estamos
git checkout master #Ponernos en la rama master
git branch -M main #Cambiamos el nombre a la rama master
git remote add origin git@github.com:nombreUsuario/class-git.git #Agregamos el repositorio remoto, este es un ejemplo
git remote -v #Vemos si ya esta conectado
git merge segunda #Mergeamos lo que tenemos en la rama segunda en main
git commit -am "Uso de GitHub parte 2" #Hacemos el commit de hoy
git push origin main #Pasamos todo lo hecho a GitHub, revisar en el repositorio en GitHub.
```

Frente al cambio de nombre de rama master a main, suele suceder que en el repo de GitHub se hayan creado dos ramas, la rama master y la rama main, se debe ir al repo, settings y ahí se puede cambiar la rama principal, en vez de que siga siendo master, que sea la rama main, luego de eso ya podemos borrar la rama master.

## CLASE 03 MIÉRCOLES 27 DE AGOSTO DEL 2025 -
Cambios en GitHub: de master a main<br>
¿Cuando es que sigue siendo master y cuando sigue siendo main?<br>
Cuando se crea un repositorio desde git bash en nuestro ordenador a través de git init, sigue siendo el estandar como master. <br>¿Qué hacer con esto? Debes cambiar el nombre de la rama master a main con el comando:<br>
```sh
git branch -M main
# O cambiando la asignación por default con este otro comando:
git config --global init.defaultBranch main
```
A partir de este comando siempre que ingreses git init será la rama main.<br>
Ahora cuando creamos un repositorio desde la nube, osea desde GitHub, ya verás que la rama principal tiene por default el nombre de main y al clonar a nuestro ordenador seguira teniendo este nombre y no será necesario ningun cambio.<br>

```sh
# Otro comando que deben saber es:
gitk
```
Si no te funciona el comando gitk es posible no lo tengas instalado por defecto.<br>

```sh
# Para instalar gitk debemos ejecutar los siguientes comandos:
sudo apt-get update
sudo apt-get install gitk
```

Recuerda que podemos ver gráficamente nuestro entorno y flujo de trabajo local con Git utilizando el comando gitk.<br>
 Gitk fue el primer visor gráfico que se desarrolló para ver de manera gráfica el historial de un repositorio de Git.
<br>

## CLASE 04 MIÉRCOLES 3 DE SEPTIEMBRE DEL 2025 -
### Tu primer push
La creación de las SSH es necesario solo una vez por cada computadora. <br>
 Aquí conocerás cómo conectar a GitHub usando SSH.<br>
Luego de crear nuestras llaves SSH podemos entregarle la llave pública a GitHub para comunicarnos de forma segura y sin necesidad de escribir nuestro usuario y contraseña todo el tiempo.<br>

Para esto debes entrar a la Configuración de Llaves SSH en GitHub, crear una nueva llave con el nombre que le quieras dar y el contenido de la llave pública de tu computadora.<br>

Ahora podemos actualizar la URL que guardamos en nuestro repositorio remoto, solo que, en vez de guardar la URL con HTTPS, vamos a usar la URL con SSH:<br>

ssh

> it remote set-url origin url-ssh-del-repositorio-en-github

Comandos para copiar la llave SSH:<br>

### ESTAS SON LAS RUTAS DEL SSH PUBLICO
```sh
# -Mac:
pbcopy < ~/.ssh/id_rsa.pub
# Windows (Git Bash):
clip < ~/.ssh/id_rsa.pub
# Linux (Ubuntu):
cat ~/.ssh/id_rsa.pub
```
* Importante
Las buenas costumbres nos enseñan que antes de hacer un push, siempre debemos hacer un pull, un fetch, esto para que si alguien ya hizo algún cambio, no se genere un conflicto.<br>
* Invitar a un colaborador<br>
Para invitar a un colaborador debemos ir a GitHub y seleccionar:<br>

> setting -> colaborators -> ingresar contraseña o un F2A de verificación y enviar la invitación escribiendo el nombre de usuario.

Del otro lado el usuario invitado solo debe aceptar y listo, ya puede participar del proyecto haciendo commit.<br>

## CLASE 05 MIÉRCOLES 10 DE SEPTIEMBRE DEL 2025
### Git tag y versiones en GitHub

En Git, las etiquetas o Git tags tienen un papel importante al asignar versiones a los commits más significativos de un proyecto. Aprender a utilizar el comando git tag, entender los diferentes tipos de etiquetas, cómo crearlas, eliminarlas y compartirlas, es esencial para un flujo de trabajo eficiente.

### Creación de etiquetas en Git

```sh
git tag

```
Sustituye con un identificador semántico que refleje el estado del repositorio en el momento de la creación. Git admite etiquetas anotadas y ligeras.<br>

### Listado de etiquetas
Para obtener una lista de etiquetas en el repositorio, ejecuta el siguiente comando:
```sh
git tag # Muestra las etiquetas
git show-ref --tags # Muestra etiquetas con más detalle Te muestra el hash del commit y el nombre de cada etiqueta.

```
### Para crear una etiqueta, ejecuta el siguiente comando:
```sh
git tag nombre_del_tag
git tag v1.0 # Ejemplo
* Crear una etiqueta anotada (recomendada)
git tag -a nombre_del_tag -m "mensaje descriptivo"
git tag -a v1.0 -m "Versión inicial del proyecto" # Ejemplo
# Esto queda registrado en el historial con detalles y se puede consultar más tarde con git show v1.0.
```
Las etiquetas anotadas almacenan información adicional como la fecha, etiquetador y correo electrónico, y son ideales para publicaciones públicas. <br>
Las etiquetas ligeras son más simples y se emplean como “marcadores” de una confirmación específica.<br>
### Etiquetar un commit anterior: Si querés marcar un commit viejo (no el último), podés hacerlo usando su hash:
```sh
git tag -a v0.9 1a2b3c4d -m "Versión anterior" # Reemplazá 1a2b3c4d por los primeros dígitos del hash del commit, que ves con git log

git show-ref --tags # Muestra etiquetas con más detalle Te muestra el hash del commit y el nombre de cada etiqueta.

```
### Subir la etiqueta a GitHub
Por defecto, las etiquetas no se suben con git push, tenés que hacerlo explícitamente:<br>
```sh
git push origin v1.0 # Subir una etiqueta específica:

git push origin --tags # Subir todas las etiquetas:


git tag

* Esto mostrará una lista de las etiquetas existentes, como:

v1.0

v1.1

v1.2
```
Para perfeccionar la lista, puedes utilizar opciones adicionales, como -l con una expresión comodín.<br>
* Qué es una expresión comodín: una expresión comodín (wildcard) usa el símbolo * para representar “cualquier conjunto de caracteres”.<br>

Por ejemplo:<br>
v1.* → todas las etiquetas que empiecen con v1.

*beta* → todas las etiquetas que contengan la palabra “beta”.

release-* → todas las etiquetas que empiecen con “release-”.
```sh
Ejemplo 
git tag -l "v1.*" # Mostrar todas las etiquetas que comienzan con “v1.”
git tag -l "*beta*" # Mostrar solo las que contienen la palabra “beta”
git tag -lv # Mostrar todas las etiquetas (equivalente a git tag)
```

### Uso compartido de etiquetas

Compartir etiquetas requiere un enfoque explícito al usar el comando git push. Por defecto, las etiquetas no se envían automáticamente. Para enviar etiquetas específicas, utiliza:<br>

git push origin<br>

Para enviar varias etiquetas a la vez, usa: <br>

git push origin --tags<br>


### Eliminación de etiquetas
Para eliminar una etiqueta, usa el siguiente comando:<br>
```sh
> Localmente
git tag -d
git tag -d v1.0 #Ejemplo 
# Esto eliminará la etiqueta identificada por en el repositorio local.
> Una vez subida a Git Hub
git push origin --delete v1.0 # Ejemplo con etiqueta v1.0
```
> En resumen, las etiquetas en Git son esenciales para asignar versiones y capturar instantáneas importantes en el historial de un proyecto. Aprender a crear, listar, compartir y eliminar etiquetas mejorará tu flujo de trabajo con Git.

## CLASE 06-A MIÉRCOLES 24 DE SEPTIEMBRE DEL 2025
### Error con los tags

#### Investigación:
¿Qué pasa si por error cargamos un tag dos veces?
¿Cómo solucionarías este problema o error?

## Error de duplicado de tags en Git

¿Un tag se puede generar dos veces?<br>

No. En el repositorio local, Git no te deja crear dos veces el mismo nombre de *tag*. Si
intentás, te da error:<br>

• fatal: tag 'v1.0' already exists<br>

¿Por qué aparece el error de “dos tags con el mismo nombre”?<br>

El problema no está en la PC, sino cuando hay dos definiciones diferentes del mismo
tag en contextos distintos:<br>
Local vs. remoto:<br>

• En tu PC tenés `v1.0` apuntando a un commit.<br>
• En el remoto (GitHub, GitLab) alguien creó también `v1.0` pero apuntando a otro
commit.<br>
• Cuando hacés `git push --tags`, Git detecta el choque y dice: “hay dos tags
distintos con el mismo nombre”.<br>

Entre distintas personas del equipo:<br>
• Cada uno pudo haber creado un tag con el mismo nombre pero sobre commits
diferentes.<br>
• Al subirlos al mismo remoto, se genera la colisión.<br>

Tipos distintos de tag:<br>
• Uno pudo ser ligero y otro anotado, ambos con el mismo nombre.<br>
• Aunque se llamen igual, Git los trata como objetos diferentes.<br>

Ejemplo paso a paso en consola<br>
En PC 1:
# Hacés un commit
git commit -m "Mi versión estable"
# Creás el tag v1.0
git tag v1.0
# Subís el tag al remoto
git push origin v1.0
Ahora en GitHub existe `v1.0` apuntando a tu commit.
En la PC 2:
# Hace otro commit distinto
git commit -m "Otra versión estable"
# También crea un tag con el mismo nombre
git tag v1.0
# Intenta subirlo
git push origin v1.0
Git responde:
! [rejected] v1.0 -> v1.0 (already exists)
error: failed to push some refs to 'github.com:repo.git'

¿Qué pasó?<br>
• En local de PC 2 : `v1.0` apunta a su commit.
• En remoto: `v1.0` ya existe, apuntando al PC 1.
• Git detecta que son dos tags diferentes con el mismo nombre → conflicto.

### Solución<br>
PC 2 debe borrar el tag local y recrearlo, o bien coordinar con vos qué commit debe
llevar el nombre `v1.0`.
### Ejemplo para borrar y recrear:
```sh
git tag -d v1.0 # Borrar tag local
git fetch origin --tags # Traer el correcto del remoto
# Si el tag remoto estaba mal y hay que corregirlo:
git tag -d v1.0
git tag v1.0 <commit_correcto>
git push origin :refs/tags/v1.0 # Borrar en remoto
git push origin v1.0 # Subir tag correcto
```
