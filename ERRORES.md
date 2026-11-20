# 🐛 Errores resueltos

Todos los problemas que me he encontrado en el reto, con su causa y su solución. Si vuelve a pasar, la respuesta está aquí.

| Error o síntoma | Causa | Solución | Día |
|---|---|---|---|
| `ERR_CONNECTION_REFUSED` en `127.0.0.1:puerto` al hacer `git push` | El servidor temporal de Git para recibir el login de GitHub se cerró o fue bloqueado | Usar un Personal Access Token: `git config --global credential.gitHubAuthModes pat` | 01 |
| `git push` se queda en `please complete authentication in your browser...` | Igual que el anterior: el navegador no logra devolver la respuesta | `Ctrl + C` y usar token | 01 |
| El commit muestra `carpeta/archivo` en vez de `archivo` | Al descomprimir el zip quedó una carpeta dentro de otra | Mover los archivos un nivel arriba y hacer `git commit --amend` | 01 |
| `LF will be replaced by CRLF` | Diferencia de saltos de línea entre Windows y Linux | Nada: es solo un aviso | 01 |
| No aparece la opción "Branch" en GitHub Pages | Estaba en los Settings de la cuenta, no del repositorio | Ir a `github.com/usuario/repo/settings/pages` | 01 |
| Repo vacío ("Quick setup") después de hacer push | El `git push` nunca terminó | Revisar la terminal; la salida correcta termina en `main -> main` | 01 |
| `MoveDirectoryItemIOError` con `Move-Item` | `Move-Item` no mueve carpetas entre discos (`C:` → `L:`) | Usar el Explorador de Windows o `Copy-Item -Recurse` | 02 |
| `.\venv\Scripts\Activate.ps1 no se reconoce` | No estaba dentro de la carpeta del proyecto | `cd` a la carpeta correcta; el prompt muestra dónde estoy | 02 |
| `Could not open requirements file` | Igual: estaba en la carpeta equivocada | `cd` a la carpeta del proyecto y verificar con `ls` | 02 |
| `No se encuentra ningún parámetro de posición...` | Dos comandos pegados en una línea | Un comando por línea | 02 |
| El `venv` deja de funcionar al mover el proyecto | El entorno virtual guarda rutas absolutas | Borrar `venv` y crearlo de nuevo | 02 |
| `[notice] A new release of pip is available` | Hay una versión nueva de pip | Opcional: `python -m pip install --upgrade pip` | 02 |
