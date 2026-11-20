# Día 02 · API de destinos turísticos de Colombia

**Fecha:** 2026-11-20 · **Frente:** Backend · **Stack:** Python, FastAPI, Pydantic, pytest
**Código:** https://github.com/foreveralone7/dia-02-api-destinos

## 🛠️ Qué construí

Una API REST para consultar y administrar destinos turísticos de Colombia: CRUD completo, filtros combinables (departamento, clima, categoría, calificación y búsqueda), estadísticas por departamento, documentación interactiva con Swagger y 13 pruebas automáticas.

## 💡 Qué aprendí

- **Qué es un backend:** en el día 1 mi página consumía la API de Open-Meteo. Hoy construí el otro lado: el programa que recibe las peticiones y responde con JSON.
- **Métodos HTTP:** GET (consultar), POST (crear), PUT (reemplazar), PATCH (editar una parte) y DELETE (borrar).
- **Códigos de estado:** 200 (bien), 201 (creado), 204 (borrado, sin contenido), 404 (no existe), 409 (conflicto, nombre repetido) y 422 (datos inválidos).
- **Validación con Pydantic:** con solo declarar `calificacion: float = Field(ge=0, le=5)`, la API rechaza sola una calificación de 7.
- **Separación en capas:** rutas (`main.py`) → repositorio (`repositorio.py`) → modelos (`models.py`). Para usar una base de datos más adelante, solo se cambia el repositorio.
- **Pruebas automáticas con pytest:** cada prueba usa datos limpios para que no se afecten entre sí.
- **Swagger:** FastAPI genera sola una página (`/docs`) donde cualquiera puede probar la API desde el navegador.

## 🐛 Problemas y cómo los resolví

**1. ¿Qué es eso del `venv`?**
- Un **entorno virtual** es una carpeta con una copia de Python y las librerías de *ese* proyecto, para que no se mezclen con las de otros proyectos.
- Se crea con `python -m venv venv` y se activa con `.\venv\Scripts\Activate.ps1`. Cuando está activo aparece `(venv)` al inicio de la línea.
- **No se sube a GitHub** (por eso está en `.gitignore`): pesa mucho y cualquiera puede recrearlo con `pip install -r requirements.txt`.

**2. `Move-Item` falló al mover el proyecto de `C:` a `L:`**
- *Qué pasó:* error `MoveDirectoryItemIOError` al mover la carpeta desde Descargas (`C:`) a mi carpeta de estudio (`L:`).
- *Por qué:* `Move-Item` de PowerShell no mueve carpetas entre discos distintos.
- *Solución:* moverla con el Explorador de Windows (cortar y pegar), o usar `Copy-Item -Recurse` y luego borrar la original.

**3. El entorno virtual no funciona si se mueve de lugar**
- El `venv` guarda rutas absolutas por dentro. Al cambiar el proyecto de carpeta hay que borrar `venv` y crearlo de nuevo.

**4. Dos comandos pegados en una sola línea**
- `cd "...destinos"python -m venv venv` falló porque PowerShell lo leyó como un solo comando con argumentos raros.
- *Lección:* un comando por línea y Enter después de cada uno. Cuando algo falla, revisar en qué carpeta estoy (lo dice el prompt: `PS L:\...>`).

**5. La API ocupa la terminal**
- Mientras `uvicorn` está corriendo, esa terminal no recibe más comandos. Se apaga con `Ctrl + C`, o se abre otra terminal para trabajar con Git.

## 🔁 Qué haría distinto

Descomprimir los proyectos directamente en `L:\Estudio 365\` desde el principio, en vez de trabajar en Descargas y moverlos después.

## ⏱️ Tiempo invertido

Día 2: de 9:45 a. m. a 10:25 a. m., cerca de 1 hora
