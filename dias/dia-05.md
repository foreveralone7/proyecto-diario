# Día 05 · Podcast automático con voces de IA local

**Fecha:** 2026-11-23 · **Frente:** IA local + audio · **Stack:** Python, Kokoro-82M, NumPy, lameenc, mutagen
**Código:** https://github.com/foreveralone7/dia-05-podcast · **Demo:** https://foreveralone7.github.io/dia-05-podcast/

## 🛠️ Qué construí

Un programa que convierte un guion de texto con dos personajes (Dora y Alex) en un episodio de podcast en MP3, usando el modelo de voz local Kokoro. También genera el feed RSS y una página web con reproductor publicada en GitHub Pages. El primer episodio, "Cuatro días, cuatro lenguajes" (3:53 min), cuenta los días 1 a 4 del reto.

## 💡 Qué aprendí

- **Un modelo de IA puede correr en mi propio computador**, sin internet ni pagar una API. Generar el episodio completo (35 líneas) tomó unos 2 minutos.
- **Cómo es el audio digital por dentro:** un arreglo de números (24.000 por segundo). Unir audios es unir arreglos, y un silencio es un arreglo de ceros.
- **Normalizar y suavizar bordes** evita volúmenes disparejos y "clics" entre frases.
- **Las voces en español leen mal el inglés:** lo resolví con un diccionario de pronunciación (GitHub → "guit jab").
- **Un podcast es solo un archivo RSS** que apunta a MP3 públicos. Spotify y Apple Podcasts leen ese archivo.
- **Probar sin depender de la IA:** una voz simulada con la misma interfaz permite probar todo el flujo en segundos.

## 🐛 Problemas y cómo los resolví

**1. "No encontré Kokoro" después de instalar**
- *Qué pasó:* la instalación con `pip install -r requirements.txt` terminó con `ERROR: Operation cancelled by user`, así que Kokoro nunca quedó instalado.
- *Por qué:* Kokoro necesita PyTorch, que pesa varios cientos de MB. La instalación tarda varios minutos sin mostrar mucho avance, y se canceló a la mitad.
- *Solución:* volver a correr el `pip install` y no tocar la ventana hasta ver `Successfully installed`. Lo ya descargado quedó en caché, así que la segunda vez fue más rápido.
- *Lección:* en PowerShell, dar clic dentro de la ventana pausa el proceso, y `Ctrl + C` lo cancela.

**2. Aviso amarillo de `symlinks` de Hugging Face**
- La primera vez que Kokoro descargó el modelo, salió una advertencia sobre "symlinks" en Windows.
- No era un error: solo indica que Windows guarda el modelo de una forma que ocupa un poco más de espacio. El episodio se generó bien.

**3. Las tildes se veían raras en la consola (`c¾digo`, `dÝas`)**
- Era solo cómo la PowerShell clásica muestra los caracteres. El texto real y el audio estaban bien.
- La app **Terminal** de Windows sí muestra bien las tildes.

## 🔁 Qué haría distinto

Escuchar primero frases sueltas con `python podcast.py probar` para ajustar el diccionario de pronunciación, antes de generar el episodio completo.

## ⏱️ Tiempo invertido

1h 30
