# Basic-github-commands
Estos son comandos basicos utilizados por mi persona
![N|Solid](https://marketing4ecommerce.net/wp-content/uploads/2018/06/GitHub-logo-2-imagen.jpg)

### 1. Git no agrega los folders vacios por lo cual si lo quieres agregar estos tienes que poner un archivo .gitkeep
[Image example]
### 2. Cuando estamos en algun editor la accion para salir
        :q!
### 3. Para salir y guardar desde el editos
        :wq!
### 4. Cambiar nombre que viene por defecto una rama
        git config --global init.defaultBranch <name>
### 5. Informacion de los commits, informacion de la rama donde se encuentra, tambien lo que añades dentro el repositorio
        git status 
### 6. Elimina un archivo en espefico de mis cambios agregados
        git reset <nombre del archivo>
### 7. Agrega comentario a nuestros cambios
        git commit -m "Primer commit"
### 8. Reconstruye el proyecto a como estaba antes del ultimo commit cualquiera de los dos comandos
        git checkout -- .
	    git reset --hard
### 9. Cambiar el nombre de una rama
        git branch -m <nombre actual> <nuevo nombre> 
### 10. Hacer pasos directos de Add. y commit
###### Ojo: esto funciona si el archivo esta en seguimiento o que no tenga la U de untrack
#
        git commit -am "readme actualizado"
### 11. Muestra un historial para los commits y quienes sus autores
        git log
### 12. Agrega todos los archivos al Staged Changes
        git add .
### 13. Agregar todas las las extensiones .html al Staged Changes
        git add *.html
### 14. Agregar extencioes pero ya dentro de folders al Staged Changes
        git add <name folder>/*.<extension>
#### Example:
git add JavaFolder/*.js
### 15. Agregar un folder completo a git al Staged Changes
        git add <folder>/
##### Example:
git add css/
### 16. Modificar user, alias esto sirve para mejorar la visibilidad 
Primero se va a la configuracion con este comando
```
    git config --global -e
```
En la parte del alias se puede colocar cuallquiera de estos son una manera resumida ojo solo uno
```
    s = status --short
    s = status -sb
```
LLamado ahora del status esa asi:
```
    git s
```
### 17. git status alias alternativo
        git status alias alternativo
### 18. Para el comando de 'git log' para tenerlo de una manera resumida usar este comando
git config --global alias.lg "log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(bold yellow)%d%C(reset)' --all"
### 19. Arregla el mensaje del commit que escribiste mal 
OJO: solo para el ultimo commit
```
    git commit --amend -m "Inserte su mensaje" 
```
### 20. Como agregar a un mismo commit archivos que me olvide 
El comando reset --soft no elimina los cambios 
		git reset --soft HEAD ^ 2
```
HEAD: India el numero de comits antes que quieres seleccionar 
^   : Indica el ultimo commit antes del HEAD
2   : Apunta al ultimo commit 
```
Ejemplo: 
|Comando|Explicacion|
|--------|--------|
| git reset --soft HEAD^ | un commit antes del HEAD |
| git reset --soft HEAD^2 | 2 commits antes del HEAD |
### 21. Como arreglar un comit de otra manera
#### Supongamos que tenemos esto con git lg
```
    git lg
```
#### Resultado en consola
    * 858d03f - (6 seconds ago) Agregamos a linterna verde - mabatule (HEAD -> main)
    * 2b21695 - (17 minutes ago) Agregamos la historia de Batman y Superman - mabatule
    * 4184e15 - (19 minutes ago) Agregamos ciudades.md - mabatule
    * c1e57bb - (20 minutes ago) Agregamos heroes.md - mabatule
    * f4fa011 - (20 minutes ago) Agregamos misiones.md - mabatule
    * 142afc7 - (22 minutes ago) Readme agregado - mabatule
#### Ahora queremos volver hasta el commit de "2b21695" pero queremos mantener los cambios del commit "858d03f"
```
    git reset --soft 2b21695
```
#### Ahora si podemos reacer nuestro commit porque lo deja hasta ese punto y los cambios que se hicieron es como sino se hubieran subido

### 22. Comandos de reset
|Comando|Explicacion|
|--------|--------|
|git reset --hard <hash>|borra los cambios hasta el comit que se selecciono|
|git reset --mixed <hash>(predeterminado)|anular cambios + anular cambios, los cambios se dejan en el árbol de trabajo|
|git reset --soft <hash>|cambios anulados , los cambios se dejan por etapas ( stage ).|
### 23. Esto es toda la linea de tiempo y salvacion xD
        git reflog
#### OJO
Sirve de mucho porque si eliminaste cosas y quieres volver a un commit copias el <hash>
```
    git reset -hard <hash>
```
### 24. Cambiar el nombre de un archivo
        git mv antes.md despues.md
### 25. Eliminar archivo 
        git rm salvar-mundo.md 
### 22. Gitignore esto se coloca como un archivo en la raiz donde se agrega las cosas que el proyecto debe ignorar
node_modules/
dist/
server.log
### 23. Uniones de ramas
|Nombre|Explicacion|
|--------|--------|
|Fast-Forward|este sucede cuando no hay cambios en la rama principal y basicamente agregaste cosas|
|Uniones Automaticas|git dectecta que hubo cambios en mi rama principal que las ramas secundarias desconoce, pero esto sucede si no fueron lineas iguales y no hay conflictos entonces lo hace automatico|
|No automatica|esto sucede cuando hay conflictos en el merge cuando dos ramas tocan la misma linea|
### 24. Crear rama
        git branch <nombre de la rama>
	    git checkout -b <nombre de la rama> con este comando directo nos movemos a la rama
### 25. Eliminar una rama
        git branch -d <nombre de la rama>
#### Aviso
  Hay casos donde si en esa rama hubo cambios que no fueron mergeados te da una advertencia que si estas seguro de borrar
#### Si estas seguro de borrar entonces este comando que fuerza a borrarlo
        git branch -d <nombre de la rama> -f
### 26. Unir dos ramas Merge
Ojo : tienes que estar donde quieres unir
```
    git merge <rama a unir>
```
### 27. TAGS o etiquetas es una referencia en un commit en el tiempo esto se usa para marcar Release o Versiones de la APP
#
##### Normalmente se pone ej: V1.2.3
ahora que significan eso numeros
|Comando|Explicacion|
|--------|--------|
|V1|Hubo cambios importantes|
|2|Aqui es donde se agregaron funcionalidades pero no es considerado una version mayor|
|3|Aqui es un Bob fix es decir correcion de errores|
### 28. Mostrar todos los tags
        git tag
### 29. Crear un tag , esto hace tag al ultimo commit ojo
        git tag <nombre del tag>
### 30. Eliminar un tag 
        git tag -d <nombre del tag>
### 31. Crear un tag en un commit
        git tag -a <nombre del tag> <hash del commit> -m "Mensaje cualquiera" 
### 32. Crear un tago con un mensaje
        git tag -a <nommbre del tag> -m "mensaje del tag"
### 33. Mostrar mas informacion de un tag
        git show <nombre del tag>
