# COMANDOS GIT

_ En esta lección aprenderás introducir órdenes a través de una Interfaz de Línea de comandos, en lugar de hacerlo en una Interfaz Gráfica de Usuario. La Interfaz de Línea de comandos es útil cuando el usuario necesita un mayor grado de precisión para llevar a cabo su investigación.

_Se utilizara los comandos simples para el uso de git.

-----------------------------------------------------------------------

..commit= Es como guardar un punto de partida, donde se puede regresar a ella.
-----------------------------------------------------------------------

--) git init : Este comando marca el inicio del proyecto, monitorea todos los trabajos (se inicia solo una vez, y siempre se debe 
              incia cuando monitoreamos algun proyecto).

--) git status :Nos dice el estado de nuestro proyecto, nos mostrara que archivos aun no han sido agregados.
--) git add :Con este comando decimos que archivos estan listos para crear un commit
    git add -A : agregamos todos los archivos que se encuentran en esa carpeta.
--) git add . : agregamos todos los archivos que se encuentran en esa carpeta. 

--) git commit -m "Algun mensaje" : guarda los cambios que se hicieron, con un mensaje que identifique que cambios se hicieron
--) git log :Nos va dar una lista de nuestros commit. con su autor, fecha, descripcion y codigo sha
--) git log > commit.txt : Nos va generar un txt con todo los commit.

--) git checkout : Con este comando  viajamos atraves de nuestros commits o nuestra ramas. (devolver a un punto de partida anterior),
             con el comando "git log" obtenemos el sha que vayamos a utilizar, ejemplo: 
               >git checkout 058c4ce38ab4da7f4320563d3c28f18d9402f3e5< nos sale un mensaje donde nos indica a donde iremos(al punto de partida anterior)
--) git checkout master : Nos regresa al ultimo commit que se tiene.

--) git reset : Es similar a "git checkout", pero a diferencia este elimina el commit.
--) git reset --soft : Es el mas simple y no borra nuestro "Working Area"(Nuestro codigo).
--) git reset --mixed : borra el "Stating Area", sin tocar el "Working Area".
--) git reset --hard : Borra todo lo que hay en el commit.("CUIDADO").

--)git commit --amend -m "algo" :Edita el ultimo commit ingresado.


********----Ramas y Fusiones---********

.Ramas: Es una linea de tiempo en nuestro proyecto, que sirven para arreglar errores, experimentar, hacer grandes cambios.
.Ramas Master: La rama master es en donde comenzamos a trabajar, es la rama principal y estable de nuestro proyecto.

EJEM:

--) git branch : Nos muestra las ramas master que se tienen.(Inicialmente solo se tiene la rama master, y se tiene marcada con * y iluminada porque
               es en la que se esta trabajando).

--) git branch "Nombre de la rama" :Para crear una rama.
--) git checkout Test : Nos movemos a nuestra rama con el nombre de "Test". Todos los cambios que se hagan apartir de ahora no se iran a *master, 
              Permaneceran en *Test.
--) git branch -d "Nombre de la rama" : Este comando borra las ramas que no estamos usando.

.Fusiones: Son las creaciones de un commit, juntando una rama con otra, es decir juntar la rama "Test" y la rama "master", y con esto se crea
          un nuevo commit. (Para hacerlo; primero nos situamos en la rama que va absorver es decir rama "master")
--) git merge "Nombre de la rama" : para fusionar estas ramas.

--) git branch -a : se ven las Ramas ocultas 

********---- GitHub(Cualquier cliente)----*********

--) git clone "url" :nos sirve para clonar un proyecto, normalmente, se usa cuando no nos interesa colaborar en el proyecto.
--) git remote add origin "url (del repositorio creado en nuestro GitHub)" : vincula nuestro proyecto local, con nuestro proyecto remoto.
--) git remote -v :Para comprobar que este sicronizado con el repositorio remoto.
--) git remote remove origin :Para quitar lo que acabamos de hacer(la conexion al proyecto en github).

--) git push :Manda nuestros cambios(commits) a GitHub.
--) git push origin master : Mandamos nuestra rama principal "master", cada vez que agregamos un commit tenemos que envialos con este codigo para que se sicronice con github.
--) git push origin master -f :Fuerza a que se suban estos cambios en eñ GitHub(En caso que editamos un commit) 


--++Nota: Cuando subimos un commit a nuestro Github(Remoto), y lo buscamos en gitHub no aparece, ya que se creo otra rama y podemos buscarla en las ramas.
--++ Nota: Para unir estas ramas en el Github, tenemos que hacerlo primero en el git y luego lo sincronizamos con el Github

*********----Issues----*********

.Issues: son una forma continuar,mejorar o solucionar un error en nuestro repositorios
.Milestones: Son grupos de issues que aplican para un proyecto,carateristicas o un periodo de tiempo.
.Label: son una manera de organizar diferentes tipos de problemas.    


******* -----TAGS(Etiquetas)---*******

.Tags : Son simple puntos especificos en la historia de nuestro proyecto y se usan para marcar alguna version del mismo.
.Tags anotadas : son almacenadas como objetos completos dentro de la base de Git y contienen mas informacion.
.Tags ligeras : son otra forma de crear tags, mas simples y con poca informacion.

EJEM:

--) git tag -a V0.11 -m "version 0.11 ....." : Creamos un tag con una version del ultimo commit(V0.11).

--) git tag -a V0.1 -m "version 0.1 ....." 'numero de sha' : Agregamos una version a un commit especifico con el codigo sha.

--) git push origin V0.11 : Para compartir nuestro tag en el GitHub, con la version 'V0.11'.

--) git push origin --tags : Con este comando subimos todos los tags que tenemos, ahorrando la necesidad de subirlos uno por uno.


********------WORKFLOWS (flujo de trabajos)----*******

.Workflows : Es un flujo de trabajo(-Proyectos propios, -Proyectos en equipo, -Proyectos con terceros).
.Proyectos propios : Somos los dueños, decidimos todo lo que pasa en el repositorio.
.Proyectos en equipo :Es parecido a trabajar solo, con la excepcion de que habra commits de nuestro equipo.

--) git fetch origin : Para bajar los cambios que alguien mas realizo en nuestro proyecto, quedan en la rama oculta
--) git merge origin/master : Con esto funcionanmos la rama oculta con la rama master.


