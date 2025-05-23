# 🧪 Ejercicio en parejas de Git y GitHub: Funciones de Python y Control de Versiones

Este tutorial los guiará a ti y a un compañero a través de la colaboración en un proyecto de Python usando Git y GitHub. Practicarán la creación de un repositorio, su clonación, la escritura de código, la confirmación de cambios, el envío a GitHub y la resolución de un conflicto de fusión.

---

## 📁 Paso 0: Crear un repositorio de GitHub

El socio A debe:

1. Ir a https://github.com e iniciar sesión en su cuenta.
2. Hacer clic en el icono **+** en la parte superior derecha, luego elegir **New repository** (Nuevo repositorio).
3. Nombrar el repositorio: `python-functions-practice`
4. Opcionalmente, agregar una descripción.
5. **Dejar todas las casillas sin marcar** (sin README, sin .gitignore, sin licencia).
6. Hacer clic en **Create repository** (Crear repositorio).
7. Copiar la URL HTTPS que se muestra (la usarás para clonar).

---

## 👫 Paso 1: Invita a tu compañero al repositorio

Todavía el socio A:

1. Ir a la página del repositorio en GitHub.
2. Hacer clic en la pestaña **Settings** (Configuración).
3. Debajo de **Access** (Acceso), hacer clic en **Collaborators** (Colaboradores).
4. Hacer clic en **Invite a collaborator** (Invitar a un colaborador).
5. Escribir el nombre de usuario de GitHub de tu compañero y enviar la invitación.

El socio B debe aceptar la invitación antes de continuar.

---

## 💻 Paso 2: Clonar el repositorio

Ahora **ambos compañeros** deben ejecutar esto al mismo tiempo:

→ Ejecutar en la terminal:

```bash
git clone https://github.com/[tu-nombre-de-usuario]/python-functions-practice.git
cd python-functions-practice
```

---

## 🐍 Paso 3: Socio A - Crear un archivo Python

Socio A: crea un archivo llamado `math_utils.py`, y define una función que calcule la sumatoria de 1 a `n`. ¡Antes de mostrar la respuesta correcta, inténtalo!

??? example "Respuesta"

    ```python
    def summation(n):
        summation = 0
        for i in range(n + 1):
            summation += i
        return summation
    ```

Ahora que has creado tu archivo, veamos qué piensa Git que está sucediendo. Intenta ejecutar un `status` con Git. ¿Recuerdas cómo hacerlo?

??? example "Respuesta"

    → Ejecutar en la terminal:

    ```bash
    git status
    ```
    
    ¿Qué ves? Probablemente, tu salida se vea así:
    
    <span style="color:red">math_utils.py</span>

    Esto significa que el archivo no está `tracked` (rastreado). Es decir, hemos hecho algunos cambios en el archivo, pero no se incluirá en el próximo commit a menos que lo agregues con `git add`.
    
¡Intentemos agregarlo! Haz un `git add`, pero no veas la respuesta hasta que lo intentes:

??? example "Respuesta"

    → Ejecutar en la terminal:

    ```bash
    git add math_utils.py
    ```

¡Genial! Ahora, hemos agregado `math_utils.py`. Pero aún así, necesitamos hacer un commit. Intenta hacer un commit con el mensaje "Added summation function".

??? example "Respuesta"

    → Ejecutar en la terminal:

    ```bash
    git commit -m "Add summation function"
    ```

¡Excelente! Intenta revisar el repositorio de GitHub que acabas de crear.

Hmmm... No hay nada allí... ¿Nos falta algo?

??? example "Respuesta"

    ¡Correcto! Necesitamos hacer un `push` para enviar esos cambios al repositorio remoto.

    → Ejecutar en la terminal:

    ```bash
    git push
    ```

    Intenta revisar tu repositorio de GitHub para verificar que el archivo esté allí.

---

## 👥 Paso 4: Socio B - Agregar una nueva función

Socio B: crea un archivo llamado `math_utils.py`, y define una función que calcule la sumatoria de 1 a `n`. Tiene que ser una implementación diferente. ¡Antes de mostrar la respuesta correcta, inténtalo!

??? example "Respuesta"

    ```python
    def summation(n):
        return sum(range(1, n + 1))
    ```

¡Bien! Ahora, intenta hacer lo mismo que tu compañero. Intenta enviar los cambios al repositorio remoto.

??? example "Respuesta"

    → Ejecutar en la terminal:

    ```bash
    git add math_utils.py
    git commit -m "Added a mean function"
    git push
    ```

Ups... Algo salió mal... ¿Qué es?

??? example "Respuesta"

    El socio B hizo un cambio en un archivo que ya estaba creado, pero el archivo remoto tiene algunos cambios que el socio B no tiene en su máquina local.

    Esto se conoce como un `conflict`. Sucede cuando haces cambios localmente pero no has "pulled" los cambios que otras personas hicieron en el repositorio remoto.

---

## 🚨 Paso 5: Espera un conflicto de fusión

Socio B: es probable que veas algo como

<span style="color:red">! [rejected] main -> main (fetch first)</span>

Esto significa que alguien más (Socio A) ya envió cambios.

→ Ejecutar en la terminal:

```bash
git pull --no-rebase
```

Verás un conflicto de fusión en `math_utils.py`.

---

## 🛠️ Paso 6: Resolver el conflicto de fusión

Abre `math_utils.py`. Verás algo como:

```python
<<<<<<< HEAD
def summation(n):
    return sum(range(1, n + 1))
=======
def summation(n):
    summation = 0
    for i in range(n + 1):
        summation += i
    return summation
>>>>>>> main
```

En la parte superior, verás algunas opciones, como `Accept Current Change` | `Accept Incoming Change` | `Accept Both Changes` | `Compare Changes`.

Estas son algunas alternativas que puedes elegir para resolver el conflicto. Significan:

- Accept Current Change
→ Mantiene tus cambios locales y descarta los remotos.

- Accept Incoming Change
→ Mantiene los cambios del repositorio remoto y descarta tus ediciones locales.

- Accept Both Changes
→ Incluye tanto tus cambios como los cambios remotos, apilados uno tras otro.
⚠️ A menudo necesitarás editar manualmente después para que el resultado tenga sentido.

- Compare Changes
→ Muestra una vista de diferencias lado a lado para ayudarte a decidir qué cambios mantener.

Intentemos aceptar ambos cambios. Si el archivo hizo algo extraño, intenta cambiarlo para que se vea así:

```python
def summation(n):
    return sum(range(1, n + 1))

def summation_2(n):
    summation = 0
    for i in range(n + 1):
        summation += i
    return summation
```

Luego ejecuta:

→ Ejecutar en la terminal:
```bash
git add math_utils.py
git commit -m "Resolve merge conflict and keep both functions"
git push
```

---

# 🧪 Lección extra: Ejercicio en parejas de Git y GitHub en VSCode

Intenta recrear el tutorial invirtiendo tus roles. Pero ahora, intentaremos usar la función incorporada de Visual Studio Code para gestionar el repositorio Git. En lugar de usar comandos de Git en Bash, podemos usar VS Code para hacer todo lo que necesitamos.

Si necesitas ayuda, consulta la sección de [Git en VS Code](commands_vs_code.es.md).

---

## 💬 Consejos profesionales

- Ejecuta `git status` a menudo; es tu guía para saber lo que está pasando.
- Comunícate con tu compañero para evitar superposiciones y confusiones.
- Siempre haz `pull` antes de hacer `push` cuando trabajes en equipo.

¡Feliz codificación!