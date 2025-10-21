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
Ingresamos toda esta información y terminamos