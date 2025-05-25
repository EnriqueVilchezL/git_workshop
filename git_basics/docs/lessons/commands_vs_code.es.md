# Comandos básicos de Git que necesitas saber en Visual Studio Code

Para comenzar a usar Git en Visual Studio Code, sigue estos simples pasos:

1. **Crea un Repositorio en GitHub**  
   Ve a [github.com](https://github.com) e inicia sesión.  
   Haz clic en **"New repository"**, elige un nombre y crea tu repositorio remoto.

2. **Clona el Repositorio en tu Computadora**  
   Copia la URL del repositorio (usando HTTPS o SSH).  
   Luego, abre una terminal en tu computadora y ejecuta el siguiente comando:  
   `git clone https://github.com/usuario/nombre-del-repo.git`  
   Esto descargará el repositorio en una carpeta local.

3. **Abre la Carpeta del Proyecto en VS Code**  
   Abre VS Code y ve a `Archivo` > `Abrir carpeta...`.  
   Navega hasta la carpeta donde clonaste el repositorio y ábrela.

4. **Confía en los Autores**  
   Cuando VS Code te lo indique, haz clic en **"Sí, confío en los autores"**.  
   Esto permite que Git y otras funciones del entorno de trabajo funcionen correctamente y de forma segura.

En Visual Studio Code, hay una función incorporada para gestionar tu repositorio Git. En el lado izquierdo de tu ventana de VS Code, verás este símbolo:

![VS Code Git Symbol](imgs/vs_git.png)

Haz clic en él para usar la interfaz gráfica.

## `git add`

Este comando le dice a Git qué archivos quieres incluir en la próxima instantánea (commit).

Para agregar todos los archivos, haz clic en el símbolo `+` en la sección de cambios:

![VS Code Git Add All](imgs/vs_git_add_all.png)

Para agregar un archivo específico, haz clic en el símbolo `+` en el archivo que deseas agregar:

![VS Code Git Add](imgs/vs_git_add.png)

Verás tus archivos agregados en la sección `Staged Changes` (Cambios preparados):

![VS Code Staged](imgs/vs_git_staged.png)

---

## `git commit`

Este comando guarda los cambios que has agregado, junto con un mensaje que describe lo que hiciste.

Puedes establecer tu mensaje en el cuadro de `message` (mensaje). Cuando estés listo, simplemente presiona el botón `commit`:

![VS Code Commit](imgs/vs_git_commit.png)

---

## `git status`

Este comando no está disponible a través de VS Code. Puedes ver el estado de cada archivo con la interfaz de usuario, viendo si los archivos están `Staged` (Preparados). Si no ves ningún archivo en la sección de Git, entonces no has realizado cambios en esos archivos.

---

## `git push`

Este comando envía tus cambios confirmados a un repositorio remoto como GitHub.

Para ejecutar esto, simplemente presiona el botón `Sync Changes` (Sincronizar cambios):

![VS Code Push](imgs/vs_git_push.png)

Para ver estos comandos en la terminal, consulta los [Comandos de Git](commands.es.md).