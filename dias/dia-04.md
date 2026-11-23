# Día 04 · Juego de la serpiente en Java

**Fecha:** 2026-11-22 · **Frente:** Videojuegos / escritorio · **Stack:** Java 21, Swing
**Código:** https://github.com/foreveralone7/dia-04-serpiente

## 🛠️ Qué construí

El clásico juego de la serpiente con ventana gráfica: niveles que aumentan la velocidad, récord guardado en un archivo, pausa, reinicio y 12 pruebas automáticas de las reglas.

## 💡 Qué aprendí

- **Programación orientada a objetos de verdad:** cada clase tiene una sola responsabilidad (`Juego` = reglas, `Serpiente` = cuerpo, `PanelJuego` = dibujo).
- **Separar modelo y vista:** las reglas no saben nada de la ventana, y por eso se pueden probar sin abrir el juego.
- **El bucle de un juego:** un `Timer` que cada X milisegundos avanza el estado y redibuja la pantalla.
- **`record` y `enum` con métodos:** Java moderno es mucho menos repetitivo que el Java de antes.
- **Detalles que no se ven pero importan:** guardar las teclas en una cola para que dos giros rápidos no se pierdan, y permitir que la cabeza entre a la celda que la cola está dejando libre.
- **Compilar vs ejecutar:** `javac` convierte el código en `.class` y `java` lo ejecuta. Un `.jar` empaqueta todo en un solo archivo.

## 🧪 Experimento descartado: IA modelando en Blender

Antes de este proyecto probé que una IA modelara un objeto en Blender a partir de una imagen (Cursor + Blender MCP).

- **Qué esperaba:** subir una foto y obtener un modelo 3D parecido.
- **Qué obtuve:** _(completar: qué hizo la IA y cómo quedó)_
- **Conclusión:** los videos de redes muestran los mejores intentos. La IA controlando Blender sirve para figuras simples o low-poly, no para copiar un objeto real. Para eso existen modelos especializados de imagen a 3D (Hunyuan3D, TRELLIS), que funcionan distinto.

## 🐛 Problemas y cómo los resolví

_(completar con lo que pase al instalar Java y probar)_

## 🔁 Qué haría distinto

## ⏱️ Tiempo invertido

_(completar)_
