# 🎯 Guía Paso a Paso - VS Code

## ✅ PASO 1: Preparar VS Code

1. **Abrir VS Code**
2. **Abrir la carpeta del proyecto:**
   - `Archivo` → `Abrir carpeta...` (o `Ctrl+K Ctrl+O`)
   - Navega hasta `mi-portafolio` y selecciónala
   - Click en "Seleccionar carpeta"

3. **Abrir la terminal integrada:**
   - `Terminal` → `Nueva Terminal` (o `Ctrl+Ñ`)

## ✅ PASO 2: Instalar Dependencias

En la terminal que acabas de abrir, escribe:

```bash
npm install
```

Espera a que termine (verás que se crea una carpeta `node_modules`)

## ✅ PASO 3: Probar tu Sitio Localmente

En la misma terminal, escribe:

```bash
npm run dev
```

Verás algo como:
```
🚀 astro v4.16.0 started in 234ms
  ┃ Local    http://localhost:4321/
```

**Abre tu navegador** y ve a: `http://localhost:4321`

¡Deberías ver tu portafolio! 🎉

## ✅ PASO 4: Personalizar tu Portafolio

### 4.1 - Configuración Básica

1. Abre el archivo `astro.config.mjs` (en VS Code, en el explorador de la izquierda)

2. Cambia estas líneas:
```javascript
site: 'https://TU-USUARIO-GITHUB.github.io',
base: '/NOMBRE-DE-TU-REPOSITORIO',
```

Ejemplo real:
```javascript
site: 'https://juanperez.github.io',
base: '/mi-portafolio',
```

### 4.2 - Página Principal

1. Abre `src/pages/index.astro`
2. Busca la línea 10 (aprox): `<span class="highlight">Tu Nombre</span>`
3. Cambia "Tu Nombre" por tu nombre real

### 4.3 - Página de Presentación

1. Abre `src/pages/presentacion.astro`
2. Busca y personaliza:
   - Línea 25: Tu nombre completo
   - Líneas 77-95: Tus respuestas personales

### 4.4 - Agregar tu Foto

**Opción A: Tienes una foto**
1. Copia tu foto a la carpeta `public/images/`
2. Renómbrala a `perfil.jpg` (o .png)
3. En `src/pages/presentacion.astro`, busca el `<div class="image-placeholder">` (línea 30)
4. Reemplázalo con:
```html
<img src="/images/perfil.jpg" alt="Tu Nombre" style="width: 150px; height: 150px; border-radius: 50%; object-fit: cover;">
```

**Opción B: Usas el placeholder**
- ¡No hagas nada! El icono ya se ve bien

### 4.5 - Agregar tu Video

**Cuando lo tengas en YouTube:**

1. Sube tu video a YouTube
2. Copia el ID (ejemplo: en `youtube.com/watch?v=ABC123`, el ID es `ABC123`)
3. En `src/pages/presentacion.astro`, líneas 40-46, descomenta y cambia:
```html
<iframe 
  src="https://www.youtube.com/embed/ABC123" 
  title="Video de Presentación"
  frameborder="0" 
  allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
  allowfullscreen>
</iframe>
```

4. Comenta o elimina el `<div class="video-placeholder">` (líneas 49-55)

## ✅ PASO 5: Ver tus Cambios

Cada vez que guardes un archivo (`Ctrl+S`), el navegador se actualizará automáticamente.

Si algo no se ve bien:
1. Detén el servidor (en la terminal: `Ctrl+C`)
2. Vuelve a iniciarlo: `npm run dev`

## ✅ PASO 6: Preparar para GitHub

### 6.1 - Crear el repositorio en GitHub

1. Ve a [github.com](https://github.com)
2. Click en el "+" arriba a la derecha → "New repository"
3. Nombre: `mi-portafolio` (o el que prefieras)
4. Descripción: "Portafolio - Bases de Datos 1"
5. **Público** ✅
6. **NO marques** "Add a README file"
7. Click en "Create repository"

### 6.2 - Conectar tu proyecto

En la terminal de VS Code:

```bash
git init
git add .
git commit -m "Initial commit: Portfolio setup"
git branch -M main
git remote add origin https://github.com/TU-USUARIO/mi-portafolio.git
git push -u origin main
```

⚠️ **Reemplaza `TU-USUARIO` y `mi-portafolio`** con tus datos reales

## ✅ PASO 7: Activar GitHub Pages

1. En tu repositorio de GitHub, click en **"Settings"**
2. En el menú lateral izquierdo, click en **"Pages"**
3. En "Build and deployment":
   - Source: **GitHub Actions**
4. ¡Listo! No necesitas hacer nada más aquí

## ✅ PASO 8: Esperar el Deploy

1. Ve a la pestaña **"Actions"** en tu repositorio
2. Verás un proceso ejecutándose
3. Espera 2-3 minutos hasta que aparezca un ✅ verde
4. Tu sitio estará en: `https://TU-USUARIO.github.io/mi-portafolio/`

## 🔄 Actualizar tu Sitio Después

Cada vez que hagas cambios:

```bash
git add .
git commit -m "Descripción de tus cambios"
git push
```

GitHub Pages se actualizará automáticamente en 2-3 minutos.

## 🎨 Tips de Personalización Extra

### Cambiar Colores

En `src/layouts/Layout.astro`, busca (alrededor de la línea 60):

```css
:root {
  --accent: #3b82f6;  /* Cambia este color */
}
```

Usa [coolors.co](https://coolors.co) para elegir colores bonitos.

### Agregar más Secciones en el Menú

En `src/layouts/Layout.astro`, busca `<ul class="nav-links">` y agrega:

```html
<li><a href="/nueva-seccion">Nueva Sección</a></li>
```

Luego crea el archivo `src/pages/nueva-seccion.astro`

## 🆘 Problemas Comunes

### "npm no se reconoce como comando"
- **Solución:** Instala Node.js desde [nodejs.org](https://nodejs.org)

### El sitio en GitHub Pages muestra 404
- **Solución:** Verifica que `base` en `astro.config.mjs` sea exactamente el nombre de tu repo

### Las imágenes no se ven
- **Solución:** Asegúrate de que las rutas empiecen con `/` (ejemplo: `/images/foto.jpg`)

### Los estilos no se aplican
- **Solución:** 
  1. Detén el servidor (`Ctrl+C`)
  2. Borra la carpeta `dist` si existe
  3. Reinicia: `npm run dev`

## ✅ Checklist Final

Antes de entregar, verifica:

- [ ] Mi nombre aparece correctamente en todas las páginas
- [ ] Mi foto/avatar está visible
- [ ] Mi video está embebido (o el placeholder está claro)
- [ ] La sección "Sobre Mí" está completa
- [ ] La página "Evidencias" tiene las 4 categorías
- [ ] Mi sitio está en GitHub
- [ ] GitHub Pages está activo
- [ ] El sitio se ve bien en el navegador
- [ ] Todos los links del menú funcionan
- [ ] Probé mi sitio en el celular (responsive)

## 📤 ¿Qué Entregar?

En Brightspace, entrega:

1. **URL de tu GitHub Pages:** `https://TU-USUARIO.github.io/mi-portafolio/`
2. **URL de tu repositorio (opcional):** `https://github.com/TU-USUARIO/mi-portafolio`

---

## 🎉 ¡Listo!

Si todo está bien, ¡felicidades! Ya tienes tu portafolio profesional publicado.

**¿Preguntas?** Revisa el archivo `README.md` principal para más detalles técnicos.
