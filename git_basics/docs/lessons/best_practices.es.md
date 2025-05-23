# 🤝 Mejores Prácticas de Colaboración

Trabajar juntos en código puede ser súper divertido, y un poco complicado si recién estás comenzando. Aquí tienes algunos consejos sencillos para que la colaboración sea más fácil, limpia y menos estresante. 🚀

---

## 🧠 1. Habla antes de codificar

¡La comunicación es clave! Antes de sumergirte en el trabajo:

- Conversa con tu compañero o equipo sobre lo que cada uno va a hacer.
- Decidan quién hace qué para **no trabajar accidentalmente en el mismo archivo** al mismo tiempo.
- Usen aplicaciones de mensajería, un documento compartido o incluso hablen en persona si pueden. ☎️

---

## 🌱 2. Haz `pull` antes de hacer `push`

Antes de enviar tus cambios a GitHub, ejecuta esto en tu terminal:

→ **Ejecutar en la terminal:**

```bash
git pull
```

✅ Esto te ayuda a obtener los últimos cambios de tu equipo.

📛 **Si no haces `pull` primero, podrías causar un conflicto de fusión.**

---

## 🎯 3. Haz `commit` a menudo, con mensajes claros

Haz `commits` pequeños a medida que avanzas y escribe mensajes cortos y útiles como:

→ **Ejecutar en la terminal:**

```bash
git commit -m "Agregar función para calcular promedio"
```

❌ Evita mensajes como:

```bash
git commit -m "cosas"
git commit -m "lo arreglé"
```

✅ Los buenos mensajes ayudan a tus compañeros a entender lo que hiciste de un vistazo.

---

## 🧼 4. Limpia tu código antes de compartirlo

🧹 Antes de hacer `push` a GitHub:

- Elimina las sentencias `print()` (a menos que sean necesarias)
- Asegúrate de que tu código **se ejecute sin errores**
- Usa nombres de variables significativos (`precio_total`, no `x`)

¡Tus compañeros te lo agradecerán! 🙏

---

## 🧪 5. Revisa los cambios juntos

Antes de fusionar tu código:

- **Revisa tus cambios** para detectar errores.
- **Pide a tu compañero que revise** (usa las pull requests de GitHub si es posible).

👀 Dos pares de ojos > uno.

---

## 🔄 6. Resuelve los conflictos juntos

Si ocurre un **conflicto de fusión**:

- No entres en pánico 😅
- Abre el archivo y busca líneas como:

```bash
<<<<<<< HEAD
tus cambios
=======
sus cambios
>>>>>>> origin/main
```

- Habla con tu compañero sobre qué versión mantener.
- Edita el archivo para mantener la versión correcta.

Luego:

→ **Ejecutar en la terminal:**

```bash
git add .
git commit -m "Resolver conflicto en archivo.py"
git push
```

---

## 🎉 8. Celebra los logros

¿Terminaste una característica? ¿Arreglaste un error? ¿Resolviste un conflicto complicado?

🎉 Choca esos cinco con tu compañero, ¡remoto o en persona!
Las pequeñas victorias merecen reconocimiento. Mantiene el trabajo en equipo divertido. 🙌

---

## 🧭 9. Pide ayuda (y sé amable al darla)

Está totalmente bien hacer preguntas. Todos estamos aprendiendo. 💬

Y cuando alguien te pida ayuda, sé amable, paciente y alentador.

Todos empezamos en algún lugar. 🤗