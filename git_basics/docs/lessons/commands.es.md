# Comandos básicos de Git que necesitas saber

Comprender Git puede ser más fácil si lo imaginas como enviar paquetes (tus archivos) a una bóveda segura en otro país; esa bóveda es GitHub. Al igual que al enviar un paquete por correo, hay pasos que debes seguir para preparar, organizar y enviar tus archivos de forma segura. Git es la herramienta que te ayuda a gestionar cada parte de este proceso.

## `git init`

Este comando inicializa un nuevo repositorio Git en la carpeta de tu proyecto. Úsalo cuando estés comenzando un nuevo proyecto y quieras rastrear sus cambios con Git.

```bash
git init
```

### 📦 Analogía

Piensa en esto como conseguir unas cajas vacías nuevas donde colocarás los artículos (archivos) que planeas enviar.

![Boxes](imgs/empty_boxes.png)

---

## `git add`

Este comando le dice a Git qué archivos quieres incluir en la próxima instantánea (commit).

Para agregar todos los archivos:

```bash
git add .
```

Para agregar un archivo específico:

```bash
git add [archivo_especifico.txt]
```

### 📦 Analogía

Esto es como colocar artículos dentro de tu caja. Por ejemplo:

```bash
git add taza.txt
```

Estás poniendo una taza dentro de la caja.

![Boxes](imgs/box_with_mug.png)

---

## `git commit`

Este comando guarda los cambios que has agregado, junto con un mensaje que describe lo que hiciste.

```bash
git commit -m "Un mensaje que explica el commit"
```

### 📦 Analogía

Esto es como sellar tu caja con cinta y etiquetarla. Por ejemplo:

```bash
git commit -m "Esta es una taza, es muy frágil"
```

Estás sellando la caja y escribiendo en ella: "Esta es una taza, es muy frágil".

![Sealed Box](imgs/sealed_box.png)

---

## `git status`

Este comando muestra el estado actual de tu proyecto: qué archivos han cambiado, cuáles están preparados para el commit y más.

```bash
git status
```

### 📦 Analogía

Esto es como revisar lo que hay dentro de la caja. Puedes ver si está abierta, qué se ha añadido y qué aún necesita ser sellado. Si la caja aún no está sellada, puedes ver lo que hay dentro, pero si está sellada, este comando te otorga una genial visión de rayos X para ver lo que hay dentro.

![X ray Vision for box](imgs/x_ray.png)

---

## `git log`

Este comando muestra un historial de todos tus commits: los mensajes que escribiste y cuándo hiciste los cambios.

```bash
git log
```

### 📦 Analogía

Esto es como hojear tu libro de registro de envíos. En él se enumeran todas las cajas que has enviado, cuándo las enviaste y qué etiquetas (mensajes) escribiste en cada una.

![List](imgs/shipping_list.png)

## `git push`

Este comando envía tus cambios confirmados a un repositorio remoto como GitHub.

```bash
git push origin main
```

### 📦 Analogía

Esto es como entregar tu caja sellada y etiquetada a la empresa de transporte. Finalmente la estás enviando a la bóveda segura (GitHub) en otro país. Hasta que no hagas `push`, la caja sigue en tu casa, preparada, pero no entregada.

![Truck with boxes](imgs/truck.png)

Para ver estos comandos en VS Code, consulta la [sección de Git en VS Code](commands_vs_code.es.md).