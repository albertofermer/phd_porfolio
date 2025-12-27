# Guía de Inicio Rápido

## Primeros pasos con tu portfolio académico

### 1. Previsualizar el sitio

```powershell
# Abrir terminal en la carpeta del proyecto y ejecutar:
quarto preview
```

Esto abrirá el sitio en tu navegador con recarga automática.

### 2. Personalizar el contenido

#### Información personal (about.qmd)

- Actualizar foto de perfil (descomenta y agrega imagen)
- Modificar formación académica
- Agregar enlaces a tus perfiles reales

#### Configuración del sitio (_quarto.yml)

- Cambiar título del sitio
- Actualizar URL del repositorio
- Ajustar colores en `custom.scss`

### 3. Agregar tu primera entrada de diario

Crea un nuevo archivo en `log/` con este formato:

```markdown
---
title: "Mi primera entrada"
description: "Descripción breve"
date: "2025-XX-XX"
categories: [categoría]
---

## Contenido

Tu texto aquí...
```

### 4. Publicar en GitHub

```powershell
# Inicializar git (si no lo hiciste)
git init
git add .
git commit -m "Initial commit"

# Conectar con GitHub
git remote add origin https://github.com/tu-usuario/phd-portfolio.git
git push -u origin main
```

El sitio se publicará automáticamente en GitHub Pages.

## Comandos útiles

```powershell
# Previsualizar
quarto preview

# Generar sitio estático
quarto render

# Verificar configuración
quarto check

# Ver ayuda
quarto --help
```

## Próximos pasos

1. ✅ Personalizar información en `about.qmd`
2. ✅ Ajustar colores y estilos
3. ✅ Escribir primera entrada de diario
4. ✅ Agregar tu contenido de investigación
5. ✅ Configurar GitHub Pages

---

Para más detalles, consulta el [README.md](README.md) completo.
