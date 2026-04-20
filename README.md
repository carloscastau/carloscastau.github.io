# Carlos Castaño - Portafolio

Portafolio web estático, minimalista y de alto rendimiento para **Carlos Castaño**, Machine Learning Engineer & Data Science Leader.

**Tech Stack**: Astro SSR, HTML con estilos inline, GitHub Pages

## 🚀 Inicio Rápido

### Requisitos
- Node.js >= 22.12.0
- npm >= 9.6.5

### Instalación y desarrollo

```bash
# Instalar dependencias
npm install

# Servidor de desarrollo con live-reload
npm run dev

# Build de producción
npm run build

# Vista previa local del build
npm run preview
```

### Despliegue automático (GitHub Pages)

El proyecto incluye GitHub Actions para despliegue automático en cada push a `main`:

1. Los archivos generados en `dist/` se publican en GitHub Pages.
2. El sitio estará disponible en https://carloscastau.github.io (o el dominio configurado en CNAME).

#### Cómo funciona el deploy

- **Sin Jekyll**: El archivo `.nojekyll` desactiva Jekyll para evitar errores con archivos `.astro`
- **Build**: GitHub Actions ejecut `npm run build` para generar archivos estáticos en `dist/`
- **Despliegue**: Usa `actions/deploy-pages@v4` para subir a GitHub Pages

#### Configuración de GitHub Pages

En Settings > Pages del repositorio:
- **Source**: Deploy from a branch (o GitHub Actions)
- **Branch**: `gh-pages` / (root) si se usa branch

No hacer push directo a `gh-pages` - el workflow lo maneja automáticamente.

#### Deploy manual (alternativo)

```bash
npm run deploy
```

## 📁 Estructura del Proyecto

```text
/
├── src/
│   ├── pages/
│   │   └── index.astro      # Landing principal (HTML con estilos inline)
│   └── assets/              # CV en PDF
├── public/                  # Favicon, robots.txt, CNAME
├── .github/workflows/      # GitHub Actions (deploy.yml)
├── astro.config.mjs        # Configuración de Astro
├── tailwind.config.mjs     # Configuración de Tailwind
├── postcss.config.mjs      # Configuración de PostCSS
└── package.json
```

## 🎯 Añadir o Modificar Contenido

### Modificar información personal

Edita directamente `src/pages/index.astro`. Busca las secciones:

- **Hero**: Nombre, título, subtitle, badges de habilidades (líneas 84-102)
- **About**: Bio y grupos de habilidades (líneas 106-173)
- **Projects**: Tarjetas de proyecto (líneas 182-243)
- **Contact**: Enlaces (líneas 256-259)
- **Footer**: Enlace a GitHub (líneas 270-273)

### Añadir un nuevo proyecto

En `src/pages/index.astro`, en la sección "Projects", duplica un bloque de proyecto existente y modifica título, descripción, tags y enlaces.

### Actualizar el CV

Reemplaza el archivo `src/assets/cv-carlos-castano.pdf` con tu CV actual.

## 🎨 Personalización

| Elemento | Archivo |
|----------|---------|
| Colores primarios | Buscar `text-primary-600` y `bg-primary-600` en index.astro |
| Tipografía | Modificar `font-family` en el `<style>` del `<head>` |
| Enlaces sociales | Secciones Contact y Footer |
| Dominio | Editar `public/CNAME` |
| Favicon | Reemplazar `public/favicon.svg` |

## 📊 Performance & SEO

- **Lighthouse score target**: >95 (móvil y desktop)
- **SEO**: Metatags Open Graph y Twitter configurados
- **Sitemap**: Generado automáticamente en `sitemap-index.xml`
- **Compresión**: Gzip en producción

## 🛠️ Solución de Problemas

### Build falla con "BaseLayout is not defined"
Este proyecto usa HTML plano en `index.astro`. Si ves este error, asegúrate de que `index.astro` tenga el frontmatter `---` vacío y luego HTML completo.

### GitHub Pages no refleja cambios
Verifica que el workflow se ejecute y que los archivos estén en rama `main`.

## 📝 Notas Técnicas

- **Enfoque**: HTML plano con mínima lógica Astro. Esto garantiza máxima compatibilidad.
- **Responsive**: Mobile-first con media queries.
- **Accesibilidad**: Navegación con anclas, ARIA labels en iconos SVG.

## 📦 Scripts Disponibles

| Script | Descripción |
|--------|-------------|
| `npm run dev` | Servidor de desarrollo |
| `npm run build` | Genera sitio estático en `dist/` |
| `npm run preview` | Previsualiza el build localmente |
| `npm run deploy` | Build + deploy a GitHub Pages |

## 🤝 Contacto

- GitHub: [carloscastau](https://github.com/carloscastau)
- LinkedIn: [carloscastau](https://linkedin.com/in/carloscastau)
- Email: ccastanourrego@gmail.com
