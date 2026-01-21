# 🚀 GUÍA: PUBLICAR EN CLOUDFLARE PAGES
## Caballero De León - Deployment Guide

---

## ✅ VENTAJAS DE CLOUDFLARE PAGES

- ✅ **GRATIS** para siempre
- ✅ **SSL automático** (HTTPS)
- ✅ **CDN global** (súper rápido en todo el mundo)
- ✅ **Deploy ilimitados**
- ✅ Ya tienes el dominio en Cloudflare
- ✅ Git integration opcional
- ✅ Analytics incluido

---

## 📋 PREREQUISITOS

- [x] Dominio comprado en Cloudflare ✓
- [ ] Cuenta GitHub (opcional pero recomendado)
- [ ] Archivos del sitio listos
- [ ] Configuraciones completadas (Calendly, Google Sheets, etc.)

---

## 🎯 MÉTODO 1: DRAG & DROP (MÁS RÁPIDO - 5 MINUTOS)

### Paso 1: Preparar archivos
Ya tienes todo listo en `/sitio-mejorado/`:
- index.html (versión mejorada con leads)
- Todas las páginas HTML
- Carpeta images/
- Guías de configuración

### Paso 2: Acceder a Cloudflare Pages
1. Inicia sesión en tu cuenta de Cloudflare
2. En el panel lateral, busca **"Workers & Pages"**
3. Click en **"Create application"**
4. Selecciona **"Pages"**
5. Click en **"Upload assets"**

### Paso 3: Subir archivos
1. Arrastra toda la carpeta `sitio-mejorado` o selecciona los archivos:
   ```
   ✓ index.html
   ✓ nosotros.html
   ✓ preguntas-frecuentes.html
   ✓ financial-tax-advisory.html
   ✓ property-asset-management.html
   ✓ architecture-design-advisory.html
   ✓ Carpeta images/ (con hero-background.jpg)
   ```

2. Dale un nombre al proyecto: **caballero-de-leon**

3. Click en **"Save and Deploy"**

### Paso 4: ¡Ya está online!
Cloudflare te dará una URL temporal como:
```
https://caballero-de-leon.pages.dev
```

**¡Prueba que todo funcione antes de conectar el dominio!**

### Paso 5: Conectar tu dominio personalizado
1. En Cloudflare Pages, ve a tu proyecto
2. Click en **"Custom domains"**
3. Click en **"Set up a custom domain"**
4. Escribe tu dominio: `caballerodeleon.com` (o el que compraste)
5. Cloudflare configurará automáticamente los DNS
6. ¡Listo! En 1-5 minutos estará activo

**Resultado:** 
- https://www.caballerodeleon.com ✓
- https://caballerodeleon.com ✓
- Ambos con HTTPS automático ✓

---

## 🎯 MÉTODO 2: CON GITHUB (RECOMENDADO PARA ACTUALIZACIONES)

### ¿Por qué usar GitHub?
- Actualizaciones más fáciles
- Control de versiones
- Deploy automático al hacer cambios
- Backup en la nube

### Paso 1: Crear repositorio en GitHub
1. Ve a https://github.com
2. Click en **"New repository"**
3. Nombre: `caballero-de-leon-web`
4. Privacidad: **Private** (recomendado)
5. Click en **"Create repository"**

### Paso 2: Subir archivos a GitHub

**Opción A - Interfaz web (más fácil):**
1. En tu nuevo repo, click en **"uploading an existing file"**
2. Arrastra todos los archivos del sitio
3. Escribe en commit: "Initial commit - sitio completo"
4. Click en **"Commit changes"**

**Opción B - Línea de comandos:**
```bash
cd /ruta/a/sitio-mejorado
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/TU-USUARIO/caballero-de-leon-web.git
git push -u origin main
```

### Paso 3: Conectar GitHub con Cloudflare Pages
1. En Cloudflare, **"Workers & Pages"** → **"Create application"**
2. Selecciona **"Pages"**
3. Click en **"Connect to Git"**
4. Autoriza GitHub
5. Selecciona tu repositorio: `caballero-de-leon-web`
6. Configuración de build:
   ```
   Framework preset: None
   Build command: (dejar vacío)
   Build output directory: /
   ```
