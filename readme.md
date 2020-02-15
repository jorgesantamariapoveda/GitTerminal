#Paso 11: deshacer último commit (perdiendo los cambios realizados en el working copy)

**Comando**
*git reset --hard HEAD~1*

**Explicación**
La diferencia entre aplicar --hard o no aplicarla es que se pierden los cambios del
commit realizado (especificado por ~1 (un commit en este caso). Si no se hubiese aplicado el --hard
los cambios seguirían estando en el working copy. Con el simil de los minions viene a ser que en ambos casos
los sacamos del escenario (staging area) pero con --hard les quitamos además todo el maquillaje y sin hard
les dejamos el maquillaje por si queremos además cortales el pelo antes de volver a subirlos al escenario con
add y hacerles la foto con commit.

#Paso 12: rehacer el último commit

**Comando**
*git reflog*
*git reset --hard SHA*

**Explicación**
Tenemos que ir hacia nuestro hijo por lo que necesitamos del caminito de migas que proporciona reflog para
saber como se llama nuestro hijo (el SHA para los amigos). Aplico *git reflog*, gracias a los siempre útiles
comentarios es fácil identificarlo. Una vez sabido su nombre (SHA) y como queremos recuperar el estado intacto
tan solo hace falta hacer un *git reset --hard <SHA>*

#Paso 13: hacer un merge con master (styled abosrbe a master)

**Comando**
*git merge master*

**Explicación**
Aquí lo importante es saber quien absorbe a quien y como hacerlo. Como es styled quien absorbe a master es
en styled desde donde debemos sacar la cola succionadora para absorver a master. Puesto que ya estamos en
styled, para asegurarnos podemos ejecutar el comando *git branch*, solamente hay que indicar la rama que
será nuestra víctima *git merge nombreRamaVictimaAbsorbida*.
 
#Paso 19: hacer un merge de htmlify en styled (styled absrobe a htmlify)

**Comando**
*git checkout styled*
*git merge htmlify*

**Explicación**
Puesto que estamos en la rama *htmlify* y ésta será absorbida por *styled* hay que moverse a ésta última.
Por ello lo primero se realiza el *git checkout styled* y a continuación sacamos la cola succionadora con
*git merge htmlify*

#Paso 21: desde master, hacer un merge con styled

**Comando**
*git checkout master*
*git merge styled*

**Explicación**
Misma explicación que paso 19, salvo que como estamos en la rama *styled* debemos pasar a *master" y que
ahora es *styled* la que sufre la consecuencias y es absorbida por *master*. El mundo es así...

#Paso 25: dibujar el diagrama

**Comando**
*git log --graph*

**Explicación**
El comando *git log graph* nos muestra una especie de mapa del metro con los diferentes commits desde la
rama en la que estamos y con todas las bifurcaciones que se hallan podido surgir al crear una nueva rama
y también cuando es absorbida 

#Paso 26: hacer un merge "no fast-forward" de title en master

**Comando**
*git merge --no-ff title*

**Explicación**
Si no se hubiese especifado el parámetro *--no-ff* git hubiera realizado un merge *fast-forward* puesto
que en este caso eran lineales (formaban una lista los commits), y por lo tanto únicamente se hubiera
hecho un desplazamiento del puntero *HEAD* y *master* hacia el commit que es apuntado por *title*. De esta
otra forma lo que se fuerza es a crear un nuevo commit que es hijo tanto de donde apunta *title" como del
commit hasta ahora apuntado por *HEAD* y *master* y que ahora apuntaran a este nuevo commit

#Paso 27: deshacer el merge (sin perder los cambios del working copy)

**Comandos*
*git reset HEAD~1*

**Explicación**
Ha diferencia del paso 11 en el cual se querían los perder los cambios, en éste paso se pide
deshacer el commit pero manteniendo los cambios en el working copy. Esto tiene varios motivos,
como puede ser poner un comentario más apropiado a la hora de hacer el commit, hacer alguna 
mejora en el código, etc

#Paso 28: descartar los cambios

**Comandos**
*git checkout --git-nuestro.md*

**Explicación**
Puesto que tenemos los cambios presentes todavía en el working copy la forma de que quede en su
estado original es simplemente ejecutando *git checkout --<nombreArchivo>*

#Paso 29: eliminar la rama title

**Comandos**
*git branch -d title*

**Explicación**
Aquí lo importante es que para poder eliminar una rama, realmente se elimina el puntero no los
commits que se fuesen generando por esa rama, se ha de estar en una rama que no sea la que se 
va a eliminar. Como estamos en master no hay problema alguno.

#Paso 30: rehacer el merge que hemos deshecho
##Nota para Alberto: en este paso me he hecho un poco de lío. La forma de localizar el commit
en cuestión la tenía clara con el comando *git reflog*. El problema es que después me he
hecho un poco de lío para acceder a dicho commit por medio de su SHA. He utilizado el checkout
y claro me salía el famoso mensaje de que el HEAD estaba apuntado directamente a un commit. Después he intentando invertir la situación y total cuando veas el movimiento por un momento
ha cundido el pánico, por fin lo he podido resolver pero el reflog, entre esto y los paseitos
que he tenido que ir realizando para ir actualizando el readme, parece una peregrinación
**Comandos**
*git reflog*
*git reset --hard id*

**Explicación**
Bueno, pues lo dicho, con el *git reflog* obtengo el id gracias a los comentarios de los commits
y después es realizar un *git reset --hard <id>

#Paso 32: volver al commit inicial cuando se creó el poema

**Comandos**
git log
git reser --hard id**

**Explicación**
Como estoy en la rama master basta hacer un *git log* para ver el id (SHA) del primer commit
y a continuación un *git reset --hard id*
