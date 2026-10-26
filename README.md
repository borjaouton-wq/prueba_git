# Práctica de Sistemas de Control de Versiones (Git)
## Paso 1:
Se creó el directorio `prueba_git` y se usó el editor `nano` para redactar `texto.txt` y `script.sh`
Comandos ejecutados:
```bash
mkdir prueba_git
cd prueba_git
nano texto.txt
Contenido de texto.txt :
uno
dos
tres
nano script.sh
Contenido de script.sh :
echo Listado completo
ls -l
```
## Paso 2:
Se inicializó el repositorio local mediante `git init` y se comprobó el estado de los archivos con `git status`

```bash
$ git init
Initialized empty Git repository in C:/Users/Borja/prueba_git/.git/

$ git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        script.sh
        texto.txt

nothing added to commit but untracked files present (use "git add" to track)

```

## Paso 3:
Cambiamos el `master` a `main` y lo volvemos a dejar como estaba 

```bash
Borja@DESKTOP-G0V6A3S MINGW64 ~/prueba_git (master)
$ git branch -m main

Borja@DESKTOP-G0V6A3S MINGW64 ~/prueba_git (main)
$ git branch -m master

Borja@DESKTOP-G0V6A3S MINGW64 ~/prueba_git (master)
$
```

## Paso 4:
Añadimos el archivo a `archivos rastreados` 
``` bash
Borja@DESKTOP-G0V6A3S MINGW64 ~/prueba_git (master)
$ git add script.sh
warning: in the working copy of 'script.sh', LF will be replaced by CRLF the next time Git touches i
t

Borja@DESKTOP-G0V6A3S MINGW64 ~/prueba_git (master)
$ git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   script.sh

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        texto.txt

```

## Paso 5:
Establecemos una `versión sincronizada` del archivo

``` bash
Borja@DESKTOP-G0V6A3S MINGW64 ~/prueba_git (master)
$ git commit -m "Confirmacion inicial"
[master (root-commit) 5824c26] Confirmacion inicial
 1 file changed, 2 insertions(+)
 create mode 100644 script.sh

Borja@DESKTOP-G0V6A3S MINGW64 ~/prueba_git (master)
$ git status
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        texto.txt

nothing added to commit but untracked files present (use "git add" to track)

```

## Paso 6
Se añadieron los archivos al área de seguimiento mediante `git add` y se realizaron las confirmaciones de versión con `git commit`.
``` bash
Borja@DESKTOP-G0V6A3S MINGW64 ~/prueba_git (master)
$ git add texto.txt
warning: in the working copy of 'texto.txt', LF will be replaced by CRLF the next time Git touches i
t

Borja@DESKTOP-G0V6A3S MINGW64 ~/prueba_git (master)
$ git commit -m "Añadiendo archivo texto.txt"
[master 810a453] Añadiendo archivo texto.txt
 1 file changed, 3 insertions(+)
 create mode 100644 texto.txt

Borja@DESKTOP-G0V6A3S MINGW64 ~/prueba_git (master)
$ git status
On branch master
nothing to commit, working tree clean

```

## Paso 7: 

Se modificó el archivo `texto.txt`, comprobando su estado con `git status`, preparándolo en el área de trabajo  con `git add` y confirmando la nueva versión mediante `git commit`.

Comandos y salida:
```bash
Borja@DESKTOP-G0V6A3S MINGW64 ~/prueba_git (master)
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   texto.txt

no changes added to commit (use "git add" and/or "git commit -a")

Borja@DESKTOP-G0V6A3S MINGW64 ~/prueba_git (master)
$ git add texto.txt
warning: in the working copy of 'texto.txt', LF will be replaced by CRLF the next time Git touches i
t

Borja@DESKTOP-G0V6A3S MINGW64 ~/prueba_git (master)
$ git commit -m "Ampliada la explicación del texto"
[master 46bedd9] Ampliada la explicación del texto
 1 file changed, 1 insertion(+)

Borja@DESKTOP-G0V6A3S MINGW64 ~/prueba_git (master)
$ git status
On branch master
nothing to commit, working tree clean
```

## Paso 8: Información 

Se consultó el historial de cambios y las confirmaciones realizadas en el repositorio mediante los comandos `git log` y `git log --oneline`

