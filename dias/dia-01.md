# Día 01 · Dashboard del clima en Colombia

**Fecha:** 2026-11-19 · **Frente:** Frontend · **Stack:** HTML, CSS, JavaScript, Chart.js, API de Open-Meteo
**Código:** https://github.com/foreveralone7/dia-01-clima · **Demo:** https://foreveralone7.github.io/dia-01-clima/

## 🛠️ Qué construí

Un dashboard web que muestra el clima actual, una gráfica de las próximas 24 horas y el pronóstico de 7 días de cualquier municipio de Colombia. Incluye buscador, geolocalización y modo claro/oscuro.

## 💡 Qué aprendí

- **Qué es consumir una API:** mi página le pide los datos a Open-Meteo con una URL y recibe una respuesta en JSON.
- **`fetch` con `async/await`**, y cómo manejar los estados de carga y de error para que la página no se quede en blanco si algo falla.
- **Debounce:** esperar a que el usuario deje de escribir antes de buscar, para no hacer una petición por cada letra.
- **Variables CSS** para cambiar entre tema claro y oscuro sin duplicar estilos.
- **El flujo de Git:** `init`, `add`, `commit`, `remote`, `push`, y publicar una página gratis con GitHub Pages.

## 🐛 Problemas y cómo los resolví

**1. El login de GitHub fallaba con `ERR_CONNECTION_REFUSED` en `127.0.0.1`**
- *Qué pasó:* al hacer `git push`, Git abría el navegador para iniciar sesión, pero la página de retorno (`127.0.0.1:puerto`) no cargaba y la terminal se quedaba esperando.
- *Por qué:* Git abre un servidor temporal en el computador para recibir la confirmación de GitHub. Si se cierra o algo lo bloquea, la respuesta no llega.
- *Solución:* crear un **Personal Access Token (classic)** con permiso `repo` y configurar Git para usarlo:
  `git config --global credential.gitHubAuthModes pat`

**2. Los archivos quedaron dentro de una subcarpeta en el commit**
- *Qué pasó:* el commit mostraba `dia-01-clima/index.html` en vez de `index.html`. Al descomprimir el zip quedó una carpeta dentro de otra con el mismo nombre.
- *Por qué importa:* GitHub Pages busca el `index.html` en la raíz del repo.
- *Solución:* antes de subir, mover los archivos un nivel arriba y rehacer el commit:
  ```powershell
  Move-Item .\dia-01-clima\* .
  Remove-Item .\dia-01-clima
  git add -A
  git commit --amend -m "mensaje"
  ```
- *Lección:* revisar la lista de archivos que muestra el commit antes de hacer `push`.

**3. No encontraba la opción "Branch" de GitHub Pages**
- *Qué pasó:* estaba en los **Settings de mi cuenta**, no en los del repositorio.
- *Solución:* los Settings del repo están en la pestaña ⚙️ dentro del repo (`github.com/usuario/repo/settings/pages`).

**4. Advertencias `LF will be replaced by CRLF`**
- No era un error. Windows y Linux marcan los saltos de línea de forma distinta y Git solo avisa que los ajusta.

## 🔁 Qué haría distinto

Revisar con `git status` qué archivos se van a subir antes de hacer el commit.

## ⏱️ Tiempo invertido

Día 1: de 7:45 p. m. a 10:20 p. m., unas 2 horas y media
