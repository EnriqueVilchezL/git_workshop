# 🛠️ Cómo instalar Git y usar GitHub

¡Hola! 👋 Vamos a configurar Git en tu computadora y conectarlo a GitHub. Es más fácil de lo que crees, ¡solo sigue los pasos a continuación!

---

## 💻 Instalando Git en tu computadora

Elige tu sistema operativo a continuación para ver las instrucciones correctas 👇

=== "🪟 Windows"

    1. Ve a [https://git-scm.com/download/win](https://git-scm.com/download/win)
    2. Descarga el archivo y ejecútalo.
    3. Haz clic en "Siguiente" durante la instalación; la configuración predeterminada es perfecta.
    4. ¡Listo! 🎉

=== "🍏 Mac"

    1. Abre la aplicación **Terminal** (busca "Terminal").
    2. Escribe esto y presiona Enter:
       `git --version`
    3. Si dice que Git no está instalado, escribe:
       `xcode-select --install`
    4. Sigue las instrucciones que aparezcan. ✅

=== "🐧 Linux (Ubuntu)"

    1. Abre **Terminal**.
    2. Escribe los siguientes comandos uno por uno y presiona Enter:

       ```bash
       sudo apt-get update
       sudo apt-get install git
       ```
    3. ¡Todo listo! Git está instalado y preparado. 💪

---

## ✍️ Configuración inicial de Git

### Dile a Git quién eres

Después de instalar Git, abre **Git Bash** (en Windows) o la **Terminal** (en Mac o Linux). Luego escribe lo siguiente 👇

🖥️ *Escribe en la terminal:*

    git config --global user.name "Tu Nombre"
    git config --global user.email "tu.email@example.com"

Esto le dice a Git cómo firmar tus proyectos (como si dejaras tu firma digital).

---

## 🔐 ¿Qué pasa la primera vez que usas `git clone`?

Cuando intentas copiar (o "clonar") un proyecto desde GitHub por primera vez, Git necesita saber que realmente eres tú. Esto se llama **autenticación**, y funciona de forma diferente según tu computadora:

---

=== "🪟 Windows"

    1. Abre **Git Bash** y escribe lo siguiente para clonar tu repositorio:
    ```bash
    git clone https://github.com/tu-usuario/tu-repositorio.git
    ```

    2. Se abrirá una **ventana del navegador** automáticamente.
    3. Inicia sesión en GitHub con tu usuario y contraseña, como si entraras normalmente a la página.
    4. ¡Listo! 🎉 Git recordará que eres tú y no volverá a pedir tu contraseña cada vez que uses Git.

    > ✅ Esto es posible gracias a una herramienta llamada **Git Credential Manager (GCM)**, que ya viene incluida en Git para Windows. Guarda tus credenciales de forma segura en tu computadora.

=== "🍏 Mac"

    1. Abre tu navegador y ve a esta página:  
    [https://github.com/settings/tokens](https://github.com/settings/tokens)

    2. Haz clic en **"Generate new token"**.
    3. Toma en cuenta esto para crearlo:
        - Ponle una nota para recordar de qué es el token (por ejemplo, "Para acceso a repositorios").
        - Elige una duración (por ejemplo, 90 días). Al finalizar los 90 días, deberás crear un nuevo token y repetir estos pasos. Si no quieres que expire, puedes indicar que no tenga fecha de expiración. ⚠️ Esto no se recomienda por motivos de seguridad, pero tú decides si te queda más cómodo.
        - Marca la opción `repo` para darle permisos y que funcione con tus proyectos.

        ![Opcion repo en GitHub](imgs/option_repo.png)

    4. Haz clic en **"Generate token"** al final.  
    🔐 Copia ese código que aparece (¡guárdalo o pégalo en un lugar seguro porque luego no se puede recuperar!).

    5. Luego abre la **Terminal** y escribe:
        ```bash
        git config --global credential.helper store
        ```
        Esto le dice a Git que guarde tus credenciales para que no tengas que estar escribiendo tu token cada vez que interactúas con el repositorio de GitHub. Luego, intenta clonar tu repositorio:
        ```bash
        git clone https://github.com/tu-usuario/tu-repositorio.git
        ```

    6. Git te va a pedir:

        - Tu **nombre de usuario de GitHub**
        - Tu **token** (ese código largo que copiaste antes). Cuando pegues el token, no verás nada en la terminal, y eso es completamente normal. El token se pegó, pero la terminal no lo muestra porque se trata como una contraseña.

    7. Listo! Ahora puedes hacer `git push`, `git clone`, etc. sin problema.

    > ⚠️ Esto guardará tu token en un archivo de texto dentro de tu computadora. Funciona bien si es tu PC personal, pero no lo hagas en computadoras públicas o compartidas.

=== "🐧 Linux"

    1. Abre tu navegador y ve a esta página:  
    [https://github.com/settings/tokens](https://github.com/settings/tokens)

    2. Haz clic en **"Generate new token"**.
    3. Toma en cuenta esto para crearlo:
        - Ponle una nota para recordar de qué es el token (por ejemplo, "Para acceso a repositorios").
        - Elige una duración (por ejemplo, 90 días). Al finalizar los 90 días, deberás crear un nuevo token y repetir estos pasos. Si no quieres que expire, puedes indicar que no tenga fecha de expiración. ⚠️ Esto no se recomienda por motivos de seguridad, pero tú decides si te queda más cómodo.
        - Marca la opción `repo` para darle permisos y que funcione con tus proyectos.

        ![Opcion repo en GitHub](imgs/option_repo.png)

    4. Haz clic en **"Generate token"** al final.  
    🔐 Copia ese código que aparece (¡guárdalo o pégalo en un lugar seguro porque luego no se puede recuperar!).

    5. Luego abre la **Terminal** y escribe:
        ```bash
        git config --global credential.helper store
        ```
        Esto le dice a Git que guarde tus credenciales para que no tengas que estar escribiendo tu token cada vez que interactúas con el repositorio de GitHub. Luego, intenta clonar tu repositorio:
        ```bash
        git clone https://github.com/tu-usuario/tu-repositorio.git
        ```

    6. Git te va a pedir:

        - Tu **nombre de usuario de GitHub**
        - Tu **token** (ese código largo que copiaste antes). Cuando pegues el token, no verás nada en la terminal, y eso es completamente normal. El token se pegó, pero la terminal no lo muestra porque se trata como una contraseña.

    7. Listo! Ahora puedes hacer `git push`, `git clone`, etc. sin problema.

    > ⚠️ Esto guardará tu token en un archivo de texto dentro de tu computadora. Funciona bien si es tu PC personal, pero no lo hagas en computadoras públicas o compartidas.

---

Si usas Git por primera vez, no te preocupes si algo no sale perfecto. ¡Todo el mundo aprende poco a poco! 🧠✨

## 🌐 ¿Qué es GitHub?

GitHub es un sitio web gratuito donde puedes:

- 🗃️ **Almacenar tus proyectos en línea**: Imagina que es como un gran disco duro en la nube para todo tu código.
- 👯 **Colaborar con otros**: Trabaja en equipo en un mismo proyecto sin sobrescribir el trabajo de los demás.
- 📣 **Mostrar tu trabajo al mundo**: Comparte tus creaciones con reclutadores, amigos o la comunidad.

Git es la herramienta que usamos para llevar el control de versiones local, y GitHub nos ayuda a compartir ese control de versiones con más personas, en distintas máquinas.

---

## 🚀 Cómo usar GitHub

- Ve a [https://github.com](https://github.com) y **regístrate para obtener una cuenta gratuita**.

![GitHub SignUp](imgs/github_signup.png)

- En la esquina superior derecha, haz clic en el icono **+** y elige **New repository** (Nuevo repositorio).

![GitHub New Repository](imgs/github_new_repo.png)

- Dale un nombre a tu proyecto (como `mi-primer-proyecto`) y haz clic en **Create repository** (Crear repositorio).

![GitHub Create Repository](imgs/github_create_repo.png)

Git tiene muchas otras opciones, por ahora las que podrían ser importantes son:

    - **Repositorio público**: El repositorio es visible para cualquiera. Úsalo para proyectos que quieras compartir con mucha gente.
    - **Repositorio privado**: El repositorio es visible solo para ti y las personas que invites. Úsalo para proyectos privados, donde quieras proteger tu código.

- Después de crearlo, copia la dirección web (también llamada **URL**) que se parece a: `https://github.com/tu-nombre-de-usuario/nombre-de-tu-repositorio.git`.

![GitHub Link](imgs/github_link.png)

- Ahora abre la **Terminal** y escribe este comando para copiar el proyecto a tu computadora:

```bash
git clone [https://github.com/tu-nombre-de-usuario/nombre-de-tu-repositorio.git]
```

- Presiona Enter y Git descargará la carpeta del proyecto a tu computadora. 🎉