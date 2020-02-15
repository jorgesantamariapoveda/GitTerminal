#Paso 11: deshacer último commit

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
será nuestra víctima *git merge nombreRamaVictimaAbsorbida*
 