Comandos y salida:
```bash
Borja@DESKTOP-G0V6A3S MINGW64 ~/prueba_git (master)
$ git log
commit 46bedd9d7d6b49652d34b16f917f0d3837b7a44f (HEAD -> master)
Author: Borja <borjaouton@gmail.com>
Date:   Mon Oct 26 13:10:32 2026 +0100

    Ampliada la explicación del texto

commit d889e2ca63c2a35806a4981adbfb0b9131ca53cd
Author: Borja <borjaouton@gmail.com>
Date:   Mon Oct 26 13:04:58 2026 +0100

    Amplaida la explicación de texto

commit 810a453e61b9b88c0450434e22cc589d19676214
Author: Borja <borjaouton@gmail.com>
Date:   Mon Oct 26 13:00:13 2026 +0100

    Añadiendo archivo texto.txt

commit 5824c264882662f494b6cb1f21674dd842567d95
Author: Borja <borjaouton@gmail.com>
Date:   Mon Oct 26 12:54:57 2026 +0100

    Confirmacion inicial

Borja@DESKTOP-G0V6A3S MINGW64 ~/prueba_git (master)
$ git log --oneline
46bedd9 (HEAD -> master) Ampliada la explicación del texto
d889e2c Amplaida la explicación de texto
810a453 Añadiendo archivo texto.txt
5824c26 Confirmacion inicial

Borja@DESKTOP-G0V6A3S MINGW64 ~/prueba_git (master)
$ git show
commit 46bedd9d7d6b49652d34b16f917f0d3837b7a44f (HEAD -> master)
Author: Borja <borjaouton@gmail.com>
Date:   Mon Oct 26 13:10:32 2026 +0100

    Ampliada la explicación del texto

diff --git a/texto.txt b/texto.txt
index 8c85792..23c83ff 100644
--- a/texto.txt
+++ b/texto.txt
@@ -2,3 +2,4 @@ uno
 dos
 tres
 cuatro
+cinco

```

## Paso 9:

Se modificó el archivo `texto.txt` añadiendo y eliminando líneas, y se comprobó el formato unificado de cambios mediante `git diff` antes de confirmar la versión

Comandos y salida:
```bash
Borja@DESKTOP-G0V6A3S MINGW64 ~/prueba_git (master)
$ nano texto.txt

Borja@DESKTOP-G0V6A3S MINGW64 ~/prueba_git (master)
$ git diff
warning: in the working copy of 'texto.txt', LF will be replaced by CRLF the next time Git touches it
diff --git a/texto.txt b/texto.txt
index 23c83ff..bf98941 100644
--- a/texto.txt
+++ b/texto.txt
@@ -1,5 +1,5 @@
 uno
 dos
-tres
 cuatro
 cinco
+seis

Borja@DESKTOP-G0V6A3S MINGW64 ~/prueba_git (master)
$ git commit -a -m "Probando diff"
warning: in the working copy of 'texto.txt', LF will be replaced by CRLF the next time Git touches i
t
[master ab089de] Probando diff
 1 file changed, 1 insertion(+), 1 deletion(-)

Borja@DESKTOP-G0V6A3S MINGW64 ~/prueba_git (master)
$ nano texto.txt

Borja@DESKTOP-G0V6A3S MINGW64 ~/prueba_git (master)
$ git diff
warning: in the working copy of 'texto.txt', LF will be replaced by CRLF the next time Git touches it
diff --git a/texto.txt b/texto.txt
index bf98941..430cdae 100644
--- a/texto.txt
+++ b/texto.txt
@@ -3,3 +3,4 @@ dos
 cuatro
 cinco
 seis
+siete
```
## Paso 10:

Se creó el archivo `.gitignore` para configurar las reglas de exclusión de ficheros temporales y compilados, comprobando su funcionamiento mediante `git status` y confirmando los cambios en el repositorio.

Comandos y salida:
```bash
$ git status
On branch master
Changes not staged for commit:
	modified:   texto.txt

Untracked files:
	.gitignore
	Hola.java

$ git commit -a -m "Añadidos fuentes en java y archivos importantes"
[master 83eb263] Añadidos fuentes en java y archivos importantes
 3 files changed, 15 insertions(+)
 create mode 100644 .gitignore
 create mode 100644 Hola.java

$ git status
On branch master
nothing to commit, working tree clean
```

## Paso 11: 
Se asignó una etiqueta para marcar la versión del proyecto y se comprobó su visualización en el histórico de confirmaciones mediante el comando log.

Comandos y salida:
```bash
Borja@DESKTOP-G0V6A3S MINGW64 ~/prueba_git (master)
$ git tag v0.7

Borja@DESKTOP-G0V6A3S MINGW64 ~/prueba_git (master)
$ git log --oneline
4752a62 (HEAD -> master, tag: v0.7) Añadidos fuentes en java y archivos importantes
ab089de Probando diff
46bedd9 Ampliada la explicación del texto
d889e2c Amplaida la explicación de texto
810a453 Añadiendo archivo texto.txt
5824c26 Confirmacion inicial

```

## Paso 12: 

Se creó una rama paralela llamada `Prueba`, se realizaron modificaciones en el archivo `Hola.java` de forma independiente sin afectar a la rama principal, se etiquetó la versión (`v0.7-Ent-Release`) y finalmente se fusionaron los cambios mediante `git merge`.