7. Click en **"Save and Deploy"**

### Paso 4: Deploy automático
Ahora cada vez que actualices archivos en GitHub:
1. Editas archivo en GitHub (o subes nuevo)
2. Commit
3. ¡Cloudflare automáticamente actualiza el sitio!

---

## ⚙️ CONFIGURACIÓN ADICIONAL EN CLOUDFLARE

### 1. Configurar Analytics
1. En tu proyecto de Pages → **"Analytics"**
2. Activa **Web Analytics**
3. Verás visitas, páginas más visitadas, etc.

### 2. Configurar reglas de caché
1. Ve a tu dominio en Cloudflare
2. **"Caching"** → **"Configuration"**
3. Activa:
   - ✓ Auto Minify (HTML, CSS, JS)
   - ✓ Brotli compression

### 3. Configurar SSL/TLS
1. **"SSL/TLS"** → **"Overview"**
2. Modo: **"Full (strict)"** ← Importante
3. Edge Certificates → ✓ Always Use HTTPS

### 4. Configurar Speed
1. **"Speed"** → **"Optimization"**
2. Activa:
   - ✓ Auto Minify
   - ✓ Rocket Loader (opcional)
   - ✓ Mirage (opcional)

### 5. Configurar Security
1. **"Security"** → **"Settings"**
2. Security Level: **Medium**
3. Bot Fight Mode: **On**
4. Challenge Passage: **30 minutes**

---

## 📧 CONFIGURACIÓN DE EMAIL

### Opción 1: Email Routing (GRATIS en Cloudflare)
Para recibir emails en `hola@caballerodeleon.com`:

1. En Cloudflare → Tu dominio → **"Email"** → **"Email Routing"**
2. Click en **"Get started"**
3. Agrega destinos:
   ```
   hola@caballerodeleon.com → tu-email@gmail.com
   contacto@caballerodeleon.com → tu-email@gmail.com
   ```
4. Verifica tu email
5. ¡Listo! Ya recibes emails

**IMPORTANTE:** 
- Email Routing solo RECIBE emails
- Para ENVIAR desde hola@caballerodeleon.com necesitas Gmail/Outlook configurado

### Opción 2: Gmail con dominio personalizado
1. Google Workspace ($6/mes por usuario)
2. Te permite enviar Y recibir desde @caballerodeleon.com

### Opción 3: Zoho Mail (GRATIS hasta 5 usuarios)
1. Ve a https://www.zoho.com/mail/
2. Crea cuenta con tu dominio
3. Configura DNS en Cloudflare (Zoho te guía)

---

## 🔧 TROUBLESHOOTING

### Problema: "DNS resolution error"
**Solución:**
1. Ve a Cloudflare DNS
2. Verifica que existan estos registros:
   ```
   Type: CNAME
   Name: @
   Target: caballero-de-leon.pages.dev
   
   Type: CNAME
   Name: www
   Target: caballero-de-leon.pages.dev
   ```

### Problema: El sitio muestra pero sin estilos
**Solución:**
- Verifica que subiste la carpeta `images/`
- Revisa las rutas en el HTML (deben ser relativas)

### Problema: Formulario no funciona
**Solución:**
- Verifica que configuraste el Google Apps Script
- Revisa que la URL del script esté en el HTML línea 332

### Problema: Calendly no se ve
**Solución:**
- Verifica que pusiste tu usuario de Calendly en líneas 221 y 369
- Revisa que el link de Calendly esté activo

### Problema: SSL no activo después de 24h
**Solución:**
1. Cloudflare → SSL/TLS → Edge Certificates
2. Desactiva y reactiva "Universal SSL"
3. Espera 15 minutos

---

## 📊 VERIFICACIÓN POST-DEPLOY

### Checklist de testing:
- [ ] Sitio carga en `https://tudominio.com`
- [ ] Sitio carga en `https://www.tudominio.com`
- [ ] Todas las páginas cargan correctamente
- [ ] Imágenes se ven correctamente
- [ ] Formulario de contacto funciona
- [ ] WhatsApp funciona
- [ ] Botón de Calendly funciona
- [ ] Exit popup funciona
- [ ] Google Analytics registra visitas
- [ ] Emails llegan a Google Sheets
- [ ] Sitio se ve bien en mobile
- [ ] Sitio se ve bien en tablet
- [ ] Sitio se ve bien en desktop

