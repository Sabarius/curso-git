# Comandos Importantes de Git

## == git init
Inicializa el repostitorio.

## == git add filename
Agrega el archivo seleccionado al área de preparación.

## == git commit -m "mensaje"
Agrega todos los cambios que estan en el área de preparación al repositorio y además agrega lo que no esta en preparación pero si en trabajo, es como hacer add y commit.

## == git commit -m "mensaje" -a
Agrega todos los cambios que estan en el área de preparación al repositorio y además agrega lo que no esta en preparación pero si en trabajo, es como hacer add y commit.

## == git checkout filename
Actualiza de manera local el archivo seleccinado con la ultima versión que este en el repositorio de ese archivo, simpre y cuando no este agregado en el área de preparación.

## == git mv filename newfilename
Cambia el nombre de un archivo.

## == git show filename
Muestra información relacionada con el archivo que se seleccionó.

## == git diff --staged
Muestra la diferencia de las versiones entre lo que esta en el área de preparación y lo que esta en el repositorio. 

## == git log
Muestra la lista de todos los commits realizados.

## == git log --oneline
Solo muestra los commits de manera resumida.

## == git log --oneline --all
Muestra los commits de todas las ramas.

## == $ git diff 5061a9a 0ff0dce
Muestra la diferencia entre dos commits seleccionados.

## == $ git diff --name-only 5061a9a 0ff0dce
Muestra la diferencia entre dos commits seleccionados, pero solamente muestra el nombre de los archivos afectados.

## == $ git diff --word-diff 5061a9a 0ff0dce
Muestra la diferencia entre dos commits seleccionados, pero solamente muestra el texto.

## == $ git config --global core.abbrev "numero de digitos deseado"
Cambia la configuración del número de digitos que se muestran del identificador de un commit.

## == git commit amend
Modifica el mendaje del último commit realizado, y si ademas de modificar solamenete el mensaje tambieb queremos agregar alguna cosa mas tenemos que antes agregar los cambios que se quieren hacer al área de preparación y entonces ya desúes realizar el comando.

## == git rebase -i head~#
Modifica el commit que queramos, con el # seleccionamos cuantos commits antes de donde esta head esta posicionado el commit que queremos modificar. Nos aparecerá una ventana con los commits disponibles entonces cambiamos "pick" por "edit" en el que queramos cambiar, entonces cerramos la ventana emergente, hacemos los cambios que queramos y agregamos el commit. NOTA: Después de hacer esto se borrarán todos los commits que seguían depués de este commit.

## == git rebase --continue
Agrega el respto de los commits que se pudieran haber perdido después de haber modificado un commit que no fuera el último.

## == git reset --soft hushDELcommitAdesplzsarse
Mueve el puntero head para que apunte al commit del hush que se seleccionó, "borrando" de esta manera los commits que se encontraran después de este. Los commits que se "borraron" en realidad se ponen en el área de preparación por si queremos utilizarlos para algo más; no borra o sobreescribe las cosas que pudieran estar en el área de preparación a no ser que coincidan con alguno de los que se agregaron del commit que se "borró".

## == git reset --mixed hushDELcommitAdesplzsarse
Mueve el puntero head para que apunte al commit del hush que se seleccionó, BORRANDO de esta manera los commits que se encontraran después de este. Además, tambien LIMPIA el area de preparación BORRANDO cualquier cosa que estuviera ahí. No realiza ninguna modificación en lo que está en nuestra área de trabajo.

## == git reset --hard hushDELcommitAdesplzsarse
Mueve el puntero head para que apunte al commit del hush que se seleccionó, BORRANDO de esta manera los commits que se encontraran después de este. Además BORRA lo que esta en el área de preparación y solamente SOBREESCRIBE los cambios de nuestra área de trabajo con lo que esta en el commit del hush seleccionado en los archivos que coincidan con los que estaban en el commit, archivos que esten en nuestra área de trabajo pero que no estaban en el commit que se seleccionó no sufriran ningún cambio.

## == git branch
Muestra las ramas que hay en el repositorio y en la que estamos actualmente.

## == git branch nombre-de-la-rama-a-agregar
Crea una rama nueva con el nombre seleccionado.

## == git checkout nombre-de-la-rama-seleccionada
Forma de moverse entre ramas. No esta recomendada para usarse ya que no esta creada especificamene para moverse entre ramas.

## == git switch nomrbre-de-la-rama-seleccionada
Forma correcta y más segura para moverse entre ramas, esta es la recomendada para esto ya que es especifica para moverse entre ramas.

## == git checkout -b nombre-de-la-rama-a-crear
Forma NO correcta de crear una nueva rama y a la vez posicionarse en esa nueva rama creada.

## == git swtich -c nombre-de-la-rama-a-crear
Forma CORRECTA de crear una rama y a la vez posicionarse en esa nueva rama creada.

## == git branch -d nombre-de-la-rama-a-borrar
Borra la rama seleccionada, para borrar una rama NO debemos estar en esa rama.

## == git branch -m nombre-rama-a-renombrar nombre-nuevo
Sirve para cambiar el nombre de la rama especificada idependientemente de si estamos en esa ramma o no.

## == git branch -m nombre-nuevo-de-la-rama-actual
Cambia el nombre de la rama en la que nos encontramps actualmente.

## == git merge nombre-de-la-rama-a-fusionar-con-la-que-estamos
Fusiona el contenido de la rama de la cual pusimos el nombre con la rama en la que estamos actualmente.

## == git ls-tree hushDELcommit
Meuestra todos los archivos que hay en un commit especifico.

## == git ls-tree -r hushDELcommit
Meuestra todos los archivos Y directorios (carpetas) que hay en un commit especifico.

## == git ls-tree -r --name-only hushDELcommit
Meuestra solo los nombres de todos los archivos Y directorios (carpetas) que hay en un commit especifico.

## == git ls-tree -r --name-only HEAD 
Meuestra solo los nombres de todos los archivos Y directorios (carpetas) que hay en el último commit realizado (que es donde esta apuntando head).

## == git config --global core.excludesfile "C:ruta/del-archivo/del/.gitignore_global" 
Con esto podemos configurar un archivo .gitignore que sea como global para que funcione con todos nuestros repositorios.

## == git config --global alias.nombreDelAlias "comando --que se --quiere guardar" 
Sirve para crear un alias, esto es útil para asignarle nombres mas pequeños a comandos muy largos y que así sea mas sencillo su uso.

## == git log --oneline --graph --all
Muestra un log pero con una gráfica de los commits realizados y también las ramas creadas.

## == git reflog
Muestra todos los movimientos que ha tenido el puntero de head, podría decirse que muestra como un tipo historial.

## .gitignore
Es un archivo que se puede crear y en el se ponen cosas relacionadas con arhivos que se quieren ignorar a la hora de hacer algún add o commit para que no se suban, 
entonces cuando se realiza un add o un commit este archivo se lee para saber que cosas no se deben subir.

### archivo_de_texto.txt             
Esto va a ignorar el archivo con ese nombre especifico.
### *.txt                            
Esto va a ignorar a todos los archivos que terminen con .txt.
### !este_archivo_si_subirlo.txt     
Este hará una escepción y aunque arriba hace que se ignoren todos los .txt este si se subirá.
### fotos/                           
Esto ignorará todo lo que este adentro de la carpeta "fotos".
### !fotos/background.png            
Hará una escepción de lo que esta arriba y ese archivo especifico si lo subirá.