Comandos y salida:
```bash
Borja@DESKTOP-G0V6A3S MINGW64 ~/prueba_git (master)
$ git branch Prueba

Borja@DESKTOP-G0V6A3S MINGW64 ~/prueba_git (master)
$ git log --oneline
4752a62 (HEAD -> master, tag: v0.7, Prueba) Añadidos fuentes en java y archivos importantes
ab089de Probando diff
46bedd9 Ampliada la explicación del texto
d889e2c Amplaida la explicación de texto
810a453 Añadiendo archivo texto.txt
5824c26 Confirmacion inicial

Borja@DESKTOP-G0V6A3S MINGW64 ~/prueba_git (master)
$ git branch
  Prueba
* master

Borja@DESKTOP-G0V6A3S MINGW64 ~/prueba_git (master)
$ git switch Prueba
Switched to branch 'Prueba'

Borja@DESKTOP-G0V6A3S MINGW64 ~/prueba_git (Prueba)
$ git branch
* Prueba
  master

Borja@DESKTOP-G0V6A3S MINGW64 ~/prueba_git (Prueba)
$ git log --oneline
4752a62 (HEAD -> Prueba, tag: v0.7, master) Añadidos fuentes en java y archivos importantes
ab089de Probando diff
46bedd9 Ampliada la explicación del texto
d889e2c Amplaida la explicación de texto
810a453 Añadiendo archivo texto.txt
5824c26 Confirmacion inicial

Borja@DESKTOP-G0V6A3S MINGW64 ~/prueba_git (Prueba)
$ nano Hola.java

Borja@DESKTOP-G0V6A3S MINGW64 ~/prueba_git (Prueba)
$ git commit -a -m "Llegan los Ents a Java"
warning: in the working copy of 'Hola.java', LF will be replaced by CRLF the next time Git touches i
t
[Prueba 755b6e1] Llegan los Ents a Java
 1 file changed, 1 insertion(+)

Borja@DESKTOP-G0V6A3S MINGW64 ~/prueba_git (Prueba)
$ git tag v0.7-Ent-Release

Borja@DESKTOP-G0V6A3S MINGW64 ~/prueba_git (Prueba)
$ git log --oneline
755b6e1 (HEAD -> Prueba, tag: v0.7-Ent-Release) Llegan los Ents a Java
4752a62 (tag: v0.7, master) Añadidos fuentes en java y archivos importantes
ab089de Probando diff
46bedd9 Ampliada la explicación del texto
d889e2c Amplaida la explicación de texto
810a453 Añadiendo archivo texto.txt
5824c26 Confirmacion inicial

Borja@DESKTOP-G0V6A3S MINGW64 ~/prueba_git (Prueba)
$ git switch master
Switched to branch 'master'

Borja@DESKTOP-G0V6A3S MINGW64 ~/prueba_git (master)
$ cat Hola.java
class Hola {
 public static void main(String[] args){
 System.out.println("Welcome to the Java World");
 }
}

Borja@DESKTOP-G0V6A3S MINGW64 ~/prueba_git (master)
$ git merge Prueba
Updating 4752a62..755b6e1
Fast-forward
 Hola.java | 1 +
 1 file changed, 1 insertion(+)

```

## Paso 13:
Se practicó la eliminación de archivos bajo control de versiones mediante el comando `git rm`, utilizando la opción de forzado (`-f`) cuando el archivo presentaba cambios en el índice, y confirmando la baja en el repositorio.

Comandos y salida:
```bash
Borja@DESKTOP-G0V6A3S MINGW64 ~/prueba_git (master)
$ git rm -f importante~
rm 'importante~'

Borja@DESKTOP-G0V6A3S MINGW64 ~/prueba_git (master)
$ git commit -m "Eliminado el archivo importante~"
On branch master
nothing to commit, working tree clean
```

## Paso 14:

Se vinculó el repositorio local con el repositorio remoto en GitHub mediante el comando `git remote add`, y se subieron los cambios de la rama principal junto con la rama de pruebas utilizando `git push`.

Comandos y salida:
```bash
Borja@DESKTOP-G0V6A3S MINGW64 ~/prueba_git (master)
$ git remote add origin https://github.com/borjaouton-wq/prueba_git.git

Borja@DESKTOP-G0V6A3S MINGW64 ~/prueba_git (master)
$ git push -u origin master
info: please complete authentication in your browser...
Enumerating objects: 23, done.
Counting objects: 100% (23/23), done.
Delta compression using up to 6 threads
Compressing objects: 100% (15/15), done.
Writing objects: 100% (23/23), 2.07 KiB | 424.00 KiB/s, done.
Total 23 (delta 2), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (2/2), done.
To https://github.com/borjaouton-wq/prueba_git.git
 * [new branch]      master -> master
branch 'master' set up to track 'origin/master'.

Borja@DESKTOP-G0V6A3S MINGW64 ~/prueba_git (master)
$ git push -u origin Prueba
Total 0 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
remote:
remote: Create a pull request for 'Prueba' on GitHub by visiting:
remote:      https://github.com/borjaouton-wq/prueba_git/pull/new/Prueba
remote:
To https://github.com/borjaouton-wq/prueba_git.git
 * [new branch]      Prueba -> Prueba
branch 'Prueba' set up to track 'origin/Prueba'.
```
