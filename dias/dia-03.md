# Día 03 · Organizador de archivos en Rust

**Fecha:** 2026-11-21 · **Frente:** Herramientas de terminal (CLI) · **Stack:** Rust, clap
**Código:** https://github.com/foreveralone7/dia-03-organizador

## 🛠️ Qué construí

Una herramienta de línea de comandos que ordena los archivos sueltos de una carpeta en subcarpetas por tipo. Tiene modo simulación, lista detallada y opción para deshacer, y nunca sobrescribe archivos.

## 💡 Qué aprendí

- **Rust es un lenguaje compilado:** el resultado es un `.exe` que corre sin tener Rust instalado.
- **`Result` y el operador `?`:** Rust obliga a decidir qué hacer con cada posible error (un archivo en uso, una carpeta que no existe). No hay excepciones escondidas.
- **`enum` + `match`:** el compilador avisa si olvido un caso.
- **Dueño vs préstamo:** `PathBuf` es una ruta que me pertenece y `&Path` una que solo estoy mirando.
- **Planear antes de ejecutar:** separar el plan de la acción hace que el modo simulación sea seguro.
- **Cargo:** crea el proyecto, descarga librerías, compila y corre las pruebas con un solo comando.

## 🐛 Problemas y cómo los resolví

La instalación de Rust pidió las Visual Studio C++ Build Tools, que Rust necesita para compilar en Windows

## 🔁 Qué haría distinto

## ⏱️ Tiempo invertido

2h aprox
