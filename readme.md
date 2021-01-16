## Objetivo
Asentar los conceptos de git mediante el uso de comandos desde la terminal.

## Respuestas al cuestionario planteado

##### Paso 11: deshacer último commit (perdiendo los cambios realizados en el working copy)

**Comando**
_git reset --hard HEAD~1_

**Explicación**
La diferencia entre aplicar --hard o no aplicarla es que se pierden los cambios del commit realizado (especificado
por ~1 (un commit en este caso). Si no se hubiese aplicado el --hard los cambios seguirían estando en el
working copy. Con el simil de los minions viene a ser que en ambos casos los sacamos del escenario (staging area)
pero con --hard les quitamos además todo el maquillaje y sin hard les dejamos el maquillaje por si queremos
además cortales el pelo antes de volver a subirlos al escenario con add y hacerles la foto con commit.

##### Paso 12: rehacer el último commit

**Comando**
_git reflog_
_git reset --hard SHA_

**Explicación**
Tenemos que ir hacia nuestro hijo por lo que necesitamos del caminito de migas que proporciona reflog para
saber como se llama nuestro hijo (el SHA para los amigos). Aplico _git reflog_, gracias a los siempre útiles
comentarios es fácil identificarlo. Una vez sabido su nombre (SHA) y como queremos recuperar el estado intacto
tan solo hace falta hacer un _git reset --hard <SHA>_

##### Paso 13: hacer un merge con master (styled abosrbe a master)

**Comando**
_git merge master_

**Explicación**
Aquí lo importante es saber quien absorbe a quien y como hacerlo. Como es styled quien absorbe a master es
en styled desde donde debemos sacar la cola succionadora para absorver a master. Puesto que ya estamos en
styled, para asegurarnos podemos ejecutar el comando _git branch_, solamente hay que indicar la rama que
será nuestra víctima _git merge nombreRamaVictimaAbsorbida_.

##### Paso 19: hacer un merge de htmlify en styled (styled absrobe a htmlify)

**Comando**
_git checkout styled_
_git merge htmlify_

**Explicación**
Puesto que estamos en la rama _htmlify_ y ésta será absorbida por _styled_ hay que moverse a ésta última.
Por ello lo primero se realiza el _git checkout styled_ y a continuación sacamos la cola succionadora con
_git merge htmlify_

##### Paso 21: desde master, hacer un merge con styled

**Comando**
_git checkout master_
_git merge styled_

**Explicación**
Misma explicación que paso 19, salvo que como estamos en la rama _styled_ debemos pasar a *master" y que
ahora es *styled* la que sufre la consecuencias y es absorbida por *master\*. El mundo es así...

##### Paso 25: dibujar el diagrama

**Comando**
_git log --graph_

**Explicación**
El comando _git log graph_ nos muestra una especie de mapa del metro con los diferentes commits desde la
rama en la que estamos y con todas las bifurcaciones que se hallan podido surgir al crear una nueva rama
y también cuando es absorbida

##### Paso 26: hacer un merge "no fast-forward" de title en master

**Comando**
_git merge --no-ff title_

**Explicación**
Si no se hubiese especifado el parámetro _--no-ff_ git hubiera realizado un merge _fast-forward_ puesto
que en este caso eran lineales (formaban una lista los commits), y por lo tanto únicamente se hubiera
hecho un desplazamiento del puntero _HEAD_ y _master_ hacia el commit que es apuntado por _title_. De esta
otra forma lo que se fuerza es a crear un nuevo commit que es hijo tanto de donde apunta *title" como del
commit hasta ahora apuntado por *HEAD* y *master\* y que ahora apuntaran a este nuevo commit

##### Paso 27: deshacer el merge (sin perder los cambios del working copy)

**Comandos**
_git reset HEAD~1_

**Explicación**
Ha diferencia del paso 11 en el cual se querían los perder los cambios, en éste paso se pide
deshacer el commit pero manteniendo los cambios en el working copy. Esto tiene varios motivos,
como puede ser poner un comentario más apropiado a la hora de hacer el commit, hacer alguna
mejora en el código, etc

##### Paso 28: descartar los cambios

**Comandos**
_git checkout --git-nuestro.md_

**Explicación**
Puesto que tenemos los cambios presentes todavía en el working copy la forma de que quede en su
estado original es simplemente ejecutando _git checkout --<nombreArchivo>_

##### Paso 29: eliminar la rama title

**Comandos**
_git branch -d title_

**Explicación**
Aquí lo importante es que para poder eliminar una rama, realmente se elimina el puntero no los
commits que se fuesen generando por esa rama, se ha de estar en una rama que no sea la que se
va a eliminar. Como estamos en master no hay problema alguno.

##### Paso 30: rehacer el merge que hemos deshecho

########### Nota: Alberto, en este paso me he hecho un poco de lío. La forma de localizar el commit

en cuestión la tenía clara con el comando _git reflog_. El problema es que después he hecho un
_git checkout id_ y claro me salía el famoso mensaje de que el HEAD estaba apuntado directamente
a un commit, he intentando revertir la situación y por un momento he entrado en pánico. Me he
parado un momento a pensar y por fin lo he podido resolver.
**Comandos**
_git reflog_
_git reset --hard id_

**Explicación**
Bueno, pues lo dicho, con el _git reflog_ obtengo el id gracias a los comentarios de los commits
y después es realizar un _git reset --hard <id>_

##### Paso 32: volver al commit inicial cuando se creó el poema

**Comandos**
_git log_
_git reser --hard id_

**Explicación**
Como estoy en la rama master basta hacer un _git log_ para ver el id (SHA) del primer commit
y a continuación un _git reset --hard id_

##### Paso 33: volver al estado final, cuando pusimos título al poema

**Comandos**
_git reflog_
_git reset --hard id_

**Explicación**
De nuevo vuelvo a ejecutar _git reflog_ para encontrar gracias a los comentarios el id o SHA
del commit en cuestión que se realizó en el paso 23. Una vez encontrado se ejecuta el comando
_git reset --hard id_
