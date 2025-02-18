# Práctica Manejo Básico de GIT

## Índice

- [Práctica Manejo Básico de GIT](#práctica-manejo-básico-de-git)
  - [Índice](#índice)
  - [PREREQUISITOS:](#prerequisitos)
  - [PRÁCTICA:](#práctica)
    - [PARTE 1: Crear el repositorio de trabajo](#parte-1-crear-el-repositorio-de-trabajo)
      - [Pasos a seguir:](#pasos-a-seguir)
    - [PARTE 2: Historial de cambios](#parte-2-historial-de-cambios)
    - [PARTE 3: Deshacer cambios](#parte-3-deshacer-cambios)
    - [PARTE 4: RAMAS](#parte-4-ramas)

## PREREQUISITOS:
• Confirmar que tienes GIT instalado en la máquina (git –version te puede ser útil)
• Confirma que tienes una cuenta GITHUB, sino créate una https://github.com/

## PRÁCTICA:
Vamos a seguir una serie de pasos para crear un repositorio

### PARTE 1: Crear el repositorio de trabajo
Esta parte se podría realizar de dos maneras distintas. Una de ellas sería crear el repositorio en GITHUB y luego clonarlo (git clone URL) o, como haremos en clase, trabajar desde un inicio en la máquina local para subirlo a un repositorio remoto.

1. Creamos en local una carpeta cuyo nombre sea PRACTICA_GIT.
2. Inicializamos el repositorio (“git init”).
3. Incluiremos un fichero README cuyo texto sea “This is a README file”.
4. Añadimos el repositorio dicho fichero, lo “commiteamos” con el mensaje “Initial Commit” y revisamos que todo está correcto mediante “git status”.

En este punto ya tenemos todo listo en local, pero debemos poder subirlo al repositorio remoto (nada de esto tiene sentido si nuestro trabajo queda siempre en local).

Iremos entonces a nuestra cuenta en GITHUB y crearemos el repositorio con el nombre PRACTICA_GIT.

Entre otras cosas, esto nos permite obtener una URL que podremos “linkar” con nuestro repositorio local. Por ejemplo, durante el desarrollo de este ejemplo

NOTA: En el momento de crear el repositorio, nos indica si queremos añadir un fichero gitignore. Digamos que sí a la versión JAVA.

Crearemos una rama principal y subiremos el repositorio a remoto.

```bash
1. git branch -M main
2. git remote add origin https://github.com/nmonzonlo/practica_1.git
3. git push -u origin main
```

Es probable que tengan algún problema utilizando el repositorio en clases, en este enlace obtendrán la manera de arreglarlo: https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token

#### Pasos a seguir:

1. Comprobar el estado del repositorio.
2. Crear un fichero `indice.txt` con el siguiente contenido:
   ```
   Capítulo 1: Introducción a Git
   Capítulo 2: Flujo de trabajo básico
   Capítulo 3: Repositorios remotos
   ```
3. Comprobar de nuevo el estado del repositorio.

```bash
PRACTICA_GIT % git status
En la rama main
Tu rama está actualizada con 'origin/main'.

Archivos sin seguimiento:
  (usa "git add <archivo>..." para incluirlo a lo que será confirmado)
        indice.txt

no hay nada agregado al commit pero hay archivos sin seguimiento presentes (usa "git add" para hacerles seguimiento)
```

4. Añadir el fichero a la zona de intercambio temporal.

```bash
git add indice.txt
```

5. Volver a comprobar una vez más el estado del repositorio.

```bash
PRACTICA_GIT % git status        
En la rama main
Tu rama está actualizada con 'origin/main'.

Cambios a ser confirmados:
  (usa "git restore --staged <archivo>..." para sacar del área de stage)
        nuevos archivos: indice.txt
```

6. Realizar un commit de los últimos cambios con el mensaje "Añadido índice del libro." y ver el estado del repositorio.

```bash
git commit -m "Añadido índice del libro."
```

```bash
PRACTICA_GIT % git status
En la rama main
Tu rama está adelantada a 'origin/main' por 1 commit.
  (usa "git push" para publicar tus commits locales)
```

7. Cambiar el fichero `indice.txt` para que contenga lo siguiente:
   ```
   Capítulo 1: Introducción a Git
   Capítulo 2: Flujo de trabajo básico
   Capítulo 3: Gestión de ramas
   Capítulo 4: Repositorios remotos
   ```
8. Mostrar los cambios con respecto a la última versión guardada en el repositorio.

```bash
git diff
```

```bash
PRACTICA_GIT % git diff
diff --git a/indice.txt b/indice.txt
index 8e62a31..ba17d35 100644
--- a/indice.txt
+++ b/indice.txt
@@ -1,3 +1,4 @@
 Capítulo 1: Introducción a Git
 Capítulo 2: Flujo de trabajo básico
-Capítulo 3: Repositorios remotos
+Capítulo 3: Gestión de ramas
+Capítulo 4: Repositorios remotos
:...skipping...
diff --git a/indice.txt b/indice.txt
index 8e62a31..ba17d35 100644
--- a/indice.txt
+++ b/indice.txt
@@ -1,3 +1,4 @@
 Capítulo 1: Introducción a Git
 Capítulo 2: Flujo de trabajo básico
-Capítulo 3: Repositorios remotos
+Capítulo 3: Gestión de ramas
+Capítulo 4: Repositorios remotos
~
```

9.  Añadir el fichero a la zona de intercambio temporal.

```bash
git add indice.txt
```

10. Hacer un commit de los cambios con el mensaje "Añadido capítulo 3 sobre gestión de ramas."

```bash
git commit -m "Añadido capítulo 3 sobre gestión de ramas."
```

11. Mostrar los cambios de la última versión del repositorio con respecto a la anterior.

```bash
git diff
```

12. Cambiar el mensaje del último commit por "Añadido capítulo 3 sobre gestión de ramas al índice."

```bash
git commit --amend -m "Añadido capítulo 3 sobre gestión de ramas al índice."
```

13. Volver a mostrar los últimos cambios del repositorio.

```bash
git diff
```

### PARTE 2: Historial de cambios

1. Mostrar el historial de cambios del repositorio.

```bash
git log
```

```bash
PRACTICA_GIT % git log
commit 902a2d0f41ef9c6f902fe7819c45e91aea3ed9db (HEAD -> main)
Author: Francisco J <fran@users.noreply.github.com>
Date:   Tue Feb 18 17:38:31 2025 +0000

    Añadido capítulo 3 sobre gestión de ramas al índice.

commit f89ae2d2ed6f2edcfb380d342b7f0423eef542e2
Author: Francisco J <fran@users.noreply.github.com>
Date:   Tue Feb 18 17:35:29 2025 +0000

    Añadido índice del libro.

commit b3c6e10c4e02897136b6bbc47c724839ea602417 (origin/main)
Author: Francisco J <fran@users.noreply.github.com>
Date:   Tue Feb 18 17:31:00 2025 +0000

    Add .gitignore file to ignore compiled files, logs, and package files
```

2. Crear la carpeta capítulos y crear dentro de ella el fichero capitulo1.txt con el siguiente texto:

```bash
Git es un sistema de control de versiones ideado por Linus Torvalds.
```

3. Añadir los cambios a la zona de intercambio temporal.

```bash
git add capitulos/capitulo1.txt
```

4. Hacer un commit de los cambios con el mensaje "Añadido capítulo 1." 

```bash
git commit -m "Añadido capítulo 1."
```

5. Volver a mostrar el historial de cambios del repositorio.

```bash
git log
```

6. Crear el fichero capitulo2.txt en la carpeta capítulos con el siguiente texto.

```bash
El flujo de trabajo básico con Git consiste en: 

1- Hacer cambios en el repositorio. 
2- Añadir los cambios a la zona de intercambio temporal. 
3- Hacer un commit de los cambios.
```

7. Añadir los cambios a la zona de intercambio temporal.

```bash
git add capitulos/capitulo2.txt
```

8. Hacer un commit de los cambios con el mensaje "Añadido capítulo 2."

```bash
git commit -m "Añadido capítulo 2."
```

9. Mostrar las diferencias entre la última versión y dos versiones anteriores.

```bash
git diff HEAD~2
```

```bash
PRACTICA_GIT % git diff HEAD~2        
diff --git a/capitulos/capitulo1.txt b/capitulos/capitulo1.txt
new file mode 100644
index 0000000..7431f9e
--- /dev/null
+++ b/capitulos/capitulo1.txt
@@ -0,0 +1 @@
+Git es un sistema de control de versiones ideado por Linus Torvalds.
diff --git a/capitulos/capitulo2.txt b/capitulos/capitulo2.txt
new file mode 100644
index 0000000..d2b1063
--- /dev/null
+++ b/capitulos/capitulo2.txt
@@ -0,0 +1,5 @@
+El flujo de trabajo básico con Git consiste en: 
+
+1- Hacer cambios en el repositorio. 
+2- Añadir los cambios a la zona de intercambio temporal. 
+3- Hacer un commit de los cambios.
```

10.  Crear el fichero capitulo3.txt en la carpeta capítulos con el siguiente texto.

```bash
Git permite la creación de ramas lo que permite tener distintas versiones del mismo proyecto y trabajar de manera simultánea en ellas.
```

11.  Añadir los cambios a la zona de intercambio temporal.

```bash
git add capitulos/capitulo3.txt
```

12.  Hacer un commit de los cambios con el mensaje "Añadido capítulo 3."

```bash
git commit -m "Añadido capítulo 3."
```

13.  Mostrar las diferencias entre la primera y la última versión del repositorio.

```bash
git diff HEAD~2
```

14.  Añadir al final del fichero indice.txt la siguiente línea:

```bash
Capítulo 5: Conceptos avanzados
```

15.  Añadir los cambios a la zona de intercambio temporal.

```bash
git add indice.txt
```

16.  Hacer un commit de los cambios con el mensaje "Añadido capítulo 5 al índice."

```bash
git commit -m "Añadido capítulo 5 al índice."
```

### PARTE 3: Deshacer cambios

1. Eliminar la última línea del fichero indice.txt y guardarlo.

2. Comprobar el estado del repositorio.

```bash
git status
```

3. Deshacer los cambios realizados en el fichero indice.txt para volver a la versión anterior del fichero.

```bash
git checkout -- indice.txt
```

4. Volver a comprobar el estado del repositorio.

```bash
git status
```

5. Eliminar la última línea del fichero indice.txt y guardarlo.

6. Añadir los cambios a la zona de intercambio temporal.

```bash
git add indice.txt
```

7. Comprobar de nuevo el estado del repositorio.

```bash
git status
```

8. Quitar los cambios de la zona de intercambio temporal, pero mantenerlos en el directorio de trabajo.

```bash
git reset HEAD indice.txt
```

9. Comprobar de nuevo el estado del repositorio.

```bash
git status
```

10. Deshacer los cambios realizados en el fichero indice.txt para volver a la versión anterior del fichero.

```bash
git checkout -- indice.txt
```

11. Volver a comprobar el estado del repositorio.

```bash
git status
```

12. Eliminar la última línea del fichero indice.txt y guardarlo.

13. Eliminar el fichero capitulos/capitulo3.txt.

```bash
git rm capitulos/capitulo3.txt
```

14. Añadir un fichero nuevo captitulos/capitulo4.txt vacío.

15. Añadir los cambios a la zona de intercambio temporal.

```bash
git add indice.txt
git add capitulos/capitulo4.txt
```

16.  Comprobar de nuevo el estado del repositorio.

```bash
PRACTICA_GIT % git status
En la rama main
Tu rama está adelantada a 'origin/main' por 6 commits.
  (usa "git push" para publicar tus commits locales)

Cambios a ser confirmados:
  (usa "git restore --staged <archivo>..." para sacar del área de stage)
        borrados:        capitulos/capitulo3.txt
        nuevos archivos: capitulos/capitulo4.txt
        modificados:     indice.txt
```

17. Quitar los cambios de la zona de intercambio temporal, pero mantenerlos en el directorio de trabajo.

```bash
git reset HEAD 
```

18. Comprobar de nuevo el estado del repositorio.

```bash
PRACTICA_GIT % git status
En la rama main
Tu rama está adelantada a 'origin/main' por 6 commits.
  (usa "git push" para publicar tus commits locales)

Cambios no rastreados para el commit:
  (usa "git add/rm <archivo>..." para actualizar a lo que se le va a hacer commit)
  (usa "git restore <archivo>..." para descartar los cambios en el directorio de trabajo)
        borrados:        capitulos/capitulo3.txt
        modificados:     indice.txt

Archivos sin seguimiento:
  (usa "git add <archivo>..." para incluirlo a lo que será confirmado)
        capitulos/capitulo4.txt
```

19. Deshacer los cambios realizados para volver a la versión del repositorio.

20. Volver a comprobar el estado del repositorio. 

```bash
git status
```

21.  Eliminar la última línea del fichero indice.txt y guardarlo.

22.  Eliminar el fichero capitulos/capitulo3.txt.

```bash
git rm capitulos/capitulo3.txt
```

23. Añadir los cambios a la zona de intercambio temporal y hacer un commit con el
mensaje "Borrado accidental."

```bash
git commit -m "Borrado accidental."
```

23.  Comprobar el historial del repositorio.

```bash
git log
```

24.  Deshacer el último commit, pero mantener los cambios anteriores en el directorio de trabajo y la zona de intercambio temporal.

```bash
git reset HEAD~1
```

25.  Comprobar el historial y el estado del repositorio.

```bash
git status
```

26.  Volver a hacer el commit con el mismo mensaje de antes.

```bash
git commit -m "Borrado accidental."
```

27.  Deshacer el último commit y los cambios anteriores del directorio de trabajo volviendo a la versión anterior del repositorio.

```bash
git reset HEAD~1
```

28.  Comprobar de nuevo el historial y el estado del repositorio.

```bash
git status
```

### PARTE 4: RAMAS

1. Crear una nueva rama bibliografía y mostrar las ramas del repositorio.

```bash
git branch bibliografia
```

```bash
PRACTICA_GIT % git branch
  bibliografia
  main
```

2. Crear el fichero capitulos/capitulo1.txt y añadir el texto siguiente

```bash
echo "En este capítulo veremos cómo usar GitHub para alojar repositorios en remoto." > capitulos/capitulo1.txt
```

3. Añadir los cambios a la zona de intercambio temporal.

```bash
git add capitulos/capitulo1.txt
```

4. Hacer un commit con el mensaje "Añadido capítulo 1."

```bash
git commit -m "Añadido capítulo 1."
```

5. Mostrar la historia del repositorio incluyendo todas las ramas.

```bash
git log --all
```

6. Cambiar a la rama bibliografía.

```bash
git checkout bibliografia
```

7. Crear el fichero bibliografia.txt y añadir la siguiente referencia
"Chacon, S. and Straub, B. Pro Git. Apress."

```bash
echo "Chacon, S. and Straub, B. Pro Git. Apress." > bibliografia.txt
```

8. Añadir los cambios a la zona de intercambio temporal (staging area).

```bash
git add bibliografia.txt
```

9. Hacer un commit con el mensaje "Añadida primera referencia bibliográfica."

```bash
git commit -m "Añadida primera referencia bibliográfica."
```

10.  Mostrar la historia del repositorio incluyendo todas las ramas.

```bash
PRACTICA_GIT % git commit -m "Añadida primera referencia bibliográfica."
[bibliografia 9787aa2] Añadida primera referencia bibliográfica.
 1 file changed, 1 insertion(+)
 create mode 100644 bibliografia.txt
PRACTICA_GIT % git log --all
commit 9787aa2c039556899a64276dfafcaf04cc9be4a1 (HEAD -> bibliografia)
Author: Francisco J <fran@users.noreply.github.com>
Date:   Tue Feb 18 18:07:19 2025 +0000

    Añadida primera referencia bibliográfica.

commit 5a414bf9993143c8f5e0f921c2aa938d104a5b13 (main)
Author: Francisco J <fran@users.noreply.github.com>
Date:   Tue Feb 18 18:06:06 2025 +0000

    Añadido capítulo 1.

commit 07258fce0157e0638aa2c9dd57cc767a6bdeeb46 (origin/main)
Author: Francisco J <fran@users.noreply.github.com>
Date:   Tue Feb 18 18:02:50 2025 +0000

    Revert "Borrado accidental."
```

11.  Fusionar la rama bibliografía con la rama master.
   
```bash
git checkout main
git merge bibliografia
```

12. Mostrar la historia del repositorio incluyendo todas las ramas.

```bash
git log --all
```

13. Eliminar la rama bibliografía.

```bash
git branch -d bibliografia
```

14. Mostrar de nuevo la historia del repositorio incluyendo todas las ramas.

```bash
git log --all
```

15. Cambiar el fichero bibliografia.txt para que contenga las siguientes referencias:

```bash
Scott Chacon and Ben Straub. Pro Git. Apress.
Ryan Hodson. Ry's Git Tutorial. Smashwords (2014)
```

16.  Añadir los cambios a la zona de intercambio temporal y hacer un commit con el mensaje "Añadida nueva referencia bibliográfica."

```bash
git add bibliografia.txt
git commit -m "Añadida nueva referencia bibliográfica."
```

17.  Cambiar a la rama master.

```bash
git checkout main
```

18.  Cambiar el fichero bibliografia.txt para que contenga las siguientes referencias:

```bash
Chacon, S. and Straub, B. Pro Git. Apress.
Loeliger, J. and McCullough, M. Version control with Git. O'Reilly.
```

19.  Añadir los cambios a la zona de intercambio temporal y hacer un commit con el
mensaje "Añadida nueva referencia bibliográfica."

```bash
git add bibliografia.txt
git commit -m "Añadida nueva referencia bibliográfica."
```

20.  Fusionar la rama bibliografía con la rama master.

```bash
git merge bibliografia
```

21. Resolver el conflicto dejando el fichero bibliografia.txt con las referencias:

Antes: 

```
<<<<<<< HEAD
Chacon, S. and Straub, B. Pro Git. Apress.
Loeliger, J. and McCullough, M. Version control with Git. O'Reilly.
=======
Scott Chacon and Ben Straub. Pro Git. Apress.
>>>>>>> bibliografia
```

Después:

```bash
Chacon, S. and Straub, B. Pro Git. Apress.
Loeliger, J. and McCullough, M. Version control with Git. O'Reilly.
Hodson, R. Ry's Git Tutorial. Smashwords (2014)
```

```bash
git add bibliografia.txt
git commit -m "Resuelto conflicto de bibliografía."
```

22. Mostrar la historia del repositorio incluyendo todas las ramas. 

```bash
git log --all
```
