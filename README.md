# Práctica Manejo Básico de GIT

## Prerrequisitos
- Confirmar que tienes GIT instalado en la máquina (`git --version`)
- Confirma que tienes una cuenta GITHUB, sino créate una: https://github.com/

## Descripción de la Práctica
Esta práctica está diseñada para familiarizarse con los comandos básicos de Git y el flujo de trabajo habitual al desarrollar software. Se divide en cuatro partes principales que cubren desde la creación de un repositorio hasta el manejo avanzado de ramas.

## Partes de la Práctica

### PARTE 1: Crear el Repositorio de Trabajo

Esta parte se puede realizar de dos maneras distintas:
- Crear el repositorio en GITHUB y luego clonarlo (`git clone URL`)
- Trabajar desde un inicio en la máquina local para luego subirlo a un repositorio remoto (método usado en esta práctica)

#### Pasos a seguir:
1. Crear una carpeta local llamada `PRACTICA_GIT`
2. Inicializar el repositorio con `git init`
3. Crear un fichero README con el texto "This is a README file"
4. Añadir el fichero al repositorio con `git add README.md`
5. Hacer commit con el mensaje "Initial Commit" usando `git commit -m "Initial Commit"`
6. Verificar el estado del repositorio con `git status`

Después, creamos un repositorio remoto en GitHub con el nombre `PRACTICA_GIT` y lo vinculamos con nuestro repositorio local:

```bash
git branch -M main
git remote add origin https://github.com/usuario/PRACTICA_GIT.git
git push -u origin main
```

A continuación, realizamos los siguientes pasos:

1. Comprobar el estado del repositorio con `git status`
2. Crear un fichero `indice.txt` con contenido inicial
3. Añadir el fichero a la zona de intercambio temporal con `git add indice.txt`
4. Realizar un commit con `git commit -m "Añadido índice del libro."`
5. Modificar el fichero `indice.txt`
6. Mostrar cambios con `git diff`
7. Añadir cambios y hacer commit con mensaje adecuado
8. Modificar el mensaje del último commit con `git commit --amend -m "Nuevo mensaje"`

### PARTE 2: Historial de Cambios

En esta parte trabajamos con:
1. Mostrar el historial de cambios con `git log`
2. Crear una estructura de carpetas y archivos
3. Realizar varios commits
4. Comparar versiones con `git diff HEAD~2 HEAD`
5. Analizar quién ha realizado cambios con `git blame`

### PARTE 3: Deshacer Cambios

Esta sección explora diversas formas de deshacer cambios:
1. Descartar cambios locales con `git checkout -- <file>`
2. Retirar archivos del área de preparación con `git reset HEAD <file>`
3. Revertir commits con `git reset --soft HEAD~1` y `git reset --hard HEAD~1`
4. Manejar errores y recuperar el estado anterior del repositorio

### PARTE 4: Ramas

Finalmente, trabajamos con ramas:
1. Crear nuevas ramas con `git branch <nombre-rama>`
2. Cambiar entre ramas con `git checkout <nombre-rama>`
3. Fusionar ramas con `git merge <nombre-rama>`
4. Resolver conflictos de fusión
5. Eliminar ramas con `git branch -d <nombre-rama>`

## Referencia de Comandos Git

A continuación se presenta un resumen de los comandos Git utilizados en esta práctica:

### Configuración inicial
- `git --version`: Verificar la versión de Git instalada
- `git init`: Inicializar un repositorio local
- `git config --global user.name "Nombre"`: Configurar nombre de usuario
- `git config --global user.email "email@example.com"`: Configurar email

### Gestión básica
- `git status`: Comprobar el estado del repositorio
- `git add <archivo>`: Añadir archivos a la zona de intercambio temporal
- `git commit -m "mensaje"`: Realizar un commit con un mensaje descriptivo
- `git commit --amend -m "nuevo mensaje"`: Modificar el mensaje del último commit

### Trabajo con repositorios remotos
- `git branch -M main`: Renombrar la rama principal a "main"
- `git remote add origin <URL>`: Vincular repositorio local con remoto
- `git push -u origin main`: Subir contenido local a repositorio remoto
- `git clone <URL>`: Clonar un repositorio remoto

### Análisis y comparación
- `git log`: Mostrar historial de commits
- `git log --oneline`: Mostrar historial de forma resumida
- `git log --graph --all --oneline`: Mostrar historial gráfico incluyendo todas las ramas
- `git diff`: Mostrar cambios entre directorio de trabajo y área de preparación
- `git diff HEAD~n HEAD`: Comparar versión actual con n commits anteriores
- `git blame <archivo>`: Mostrar quién modificó cada línea de un archivo

### Deshacer cambios
- `git checkout -- <archivo>`: Descartar cambios en archivos modificados
- `git reset HEAD <archivo>`: Quitar archivos del área de preparación
- `git reset --soft HEAD~1`: Deshacer último commit manteniendo cambios en área de preparación
- `git reset --hard HEAD~1`: Deshacer último commit y todos los cambios asociados

### Trabajo con ramas
- `git branch`: Listar ramas existentes
- `git branch <nombre-rama>`: Crear una nueva rama
- `git checkout <nombre-rama>`: Cambiar a otra rama
- `git merge <nombre-rama>`: Fusionar rama especificada con la rama actual
- `git branch -d <nombre-rama>`: Eliminar una rama

## Conclusión

Esta práctica permite familiarizarse con los comandos esenciales de Git, desde la creación y gestión básica de repositorios hasta operaciones más avanzadas como la gestión de ramas y resolución de conflictos. Dominar estos comandos es fundamental para cualquier desarrollador que trabaje en proyectos colaborativos.
