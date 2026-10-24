# Aprende R paso a paso

Sitio de tutoriales interactivos de R. Los estudiantes escriben y ejecutan
código directamente en el navegador (gracias a webR) y reciben
retroalimentación automática en cada ejercicio. No necesitan instalar R.

## Estructura

```
tutorial-r/
├── _quarto.yml                  Configuración del sitio (menú, tema, opciones)
├── index.qmd                    Página de inicio
├── lecciones/
│   ├── 01-primeros-pasos.qmd    Lección 1 completa (6 ejercicios calificados)
│   └── _plantilla-leccion.qmd   Plantilla comentada para nuevas lecciones
├── estilos/                     Colores, tipografía y traducción de botones
├── _extensions/r-wasm/live/     Extensión quarto-live (no modificar)
└── docs/                        Sitio ya compilado, listo para publicar
```

## Requisitos (solo en tu computadora)

- [Quarto](https://quarto.org/docs/get-started/) 1.4 o superior.
- R con los paquetes `knitr` y `rmarkdown`:
  `install.packages(c("knitr", "rmarkdown"))`

## Trabajar en el sitio

Desde la carpeta del proyecto, en una terminal:

```bash
quarto preview     # abre el sitio y lo actualiza al guardar cambios
quarto render      # genera la versión final en la carpeta docs/
```

Para crear una lección nueva, copia `lecciones/_plantilla-leccion.qmd`,
renómbrala (por ejemplo `02-data-frames.qmd`) y agrégala a la sección
`Lecciones` de `_quarto.yml`.

## Publicar gratis en GitHub Pages

1. Crea un repositorio en GitHub y sube todo el contenido de esta carpeta.
2. En el repositorio ve a **Settings → Pages**.
3. En *Build and deployment* elige **Deploy from a branch**, rama `main`,
   carpeta `/docs`, y guarda.
4. En uno o dos minutos el sitio estará en
   `https://TU-USUARIO.github.io/NOMBRE-DEL-REPOSITORIO/`.

Cada vez que modifiques algo: `quarto render`, y luego sube los cambios
(incluida la carpeta `docs/`).

## Opciones útiles en `_quarto.yml`

- `show-solutions: false` oculta el botón de solución (útil para evaluaciones).
- `show-hints: false` oculta las pistas.

## Notas

- La primera carga de cada lección tarda unos segundos mientras R se
  descarga en el navegador.
- Los paquetes se declaran por lección en el encabezado (`webr: packages:`).
  La mayoría de los paquetes de CRAN están disponibles para webR.
- Los archivos de datos (CSV) se declaran con `resources:` en el
  encabezado de la lección (ver la plantilla).
- El sitio no guarda calificaciones de los estudiantes: la
  retroalimentación es inmediata pero privada para cada estudiante.
- Las cifras de población de la lección 1 provienen del Censo de
  Población y Vivienda 2020 (INEGI); conviene verificarlas antes de usarlas.
