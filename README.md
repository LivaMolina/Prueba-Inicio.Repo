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