### Herramientas de testing:
- **PageSpeed Insights:** https://pagespeed.web.dev/
  - Objetivo: >90 puntos en mobile y desktop
  
- **SSL Test:** https://www.ssllabs.com/ssltest/
  - Objetivo: A o A+
  
- **Mobile-Friendly Test:** https://search.google.com/test/mobile-friendly
  - Objetivo: Mobile-friendly ✓

---

## 🎯 ACTUALIZACIONES FUTURAS

### Método 1: Drag & Drop (Sin GitHub)
1. En Cloudflare Pages → Tu proyecto
2. **"Manage"** → **"Upload new assets"**
3. Arrastra archivos modificados
4. Deploy automático

### Método 2: GitHub (Recomendado)
1. Edita archivo en GitHub
2. O sube archivo nuevo
3. Commit changes
4. ¡Deploy automático!

### Actualizaciones comunes:
- **Cambiar texto:** Edita HTML
- **Agregar imagen:** Sube a `/images/` y referencia en HTML
- **Nueva página:** Crea nuevo .html y linkea desde navegación
- **Actualizar precios/info:** Edita el .html correspondiente

---

## 💰 COSTOS

### Cloudflare Pages:
- **Hosting:** GRATIS ✓
- **SSL:** GRATIS ✓
- **CDN:** GRATIS ✓
- **Builds:** GRATIS (500 builds/mes)
- **Bandwidth:** GRATIS (ilimitado)

### Dominio:
- **Ya lo tienes** ✓
- Renovación anual: ~$10-15/año

### Otros servicios:
- **Calendly:** GRATIS (básico) o $10/mes (Pro)
- **Google Sheets:** GRATIS ✓
- **Google Analytics:** GRATIS ✓
- **Brevo/Mailchimp:** GRATIS (hasta cierto volumen)
- **Zapier:** GRATIS (100 tasks/mes) o desde $20/mes

**Total mínimo:** $0/mes (solo dominio $10-15/año)

---

## 🚀 PASOS INMEDIATOS

### ANTES DE SUBIR:
1. [ ] Completa configuración de Calendly
2. [ ] Configura Google Sheets + Apps Script
3. [ ] Obtén ID de Google Analytics
4. [ ] (Opcional) Obtén Meta Pixel ID
5. [ ] Reemplaza todos los placeholder en el HTML:
   ```
   - TU-USUARIO (Calendly) líneas 221, 369
   - TU_WEB_APP_URL_DE_GOOGLE_SHEETS línea 332
   - G-XXXXXXXXXX (Google Analytics) líneas 12, 15
   - TU_PIXEL_ID (Meta) línea 24
   - tu-email@gmail.com en script de notificación
   ```

### AL SUBIR:
1. [ ] Sube a Cloudflare Pages (Método 1 o 2)
2. [ ] Conecta dominio personalizado
3. [ ] Verifica que todo funcione
4. [ ] Prueba formulario
5. [ ] Prueba Calendly
6. [ ] Revisa en móvil

### DESPUÉS DE SUBIR:
1. [ ] Envía link de prueba a amigo/colega
2. [ ] Configura Google Search Console
3. [ ] Envía sitemap a Google
4. [ ] Agrega sitio a Google My Business
5. [ ] ¡Empieza a promocionar! 🚀

---

## 📞 SOPORTE CLOUDFLARE

- Dashboard: https://dash.cloudflare.com
- Documentación: https://developers.cloudflare.com/pages/
- Community: https://community.cloudflare.com/
- Status: https://www.cloudflarestatus.com/

---

## ✅ CONCLUSIÓN

**Tiempo estimado de deployment:** 15-30 minutos

**Pasos:**
1. ✓ Subir archivos a Cloudflare Pages
2. ✓ Conectar dominio
3. ✓ Verificar funcionamiento
4. ✓ ¡Lanzar!

**¿Todo listo?** ¡Adelante! 🚀

Cualquier problema, revisa la sección de troubleshooting o avísame.
