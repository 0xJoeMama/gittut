# Git Gud

¿Así que has oído hablar de `git `pero no sabes qué es ni cómo se usa?\
Menos mal, porque estás en el lugar adecuado para aprender todo lo que
necesitas.

*Descargo de responsabilidad: Esto fue hecho para el* [*servidor de
discordia de Suited Llama*](https://discord.gg/fgbkwpg9Nw) *para ayudar
a la gente de allí a compartir mods, etc., pero cubre la mayoría de las
cosas comunes de git, por lo que podría valer la pena leerlo de todos
modos.*

Consulte las versiones traducidas:

- [English](https://github.com/rlDruDo/gittut)
- [Deutsch](https://github.com/rlDruDo/gittut/blob/master/README_Deutsch.md)
- [Ελληνικά](https://github.com/rlDruDo/gittut/blob/master/README_Greek.md)

## ¿Qué es git?

> Git is software for tracking changes in any set of files, usually used for coordinating work among programmers collaboratively developing source code during software development. Its goals include speed, data integrity, and support for distributed, non-linear workflows (thousands of parallel branches running on different systems)\
> [Wikipedia Git](https://en.wikipedia.org/wiki/Git)

Si tuviera que explicárselo a alguien que no tiene ni idea de nada de
eso, le diría: 
> Git es una herramienta para el seguimiento de los
cambios en los archivos y realmente genial para los proyectos en equipo.

Hay muchos sitios web diferentes que ofrecen servidores (para las
versiones gratuitas y de pago) donde puedes subir tus `repositorios`, es
decir, tus carpetas y mantener un proyecto.

Algunos ejemplos: 
- [GitHub](https://github.com) 
- [GitLab](https://about.gitlab.com) 
- [Bitbucket](https://bitbucket.org/product)

Pero también es posible ejecutar tu propio servidor git en una
RaspberryPi, por ejemplo.

## ¿Dónde se puede conseguir git?

Git es un software de código abierto y se distribuye bajo la [licencia
pública general GNU versión
2](https://en.wikipedia.org/wiki/GNU_General_Public_License#Version_2)
([Wikipedia Git](https://en.wikipedia.org/wiki/Git)).\
Así que no tienes que pagar por nada.

Linux y Mac suelen venir con una versión preinstalada de git. Si estás
en Windows es posible que necesites descargar e instalar git primero.
[Mira este enlace para más instrucciones y la
descarga.](https://git-scm.com/download/win)\
Hay clientes con interfaz gráfica de usuario, pero no voy a hablar de
ellos.

## Entonces, ¿cómo usamos git ahora?

En esta guía sólo cubriremos el uso a través de la Terminal/Consola y
vscode/IntelliJ.

¿Por qué esto último? Porque mucha gente en el [Discord de Suited
Llama](https://discord.gg/fgbkwpg9Nw) está usando estos programas para
hacer increíbles mods de Minecraft.

# Terminal/Consola

Para el propósito de esta guía crearemos una carpeta inútil con algunos
archivos inútiles y la subiremos a GitHub. Luego aplicar los cambios
locales al contenido de esta carpeta y actualizar nuestro repositorio. A
continuación, aplicar los cambios dentro del repositorio de GitHub y
tirar de ellos en su dispositivo. Finalmente crea una nueva rama y
empuja esta rama también.

Empecemos:

1.  Crea una nueva carpeta y nómbrala como quieras, sólo asegúrate de
    que no haya espacios y que sólo esté formada por letras de la
    `a a la z `y `del 1 al 9`. También se permite el uso de letras de la
    izquierda y de la `derecha`.

2.  Abra su terminal o su consola.

-   2.1. Windows: Para hacerlo en Windows busque un programa que se
    llama `Símbolo del sistema `y ábralo, si no lo encuentra consulte
    [esta
    guía](https://www.howtogeek.com/235101/10-ways-to-open-the-command-prompt-in-windows-10/)
    o [esta
    otra](https://towardsdatascience.com/a-quick-guide-to-using-command-line-terminal-96815b97b955).

    2.2. Linux: Pulsa `ctrl+alt+T `si no funciona, consulta [esta
    guía](https://towardsdatascience.com/a-quick-guide-to-using-command-line-terminal-96815b97b955).

    2.3. MacOS: Para abrir el Terminal en MacOS presiona `cmd+espacio `y
    entra en `Terminal presiona` Enter de nuevo y aparecerá una nueva
    ventana. Si esto no funciona, consulte [esta
    guía](https://towardsdatascience.com/a-quick-guide-to-using-command-line-terminal-96815b97b955).

3.  Su Terminal no estará en el directorio correcto (por lo tanto, no en
    la carpeta que creó en el paso 1). Para cambiar esto escriba: cd
    `ruta/a/su/carpeta`.\
    `cd `significa `cambiar de directorio`.

-   3.1 MacOS: Puede obtener la ruta de su carpeta haciendo clic con el
    botón derecho del ratón sobre su carpeta y manteniendo pulsada
    `la tecla Alt`. Ahora puedes seleccionar `copiar la ruta `(o algo
    similar). Puedes introducir la ruta pulsando `cmd+v`.

    3.2. Windows: Navegue hasta su carpeta. En la parte superior de la
    ventana hay una barra de direcciones. Puedes hacer clic en ella y
    copiar toda la ruta de la carpeta. Si tienes problemas sigue [esta
    guía](https://www.sony.com/electronics/support/articles/00015251).

    3.3. Linux: Lo más probable es que ya estés usando la consola para
    otros propósitos, así que asumo que sabes cómo hacerlo.\
    (También debo admitir que nunca he utilizado un sistema linux con
    interfaz gráfica y no tengo ni idea de cómo funcionan, ¡lo siento!)

4.  Ahora estás en el lugar correcto y necesitas inicializar un
    repositorio. Para ello, introduzca `git init `.\
    Este comando creará una carpeta oculta `.git`. Puedes asegurarte de
    que está ahí introduciendo ls `.git `o `dir .git `en Windows.\
    `ls `significa lista y dir.. (¿directorio tal vez?) sin embargo,
    producen el mismo resultado y listan todos los archivos y carpetas
    dentro de la carpeta .`git`.

Esta carpeta maneja todas las cosas relacionadas con git, como el
servidor que usas y tu nombre de usuario, etc.

5.  Ahora necesitas añadir un `remoto `a tu repositorio git. Un remoto
    es básicamente la dirección a la que se suben y descargan los
    archivos. Primero tenemos que hacer algunas otras cosas:

-   5.1. Vaya a [GitHub](https://github.com) e inicie sesión (o cree una
    cuenta).

    5.2 En la parte izquierda verás una pestaña llamada
    `Repositorios `junto a la que hay un botón llamado `Nuevo`. Haz clic
    en él para crear un nuevo repositorio.\
    Elige un nombre y decide si quieres hacerlo público o privado.\
    Deja el resto como está, lo cubriré más tarde.

    5.3 ¡Ahora has creado un repositorio vacío en GitHub!\
    Copie el enlace a este sitio web. Lamentablemente esto no funcionará
    en el futuro debido a razones de seguridad, necesitas añadir una
    clave SSH y los remotos vía SSH. No voy a cubrir esto en esta guía.\
    Mi enlace se ve así: https://github.com/rlDruDo/tets .

    5.4 Ahora vuelve a la terminal. Introduce
    `git remote add origin https://github.com/rlDruDo/tets `pero cambia
    mi enlace por tu enlace.\
    Este comando crea un nuevo remoto llamado origin que apunta a tu
    enlace. Es para subir y bajar.

    5.5 Asegúrate de que ha funcionado introduciendo `git remote -v `y
    comprueba si tu enlace aparece en la lista de `fetch `y `push`.

6.  A continuación, cree algunos archivos al azar dentro de su carpeta.
    Preferiblemente con un formato de archivo existente. Crea al menos
    un archivo .txt o .md.

7.  Ahora queremos subir el contenido de nuestra carpeta. La carga
    requiere varios pasos:

Primero añadimos nuestros archivos (no es necesario añadir todos los
archivos siempre, pero para el propósito de esta guía lo haremos). Luego
confirmamos esos archivos y finalmente se empujan estos archivos.

Para confirmar los cambios (archivos modificados) se introduce
`git add . `(Sí con el punto.) El punto indica que quieres añadir todos
los archivos, si no quieres eso, introduce cada archivo individualmente
separado por espacios.

Después de añadir todos tus archivos puedes comprobar si ha funcionado
introduciendo `git status`\
Este comando muestra el estado de tu repositorio git. Así es como se ve
el mío:\
![gitstatus](screens/gitstatus.png)

Ahora tenemos que confirmar los archivos con un mensaje de confirmación,
para ello introduzca `git commit -m "Su mensaje de confirmación"`\
El mensaje de confirmación debe ser un resumen **rápido** de los
cambios. Puedes considerar el uso de [gitmoji](https://gitmoji.dev).

Finalmente puedes subir tus archivos usando `git push`\
Si recibes un mensaje de error como este\
![errorgitpush](screens/error_gitpush.png)

A continuación, introduzca el comando que se muestra como
`git push --set-upstream origin master`

Genial! Ahora puedes crear un repositorio GitHub y subir tus archivos a
él. Pero\...

## \... ¿qué tal si descargo los cambios que hizo mi compañero de equipo?

Fácil.

1.  Vaya a su repositorio de GitHub.
2.  A continuación, haga clic en
    `Añadir archivo > Crear nuevo archivo `Llámelo algo.txt o algo.md y
    añada algunas líneas al azar

También puede añadir el archivo de prueba creado anteriormente haciendo
clic en este archivo y luego en el lápiz de la derecha. El que está en
el centro aquí:\
![pencil](screens/pencil.png)

3.  Ahora vaya al final de la página y pulse `Confirmar cambios`

Ahora ha simulado un cambio de un miembro del equipo.

4.  Vuelve a tu consola e introduce `git pull`\
    Te darás cuenta de que algo ha sucedido, si listas el contenido de
    tu carpeta verás que el nuevo archivo está aquí, así como los
    cambios que hiciste en tu archivo de prueba.

## De acuerdo, pero ¿qué pasa con la descarga de un repositorio existente?

También: Fácil.

Navega hasta la carpeta deseada e introduce el `git clone link`\
`Por `ejemplo,
`git clone https://github.com/SuitedLlama/An-Edible-World`

Ya sabes que tienes este repositorio instalado.

# hecho (por ahora)

Estos son los fundamentos de git. Voy a actualizar esta guía para apoyar
la ramificación y el uso de código de Visual Studio y IntelliJ. Sin
embargo, usted puede hacerlo en esos programas como he descrito
anteriormente a través de la construcción en los terminales. (Yo lo hago
así)

Que tengas una buena semana y que te mantengas saludable.
