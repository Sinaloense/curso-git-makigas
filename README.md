# LEER #

## Crear nuevo repositorio dentro de la carpeta actual
`git init`

## Agregar nombre de usuario, email y contraseña
```
git config --global user.name 'Juan Pérez'
git config --global user.email 'juanperez@example.com'
```

## Estado del repositorio
`git status`

- Existen 2 tipos de estados
    * unstaged `Archivo modificado (rojo)`
    * staged `Archivo listo para un proximo commit (verde)`



## Mover archivos de unstaged a staged
- Archivo individual
    * `git add fileName`
- Todos los archivos de la ruta actual
    * `git add .`

## Realizar cambios staged al repositorio con un comentario Vim
- Con comentario Vim
    * `git commit`

- Con comentario comentario directo
    * `git commit -a 'Comentario del commit'`

## Mostrar historial de commits en el repositorio
- Completo
    * `git log`
- Una linea
    * `git log --oneline`
- Mostrar todas las branch
    * `git log --oneline --all`

- Mostrar todas las branch con indicadores
    * `git log --oneline --all --graph`

## Mostrar que es lo que se ha editado
- Archivos unstaged y staged
    * `git diff`
- 2 commits
    * `git diff iD1 iD2`

## Actualizar mensaje del commit anterior con Vim (Esto actualiza el id del commit)
`git commit --ament`

## Desacer cambios de un archivo en estado modificado `Se perderan los cambios que no tengan commit`
- Archivo individual
    * `git checkout fileName`
- Todos los archivos de la ruta actual
    * `git checkout .`

## Mover archivos de staged a unstaged
- Archivo individual
    * `git restore --staged fileName`
- Todos los archivos de la ruta actual
    * `git restore --staged .`

## Uso de HEAD
- Obtener iD actual
    * `HEAD`
- Obtener iD antes del actual
    * `HEAD~1`
- Obtener iD 2 antes del actual
    * `HEAD~2`

## Eliminar commits que estan arriba del commit indicado `(Comando destructivo)`
- Eliminar commits y mantener cambios en unstaged
    * `git reset iD`
- Eliminar commits y mantener cambios en staged
    * `git reset iD`
- Eliminar commits y no mantener cambios
    * `git reset --hard iD`

## Revertir o desacer commit
- Revertir commit creando un commit que revierta los cambios
    * `git revert iD`
- Revertir commit sin hacer commit, dejando los cambios en staged `(Sirve para revertir mas de 1 commit)`
    * `git revert --no-commit iD`
    * Terminar y hacer el commit: `git revert --continue`

## Ramas
- Ver lista de ramas
    * `HEAD`
- Crear rama
    * `git branch branchName`
- Cambiar de rama
    * `git checkout branchName`
- Crear rama y cambiarnos a ella
    * `git checkout -b branchName`
- Cambiar nombre de una rama
    * `git branch -m branchNameOld branchNameNew`
- Eliminar rama `(Primero es necesario cambiarse a una rama que no sera eliminada)`
    * `git branch -d branchName`
    
## Combinar ramas
- Dirigirnos a la rama de destino
* `git checkout master`
- Combiar rama de destino con la rama de origen
* `git merge development`

## Tags
- Agregar tag a commit actual
* `git tag v0.2.0`
- Agregar tag a commit indicado con id
* `git tag v0.1.0 iD`
- Agregar tag con mensaje a commit indicado con id
* `git tag -a v0.1.0 iD`
- Eliminar tag
* `git tag -d v0.1.0`
- Mostrar tags
* `git tag`
- Mostrar tags con filtro
* `git tag -l 'v0.*.0'`
- Mostrar informacion de tag
* `git show v0.1.0`

## Stash `(Almacenar cambios localmente sin hacer commit para poder cambiarse de rama)`
- Almacenar cambios en stash
* `git stash`
- Almacenar cambios en stash con mensaje personalizado
* `git stash save 'Modificación en rama master'`
- Ver lista de stash actuales
* `git stash list`
- Aplicar stash
* `git stash apply iD`
- Eliminar stash
* `git stash drop iD`
- Aplicar stash y eliminar stash
* `git stash pop iD`

## Remote
- Agregar remoto
* `git remote add origin https://github.com/Sinaloense/curso-git-makigas.git`
- Ver remotos
* `git remote`
- Ver remotos y su URL
* `git remote -v`
- Subir repositorio (nombre de remoto y nombre de rama)
* `git push origin master`
- Subir repositorio a todos los remotos agregados
* `git push origin --all`