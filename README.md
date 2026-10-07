# ☀️ SOLARIX 1.3.0 — PWA (Progressive Web App)

Calculadora y dimensionamiento profesional de sistemas solares fotovoltaicos, dimensionamiento de banco de baterías, inversores, controladores y calibres de protección eléctrica.

Esta versión está completamente configurada como una **Progressive Web App (PWA)** instalable con soporte **100% offline**, lista para desplegarse de inmediato en **GitHub Pages**.

---

## 🚀 Características PWA

- 📲 **Instalable en cualquier dispositivo**: Android, iOS, Windows, macOS y Linux.
- 📶 **100% Offline (Sin conexión a internet)**: Funciona en campo o zonas remotas gracias a su Service Worker con precaché.
- ⚡ **Acceso Rápido**: Botón interactivo `"📲 Instalar App"` integrado directamente en la barra de navegación.
- 🎨 **Diseño e Iconografía Retina**: Incluye conjunto completo de iconos de alta resolución (192px, 512px, maskable adaptativo para Android, SVG vectorial y favicon).
- 🔗 **Rutas Relativas**: Diseñado específicamente para funcionar sin errores tanto en la raíz de un dominio como en subdirectorios de GitHub Pages (`https://<usuario>.github.io/<repo>/`).

---

## 🛠️ Estructura del Proyecto

```text
SOLARIX1.3.0/
├── index.html              # Aplicación web principal + registro de Service Worker
├── manifest.webmanifest    # Manifiesto de la aplicación web (PWA)
├── sw.js                   # Service Worker (Caché y soporte offline)
├── .nojekyll               # Evita que GitHub Pages ignore archivos estáticos
├── favicon.png             # Icono de pestaña (64x64)
├── icons/
│   ├── icon.svg            # Icono vectorial escalable
│   ├── icon-192.png        # Icono estándar PWA (192x192)
│   ├── icon-512.png        # Icono estándar PWA (512x512)
│   ├── icon-maskable.png   # Icono adaptable Android (512x512)
│   └── apple-touch-icon.png# Icono para dispositivos Apple iOS (180x180)
└── README.md               # Esta guía
```

---

## 📦 Guía de Despliegue en GitHub Pages

Para publicar tu aplicación en GitHub Pages y que esté disponible en internet con HTTPS (requisito indispensable para que las PWA se puedan instalar), sigue estos pasos:

### Paso 1: Inicializar Git y realizar el commit inicial

Abre tu terminal en la carpeta de este proyecto y ejecuta:

```bash
git init
git add .
git commit -m "feat: configurar SOLARIX como PWA para GitHub Pages"
```

### Paso 2: Crear el repositorio en GitHub y subir los archivos

1. Ve a [GitHub](https://github.com/) e inicia sesión.
2. Haz clic en **New repository** (o **Nuevo repositorio**).
3. Nombra tu repositorio (por ejemplo: `solarix` o `solarix-pwa`).
4. Déjalo como **Público** (Public) y **no** selecciones "Add a README file" (ya tienes uno).
5. Haz clic en **Create repository**.
6. Copia y ejecuta los comandos que GitHub te indica en tu terminal:

```bash
git branch -M main
git remote add origin https://github.com/TU_USUARIO/TU_REPOSITORIO.git
git push -u origin main
```
*(Reemplaza `TU_USUARIO` y `TU_REPOSITORIO` con tus datos correspondientes).*

### Paso 3: Activar GitHub Pages

1. En la página de tu repositorio en GitHub, ve a la pestaña **Settings** (Configuración).
2. En el menú lateral izquierdo, haz clic en **Pages** (en la sección *Code and automation*).
3. En la sección **Build and deployment**:
   - **Source**: Selecciona `Deploy from a branch`.
   - **Branch**: Selecciona la rama `main` y la carpeta `/(root)`.
   - Haz clic en **Save** (Guardar).
4. Espera entre 1 y 2 minutos mientras GitHub genera la página.
5. Tu aplicación estará disponible en la URL:
   ```text
   https://TU_USUARIO.github.io/TU_REPOSITORIO/
   ```

---

## 📱 Cómo Instalar la PWA en tus Dispositivos

Una vez abierta la URL de GitHub Pages en tu navegador:

- **En Google Chrome / Microsoft Edge (PC / Mac)**:
  - Verás el botón `"📲 Instalar App"` en la cabecera. Haz clic en él o presiona el icono de instalación que aparece en la barra de direcciones.
- **En Android (Chrome / Brave / Edge)**:
  - Toca el botón `"📲 Instalar App"` o despliega el menú de tres puntos (⋮) y selecciona **"Instalar aplicación"** o **"Agregar a la pantalla principal"**.
- **En iPhone / iPad (Safari)**:
  - Toca el botón de **Compartir** (icono de cuadro con flecha hacia arriba).
  - Desplázate hacia abajo y selecciona **"Agregar al inicio"** (Add to Home Screen).

---

## 🔒 Privacidad y Almacenamiento Local

SOLARIX funciona de manera autónoma en el navegador del usuario:
- Todos los cálculos se realizan localmente en JavaScript.
- Los proyectos guardados se almacenan en el `localStorage` de tu navegador, garantizando que tus datos permanezcan privados en tu dispositivo incluso sin conexión a internet.
