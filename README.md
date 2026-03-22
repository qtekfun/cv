# cv

> CV generado automáticamente como PDF desde Markdown, via Pandoc + WeasyPrint + GitHub Actions.

## Estructura

```
.
├── cv.md                          # Fuente del CV (edita esto)
├── style.css                      # Estilos dark/developer para HTML y PDF
└── .github/
    └── workflows/
        └── build-cv.yml           # Pipeline de build automático
```

## Cómo funciona

1. Editas `cv.md` y haces push a `master`
2. GitHub Actions ejecuta el workflow:
   - Instala Pandoc + WeasyPrint
   - Convierte `cv.md` → `cv.html` (con `style.css` embebido)
   - Convierte `cv.html` → `cv.pdf` via WeasyPrint
3. El PDF se sube como **artifact** (disponible 30 días) y como **Release `latest`**

## Build local

```bash
# Instalar dependencias (Ubuntu/Debian/Fedora)
sudo apt install pandoc weasyprint          # Debian/Ubuntu
sudo dnf install pandoc python3-weasyprint  # Fedora

# Generar HTML
pandoc cv.md --standalone --css style.css --to html5 -o cv.html

# Generar PDF
weasyprint cv.html cv.pdf
```

## Personalización

- **Contenido:** edita `cv.md` — usa `code inline` para fechas/tags, tablas para skills.
- **Colores:** cambia `--accent` en `style.css` (actualmente `#00b4d8`).
- **Fuentes:** ajusta `--font-mono` y `--font-body` en `:root`.
- **Print:** el bloque `@media print` en `style.css` convierte el tema dark a blanco para impresión física.
