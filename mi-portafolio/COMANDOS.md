# 📋 Comandos Útiles - Referencia Rápida

## 🚀 Desarrollo Local

```bash
# Instalar dependencias (solo la primera vez)
npm install

# Iniciar servidor de desarrollo
npm run dev

# El sitio estará disponible en:
# http://localhost:4321
```

## 🏗️ Build y Preview

```bash
# Crear versión de producción
npm run build

# Previsualizar la versión de producción
npm run preview
```

## 📤 Git y GitHub

```bash
# Primera vez - Inicializar Git
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/TU-USUARIO/mi-portafolio.git
git push -u origin main

# Subir cambios posteriores
git add .
git commit -m "Descripción de los cambios"
git push

# Ver estado de los archivos
git status

# Ver historial de commits
git log --oneline
```

## 🔍 Solución de Problemas

```bash
# Si algo no funciona, limpia y reinstala
rm -rf node_modules
rm package-lock.json
npm install

# Si el puerto 4321 está ocupado
npm run dev -- --port 3000

# Ver qué archivos han cambiado
git diff
```

## 📁 Estructura de Archivos

```
mi-portafolio/
├── src/
│   ├── layouts/
│   │   └── Layout.astro           ← Layout principal con navbar
│   ├── pages/
│   │   ├── index.astro            ← Página de inicio
│   │   ├── presentacion.astro     ← Tu presentación
│   │   ├── evidencias.astro       ← Evidencias (BONUS)
│   │   └── proyectos.astro        ← Tus proyectos
├── public/
│   ├── images/                    ← Tus imágenes aquí
│   └── favicon.svg                ← Icono del sitio
├── .github/
│   └── workflows/
│       └── deploy.yml             ← Configuración GitHub Actions
├── astro.config.mjs               ← ⚠️ CONFIGURAR CON TUS DATOS
├── package.json
└── README.md
```

## ⚙️ Archivos a Configurar

### 1. astro.config.mjs
```javascript
site: 'https://TU-USUARIO.github.io',  // ← Cambiar
base: '/NOMBRE-REPO',                   // ← Cambiar
```

### 2. src/pages/index.astro
```astro
<span class="highlight">Tu Nombre</span>  // ← Línea ~10
```

### 3. src/pages/presentacion.astro
```astro
<h2>Tu Nombre Completo</h2>                // ← Línea ~25
<!-- Video de YouTube -->
src="https://www.youtube.com/embed/ID"     // ← Línea ~41
```

## 🎨 Personalización de Colores

En `src/layouts/Layout.astro` (aprox. línea 60):

```css
:root {
  --bg-primary: #0a0a0a;      /* Fondo principal (negro) */
  --bg-secondary: #1a1a1a;    /* Fondo secundario */
  --bg-card: #2a2a2a;         /* Fondo de tarjetas */
  --text-primary: #ffffff;    /* Texto principal (blanco) */
  --text-secondary: #b0b0b0;  /* Texto secundario (gris) */
  --accent: #3b82f6;          /* Color de acento (azul) */
  --accent-hover: #2563eb;    /* Hover del acento */
  --border: #333333;          /* Bordes */
}
```

## 📸 Agregar Imágenes

### Foto de Perfil

1. Copia tu foto a `public/images/perfil.jpg`
2. En `presentacion.astro`, reemplaza el placeholder:

```html
<img 
  src="/images/perfil.jpg" 
  alt="Tu Nombre" 
  style="width: 150px; height: 150px; border-radius: 50%; object-fit: cover;"
>
```

### Imagen en Home

Similar, pero en `src/pages/index.astro`

## 🎥 Agregar Video

En `src/pages/presentacion.astro`:

1. Sube tu video a YouTube
2. Obtén el ID del video (ej: `dQw4w9WgXcQ`)
3. Descomenta las líneas 40-46
4. Reemplaza `TU_VIDEO_ID` con tu ID real

## 🔗 URLs Importantes

```
Local:          http://localhost:4321
GitHub Pages:   https://TU-USUARIO.github.io/mi-portafolio/
GitHub Repo:    https://github.com/TU-USUARIO/mi-portafolio
```

## ✅ Antes de Entregar

```bash
# 1. Verifica que todo compile
npm run build

# 2. Verifica que no haya errores
# (Si hay errores, los verás en la terminal)

# 3. Sube todo a GitHub
git add .
git commit -m "Final version for submission"
git push

# 4. Verifica que GitHub Pages esté activo
# Ve a: Settings → Pages en tu repo
```

## 🆘 Comandos de Emergencia

```bash
# Si VS Code no reconoce comandos de git
# Abre Git Bash o la terminal de Git

# Si el sitio no se actualiza en GitHub Pages
# Fuerza un nuevo deploy:
git commit --allow-empty -m "Trigger rebuild"
git push

# Si quieres ver los logs del servidor
npm run dev -- --verbose
```

## 🎓 Checklist de Entrega

```
□ Sitio publicado en GitHub Pages
□ URL funciona y se ve correctamente
□ Nombre personalizado en todas las páginas
□ Foto/avatar visible
□ Video agregado (o placeholder claro)
□ Sección "Sobre Mí" completa
□ Sección "Evidencias" con 4 categorías (BONUS)
□ Todos los links del menú funcionan
□ astro.config.mjs configurado correctamente
□ Probado en móvil (responsive)
□ URL entregada en Brightspace
```

---

**¿Dudas?** Revisa `GUIA-VSCODE.md` para instrucciones paso a paso.
