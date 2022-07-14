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
### 34. Stash es un lugar como un banco donde se guarda todo lo que estabas trabajando y no estaba con commit con el siguiente comando guardas en el Stash
	    git stash
### 35. Desplegar mi Stash
	    git stash pop
### 35. Muestra la lista de Stash que tengo
Ojo: Git no te dice que tienes stash
	    git stash list
### 36. Borrar todos los stash
	    git stash clear
### 37. Recuperar un Stash determinado
	stash@{0}: WIP on master: 9c2799a conflictos en stash resuelto
	stash@{1}: WIP on master: 9c2799a conflictos en stash resuelto
	stash@{2}: WIP on master: 9c2799a conflictos en stash resuelto
#### Comando
	    git stash apply <codigo del stash>
#### Ejemplo
	    git stash apply stash@{0}
### 37. Borrar un Stash determinado
	    git stash drop stash@{0}

### 38. Muestra un poco de la informacion de un stash
	    git stash show stash@{1}
#### Resultado
	villanos.md | 1 +
 	1 file changed, 1 insertion(+)
### 38. Guardar un Stash pero ahora con nombre o mensaje
	    git stash save "Inserte el mensaje aqui"
### 39. Muesta mas informacion de los Stash
	    git stash list --stat
### 40. Git Rebase
	    git rebase <nombre de la rama
### 41. Git rebase iteractivo este ejemplo es para unir dos commits que son parecidos en mensaje
##### Este comando toma 4 commits antes del Head
	    git rebase -i HEAD~4 
<img src="https://github.com/mabatule/Basic-github-commands/blob/main/image%20examples/imagen%204.png?raw=true" width="600px" height="500px">
##### aqui se puede ver los 4 commits tomados ahora con los comandos ayuda escribimos squash que lo que hace es unir con el commit anterior
<img src="https://github.com/mabatule/Basic-github-commands/blob/main/image%20examples/img%205.png?raw=true" width="600px" height="500px">
##### luego aparecera con que mensaje se quedara la union del commit
<img src="https://github.com/mabatule/Basic-github-commands/blob/main/image%20examples/img%206.png?raw=true" width="600px" height="500px">
##### resultado
<img src="https://github.com/mabatule/Basic-github-commands/blob/main/image%20examples/img%207.png?raw=true" width="600px" height="500px">
### 42. Git rebase iteractivo este ejemplo para cambiar el mensaje de un commit
##### Este comando toma 4 commits antes del Head
	git rebase -i HEAD~4 
##### Primero se coloca reword en el pick y luego Esc + : + wq!
<img src="https://github.com/mabatule/Basic-github-commands/blob/main/image%20examples/img%208.png?raw=true" width="600px" height="500px">
##### Luego de esto aparecera a esos dos que se colocaron reword para actualizar sus mensajes 

### 43. Como separar un commit que hice por accidente con Rebase
##### Este comando toma 4 commits antes del Head
	    git rebase -i HEAD~4
##### En la ventana siguiente reemplazamos al pick por un edit y asi entrara en modo rebase
<img src="https://github.com/mabatule/Basic-github-commands/blob/main/image%20examples/img%209.png?raw=true" width="600px" height="500px">
##### Ahora que estara en modo rebase en el cual ahora combinamos el reset para volver y ahora si nos aparece en el stage los dos archivos modificados y simplemente los commiteamos cada uno
<img src="https://github.com/mabatule/Basic-github-commands/blob/main/image%20examples/img%2010.png?raw=true" width="600px" height="500px">

# GitHub
### 43. comando para subir los tags
    	git push --tags

### 44. Actualizar 
	    git pull
### 45. Actualizar si hay conflictos
	    git pull --rebase

### 46. Subir cambios locales
	    git push
### 47. Comando para ver donde esta apuntando mi repositorio
	    git remote -v

### 48. Git Fetch actualizar las referencias locales
	    git fetch

### 49. Flork basicamente es clonar un repositorio y crearlo en mi repositorio manteniendo los historial de los commits
##### ahora para cuandoo hacemos 
		git remote -v
##### con este comando podemos ver nuestro repositorio
<img src="https://github.com/mabatule/Basic-github-commands/blob/main/image%20examples/img%2011.png?raw=true" width="600px" height="500px">
##### para hacer un pull del repositorio original primero tenemos que agragarlo con upstream
		git remote add upstream <url del respositorio> <nombre de la rama que quiero traer los datos>
##### ahora para actualizar hacemos
		git pull upstream
### 50. Para traer todos los cambios incluyendo la rama de otro compañero
		git pull --all
### 51. Ver todas las ramas de mi repositorio
		git branch -a
### 52. Limpiar ramas que ya no son necesarias y no existen en mi repositorio 
		git remote prune origin
### 53. Issues sirve para hacer preguntas al codigo y tambien recomendaciones en el cual se pueden resolver o no, ahora para marcar una solucion de un Issues se hace asi:
		git commit -am "Fixes #5: mensaje cualquiera"
