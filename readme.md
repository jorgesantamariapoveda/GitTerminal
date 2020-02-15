Paso 11
-----------
* Comando: git reset --hard HEAD~1
* Explicación: la diferencia entre aplicar --hard o no aplicarla es que se pierden los cambios del
commit realizado (especificado por ~1 (un commit en este caso). Si no se hubiese aplicado el --hard
los cambios seguirían estando en el working copy. Con el simil de los minions viene a ser que en ambos casos
los sacamos del escenario (staging area) pero con --hard les quitamos además todo el maquillaje y sin hard
les dejamos el maquillaje por si queremos además cortales el pelo antes de volver a subirlos al escenario con
add y hacerles la foto con commit.
