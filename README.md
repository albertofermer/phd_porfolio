# Portfolio Académico - Doctorado en Computación Avanzada, Energía y Plasmas

Este repositorio contiene el código fuente de mi sitio web académico/divulgativo, construido con [Quarto](https://quarto.org/).

## Propósito

Espacio para documentar y compartir mi investigación doctoral de forma accesible, incluyendo:

- Líneas de investigación
- Diario de investigación
- Notebooks interactivos
- Publicaciones y recursos

## Tecnologías

- **Quarto**: Sistema de publicación científica y técnica
- **Markdown/QMD**: Formato de contenido
- **Jupyter Notebooks**: Análisis y visualizaciones interactivas
- **GitHub Pages**: Hosting del sitio estático

## Estructura del proyecto

```
.
├── _quarto.yml           # Configuración principal de Quarto
├── index.qmd             # Página principal
├── about.qmd             # Sobre mí
├── styles.css            # Estilos personalizados
├── custom.scss           # Variables de tema
├── research/             # Páginas de investigación
│   └── linea-1.qmd       # Ejemplo de línea de investigación
├── log/                  # Diario de investigación
│   ├── index.qmd         # Índice del diario
│   └── 2025-01-avances.qmd
├── notebooks/            # Jupyter notebooks
│   └── ejemplo-descomposicion.ipynb
└── _site/                # Sitio generado (ignorado en git)
```

## Cómo usar este proyecto

### Prerequisitos

1. Instalar [Quarto](https://quarto.org/docs/get-started/)
2. Tener Python instalado (para ejecutar notebooks)

### Instalación

```bash
# Clonar el repositorio
git clone https://github.com/tu-usuario/phd-portfolio.git
cd phd-portfolio

# Instalar dependencias de Python (opcional, para notebooks)
pip install numpy pandas matplotlib seaborn statsmodels
```

### Previsualizar el sitio localmente

```bash
quarto preview
```

Esto abrirá el sitio en `http://localhost:XXXX` con recarga automática al editar archivos.

### Generar el sitio estático

```bash
quarto render
```

El sitio generado estará en la carpeta `_site/`.

## Cómo agregar contenido

### Nueva entrada de diario

1. Crear archivo en `log/YYYY-MM-titulo.qmd`
2. Incluir metadatos YAML:
   ```yaml
   ---
   title: "Título de la entrada"
   description: "Breve descripción"
   date: "2025-01-XX"
   categories: [categoría1, categoría2]
   ---
   ```
3. La entrada aparecerá automáticamente en el índice del diario

### Nueva línea de investigación

1. Crear archivo en `research/nombre-linea.qmd`
2. Agregar al menú de navegación en `_quarto.yml`:
   ```yaml
   - text: "Nombre de la línea"
     href: research/nombre-linea.qmd
   ```

### Nuevo notebook

1. Crear notebook en `notebooks/nombre.ipynb`
2. Enlazar desde páginas `.qmd` con:
   ```markdown
   [Ver notebook →](notebooks/nombre.ipynb)
   ```

## Despliegue en GitHub Pages

### Configuración inicial

1. En `_quarto.yml`, configurar la URL base:
   ```yaml
   website:
     repo-url: https://github.com/albertofermer/phd_porfolio
   ```

2. Crear GitHub Action (archivo `.github/workflows/publish.yml`):
   ```yaml
   name: Publish Quarto Site
   
   on:
     push:
       branches: main
   
   jobs:
     build-deploy:
       runs-on: ubuntu-latest
       permissions:
         contents: write
       steps:
         - uses: actions/checkout@v4
         
         - uses: quarto-dev/quarto-actions/setup@v2
         
         - name: Render Quarto Project
           run: quarto render
           
         - name: Deploy to GitHub Pages
           uses: peaceiris/actions-gh-pages@v3
           with:
             github_token: ${{ secrets.GITHUB_TOKEN }}
             publish_dir: ./_site
   ```

3. En la configuración del repositorio de GitHub:
   - Ir a Settings > Pages
   - Source: Deploy from a branch
   - Branch: `gh-pages` / `root`

### Actualizar el sitio

Simplemente hacer push a la rama `main`:

```bash
git add .
git commit -m "Actualizar contenido"
git push origin main
```

GitHub Actions generará y publicará automáticamente el sitio.

## Separación contenido público/privado

Este repositorio contiene **solo contenido público y divulgativo**.

Para trabajo privado (código experimental, datos sensibles, borradores):

1. Crear repositorio privado separado (ej: `phd-private`)
2. Usar submodules si es necesario compartir código entre ambos
3. Nunca hacer commit de datos confidenciales aquí

## Licencia

- **Contenido** (textos, imágenes): [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)
- **Código**: MIT License

El código de análisis específico puede tener licencias diferentes (ver repositorios individuales).

## Contacto

Para preguntas o colaboraciones: alberto.fernmer@gmail.com

---

*Portfolio académico personal. Universidad de Córdoba, 2025.*
