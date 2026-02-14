# 🎓 Mi Portafolio - Bases de Datos 1

Portafolio profesional creado para el curso de Bases de Datos 1 - Universidad El Bosque

## 🚀 Configuración Inicial

### Paso 1: Abrir el proyecto en VS Code

1. Abre VS Code
2. Ve a `File` > `Open Folder`
3. Selecciona la carpeta `mi-portafolio`

### Paso 2: Instalar dependencias

Abre la terminal en VS Code (`Ctrl + ñ` o `Terminal` > `New Terminal`) y ejecuta:

```bash
npm install
```

### Paso 3: Ejecutar en modo desarrollo

```bash
npm run dev
```

Abre tu navegador en `http://localhost:4321`

## 📝 Personalizar tu Portafolio

### 1. Configuración Básica

Edita `astro.config.mjs`:

```javascript
export default defineConfig({
  site: 'https://TU-USUARIO.github.io',
  base: '/NOMBRE-DE-TU-REPO',
});
```

Reemplaza:
- `TU-USUARIO` con tu nombre de usuario de GitHub
- `NOMBRE-DE-TU-REPO` con el nombre de tu repositorio

### 2. Personalizar Información

#### Home (`src/pages/index.astro`)
- Línea 10: Cambia "Tu Nombre" por tu nombre real
- Personaliza la descripción

#### Presentación (`src/pages/presentacion.astro`)
- Línea 25: Agrega tu nombre completo
- Líneas 50-75: Agrega tu información personal
- Para agregar tu video de YouTube:
  1. Sube tu video a YouTube
  2. Copia el ID del video (después de `v=` en la URL)
  3. Descomenta las líneas 40-46
  4. Reemplaza `TU_VIDEO_ID` con el ID real

### 3. Agregar tu Foto/Avatar

Opción A: Usa una imagen
1. Guarda tu foto en `public/images/perfil.jpg`
2. En `src/pages/presentacion.astro`, reemplaza el placeholder (líneas 30-38) con:

```html
<img src="/images/perfil.jpg" alt="Tu Nombre" />
```

Opción B: Usa un avatar de Gravatar o similar
- Reemplaza la URL de la imagen

## 📤 Publicar en GitHub Pages

### Paso 1: Crear repositorio en GitHub

1. Ve a [GitHub](https://github.com)
2. Click en "New repository"
3. Nombra tu repositorio (ej: `mi-portafolio`)
4. Hazlo público
5. NO inicialices con README

### Paso 2: Conectar tu proyecto local

En la terminal de VS Code:

```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/TU-USUARIO/NOMBRE-REPO.git
git push -u origin main
```

### Paso 3: Configurar GitHub Actions

Crea el archivo `.github/workflows/deploy.yml` con el contenido que se proporciona más abajo.

### Paso 4: Habilitar GitHub Pages

1. Ve a tu repositorio en GitHub
2. Click en "Settings"
3. En el menú lateral, click en "Pages"
4. En "Source", selecciona "GitHub Actions"
5. Guarda los cambios

### Paso 5: Hacer push y esperar

```bash
git add .
git commit -m "Add GitHub Actions workflow"
git push
```

Espera 2-3 minutos. Tu sitio estará en:
`https://TU-USUARIO.github.io/NOMBRE-REPO/`

## 📁 Estructura del Proyecto

```
mi-portafolio/
├── src/
│   ├── layouts/
│   │   └── Layout.astro          # Layout principal
│   ├── pages/
│   │   ├── index.astro           # Página de inicio
│   │   ├── presentacion.astro    # Tu presentación
│   │   ├── evidencias.astro      # Evidencias del curso
│   │   └── proyectos.astro       # Tus proyectos
│   └── styles/
├── public/
│   └── images/                   # Tus imágenes aquí
├── .github/
│   └── workflows/
│       └── deploy.yml            # Config de GitHub Pages
└── astro.config.mjs              # Configuración de Astro
```

## 🎨 Personalización de Colores

En `src/layouts/Layout.astro`, busca la sección `:root` (línea ~60) para cambiar los colores:

```css
:root {
  --bg-primary: #0a0a0a;      /* Fondo principal */
  --bg-secondary: #1a1a1a;    /* Fondo secundario */
  --accent: #3b82f6;          /* Color de acento */
  /* ... */
}
```

## ✅ Checklist para la Entrega

- [ ] Personalicé mi nombre en todas las páginas
- [ ] Agregué mi foto/avatar
- [ ] Subí mi video de presentación (90-120 segundos)
- [ ] Completé la sección "Sobre Mí" en Presentación
- [ ] La sección "Evidencias" está creada con las 4 categorías
- [ ] Configuré `astro.config.mjs` con mis datos de GitHub
- [ ] Creé mi repositorio en GitHub
- [ ] Configuré GitHub Actions
- [ ] Mi sitio está publicado y funciona
- [ ] Probé todos los enlaces del menú

## 🆘 Solución de Problemas

### El sitio no carga correctamente
- Verifica que `astro.config.mjs` tenga la configuración correcta
- Asegúrate de que `base` coincida con el nombre de tu repositorio

### Las imágenes no se ven
- Verifica que las rutas comiencen con `/` (ej: `/images/foto.jpg`)
- Las imágenes deben estar en la carpeta `public/`

### GitHub Actions falla
- Verifica que el archivo `deploy.yml` esté en `.github/workflows/`
- Asegúrate de que GitHub Pages esté habilitado en la configuración

## 📚 Recursos Adicionales

- [Documentación de Astro](https://docs.astro.build)
- [GitHub Pages Docs](https://docs.github.com/en/pages)
- [Markdown Guide](https://www.markdownguide.org/)

---

**Hecho con ❤️ para Bases de Datos 1 - Universidad El Bosque**
