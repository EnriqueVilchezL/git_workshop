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

→ Ejecuta en la terminal:

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

    → Ejecuta en la terminal:

    ```bash
    git status
    ```
    
    ¿Qué ves? Probablemente, tu salida se vea así:
    
    <span style="color:red">math_utils.py</span>

    Esto significa que el archivo no está `tracked` (rastreado). Es decir, hemos hecho algunos cambios en el archivo, pero no se incluirá en el próximo commit a menos que lo agregues con `git add`.
    
¡Intentemos agregarlo! Haz un `git add`, pero no veas la respuesta hasta que lo intentes:

??? example "Respuesta"

    → Ejecuta en la terminal:

    ```bash
    git add math_utils.py
    ```

¡Genial! Ahora, hemos agregado `math_utils.py`. Pero aún así, necesitamos hacer un commit. Intenta hacer un commit con el mensaje "Added summation function".

??? example "Respuesta"

    → Ejecuta en la terminal:

    ```bash
    git commit -m "Add summation function"
    ```

¡Excelente! Intenta revisar el repositorio de GitHub que acabas de crear.

Hmmm... No hay nada allí... ¿Nos falta algo?

??? example "Respuesta"

    ¡Correcto! Necesitamos hacer un `push` para enviar esos cambios al repositorio remoto.

    → Ejecuta en la terminal:

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

    → Ejecuta en la terminal:

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

→ Ejecuta en la terminal:

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

→ Ejecuta en la terminal:
```bash
git add math_utils.py
git commit -m "Resolve merge conflict and keep both functions"
git push
```

## ⏰ Paso 7: Socio A - Revisa la Función Original y Agrégala de Nuevo

¡Muy bien! Ahora vamos a hacer un pequeño viaje en el tiempo para ver la primera versión de nuestra función `summation` — la que escribiste antes de que tu compañero comenzara a hacer cambios. Esta es una excelente forma de comprobar si tu función original está correcta y no fue modificada accidentalmente.

### ¿Qué es exactamente lo que estamos haciendo aquí?

- Cuando usamos `git checkout <commit>`, **cambiamos temporalmente los archivos del proyecto para que se vean exactamente como estaban en ese commit específico** — como rebobinar una película a una escena anterior.  
- Esto no borra nada; solo nos permite **ver o copiar código del pasado** sin cambiar el estado actual.  
- Una vez que terminemos de revisar, volveremos a la versión más reciente en la rama main usando `git checkout main`.  
- Luego, añadiremos la función original al código actual, pero con un nombre nuevo para que no interfiera con los cambios de tu compañero.  

### Esto es lo que haremos, paso a paso:

1. Primero, actualiza tu copia local con los últimos cambios para que todo esté sincronizado. ¡No queremos más conflictos! ¿Recuerdas cómo hacerlo?

    ??? example "Respuesta"

        → Ejecuta en la terminal:

        ```bash
        git pull
        ```

2. **Encuentra el primer commit que hiciste** (eso es como la primera foto instantánea de tu proyecto):

    → Ejecuta en la terminal:
    ```bash
    git log --oneline
    ```

    Esto mostrará una lista de commits. Desplázate hasta el final para encontrar el más antiguo. Copia su código corto (parece una mezcla de letras y números, por ejemplo: `a1b2c3d`).

3. **Haz checkout a ese primer commit para ver cómo era tu código en ese momento:**

    → Ejecuta en la terminal:
    ```bash
    git checkout a1b2c3d
    ```

    ¡Esto nos hará viajar en el tiempo hasta ese commit!

    *(Reemplaza `a1b2c3d` con el código real que copiaste.)*

4. **Abre `math_utils.py` y busca tu función original `summation`.**

    Copia todo el código dentro de esta función — esta es tu versión original, sin modificar.

5. **¡Ahora, regresa al presente!**

    → Ejecuta en la terminal:
    ```bash
    git checkout main
    ```

6. **Abre `math_utils.py` otra vez.**  
    Pega la función original que copiaste, pero renómbrala como `summation_original` para mantenerla separada de la actual, así:

    ```python
    def summation_original(n):
        summation = 0
        for i in range(n + 1):
            summation += i
        return summation
    ```

7. **Guarda el archivo, luego haz add, commit y push de tus cambios:**  
    ¡Inténtalo, ya eres un experto en esto!

    ??? example "Respuesta"

        → Ejecuta en la terminal:

        ```bash
        git add math_utils.py
        git commit -m "Add original summation function as summation_original"
        git push
        ```

---

🎉 ¡Ahora tienes **ambas versiones** de la función en tu proyecto! Así puedes compararlas, probar cuál funciona mejor o simplemente conservar la original segura. ¡Gran trabajo viajando en el tiempo y aprendiendo a manejar el historial de tu proyecto como un pro!

---

# 🧪 Lección extra: Ejercicio Pareado de Git & GitHub en VSCode

Intenta recrear este tutorial invirtiendo roles. Pero ahora, usaremos la función integrada de Visual Studio Code para manejar el repositorio git. En vez de usar comandos bash, podemos usar VS Code para hacer todo lo que necesitemos.

Si necesitas ayuda, revisa la sección [VS Code Git](commands_vs_code.es.md). Si no puedes ejecutar algunos comandos en VS Code, usa la terminal.

---

## 💬 Consejos profesionales

- Ejecuta `git status` a menudo; es tu guía para saber lo que está pasando.
- Comunícate con tu compañero para evitar superposiciones y confusiones.
- Siempre haz `pull` antes de hacer `push` cuando trabajes en equipo.

¡Consulta la sección [Mejores Prácticas](best_practices.es.md) para convertirte en un Pro!

¡Feliz codificación!