# ✅ CHECKLIST COMPLETO - LANZAMIENTO DEL SITIO
## Caballero De León Advisory Studio

---

## 📅 PLANIFICACIÓN DE IMPLEMENTACIÓN

### FASE 1: CONFIGURACIÓN TÉCNICA (DÍA 1-2)
**Tiempo estimado: 3-4 horas**

#### 1.1 Calendly
- [ ] Crear cuenta en Calendly.com
- [ ] Configurar disponibilidad horaria
- [ ] Crear evento "Primera Consulta" (30 min)
- [ ] Configurar preguntas de calificación:
  - [ ] Nombre completo
  - [ ] Email
  - [ ] Teléfono
  - [ ] Servicio de interés
  - [ ] Principal desafío
  - [ ] Cómo nos conoció
- [ ] Configurar ubicación (Zoom/Google Meet)
- [ ] Copiar link de Calendly
- [ ] Pegar link en HTML (líneas 221 y 369)
- [ ] Probar que funcione

#### 1.2 Google Sheets - Base de Datos de Leads
- [ ] Crear hoja "Leads - Caballero De León"
- [ ] Configurar columnas (A-J según guía)
- [ ] Ir a Extensiones → Apps Script
- [ ] Copiar código del script (ver GUIA-CONFIGURACION-LEADS.md)
- [ ] Cambiar email de notificación a tu email
- [ ] Implementar → Nueva implementación
- [ ] Copiar Web App URL
- [ ] Pegar URL en HTML (línea 332)
- [ ] Probar envío de formulario de prueba

#### 1.3 Google Analytics
- [ ] Crear cuenta en analytics.google.com
- [ ] Crear propiedad para el sitio
- [ ] Copiar ID de medición (G-XXXXXXXXXX)
- [ ] Pegar en HTML (líneas 12 y 15)
- [ ] Verificar instalación (tiempo real)

#### 1.4 Meta Pixel (Opcional - si harás Facebook Ads)
- [ ] Ir a business.facebook.com
- [ ] Crear Pixel
- [ ] Copiar Pixel ID
- [ ] Pegar en HTML (línea 24)
- [ ] Verificar con Facebook Pixel Helper (extensión Chrome)

---

### FASE 2: CONTENIDO Y CONFIGURACIÓN DE EMAILS (DÍA 2-3)
**Tiempo estimado: 4-5 horas**

#### 2.1 Plataforma de Email Marketing
- [ ] Decidir plataforma: Brevo (recomendado) o Mailchimp
- [ ] Crear cuenta en Brevo.com
- [ ] Verificar dominio de email
- [ ] Crear lista "Leads - Caballero De León"
- [ ] Importar plantillas de email (ver PLANTILLAS-EMAIL-NURTURING.md)

#### 2.2 Secuencia de Emails
- [ ] Email 1: Bienvenida (inmediato) ← PRIORIDAD
- [ ] Email 2: Contenido de valor (+48h)
- [ ] Email 3: CTA (+5 días) ← PRIORIDAD
- [ ] Email 4: Educativo (+10 días)
- [ ] Email 5: Re-engagement (+20 días)
- [ ] Email 6: Nurturing mensual

#### 2.3 Contenido Descargable
- [ ] Crear PDF "Guía: 5 pasos para ordenar tu patrimonio"
- [ ] Diseñar portada básica
- [ ] Subir a sitio web o Dropbox/Google Drive
- [ ] Obtener link de descarga
- [ ] Agregar link en Email 4 y exit popup

#### 2.4 Plantillas de Respuesta Rápida
- [ ] Respuesta inicial (primeras 24h)
- [ ] Seguimiento sin respuesta (+2 días)
- [ ] Envío de propuesta
- [ ] Agradecimiento post-reunión

---

### FASE 3: AUTOMATIZACIÓN (DÍA 3-4)
**Tiempo estimado: 2-3 horas**

#### 3.1 Zapier / Make.com
- [ ] Crear cuenta en Zapier.com
- [ ] Crear Zap 1: Google Sheets → Brevo
  - Trigger: Nueva fila en Sheets
  - Action: Agregar contacto a lista en Brevo
- [ ] Crear Zap 2: Google Sheets → Notificación
  - Trigger: Nueva fila en Sheets
  - Action: Email/Slack/WhatsApp de notificación
- [ ] (Opcional) Crear Zap 3: Calendly → Google Sheets
  - Trigger: Nueva cita agendada
  - Action: Agregar a Sheets con tag "calendly"

#### 3.2 WhatsApp Business
- [ ] Descargar WhatsApp Business
- [ ] Configurar perfil comercial
- [ ] Agregar descripción del negocio
- [ ] Configurar mensaje de bienvenida automático
- [ ] Crear respuestas rápidas:
  - Saludo inicial
  - Servicios disponibles
  - Información de contacto
  - Link a Calendly

---

### FASE 4: DEPLOYMENT (DÍA 4-5)
**Tiempo estimado: 1-2 horas**

#### 4.1 Preparación de Archivos
- [ ] Verificar que todos los placeholders estén reemplazados:
  - [ ] TU-USUARIO → tu usuario de Calendly
  - [ ] TU_WEB_APP_URL → URL de Google Apps Script
  - [ ] G-XXXXXXXXXX → ID de Google Analytics
  - [ ] TU_PIXEL_ID → ID de Meta Pixel (si aplica)
- [ ] Probar sitio localmente (abrir index.html)
- [ ] Verificar que imágenes carguen
- [ ] Probar todos los links

#### 4.2 Subir a Cloudflare Pages
- [ ] Iniciar sesión en Cloudflare
- [ ] Workers & Pages → Create application
- [ ] Método 1 (Drag & Drop) o Método 2 (GitHub)
- [ ] Subir archivos
- [ ] Verificar deploy exitoso
- [ ] Probar URL temporal (*.pages.dev)

#### 4.3 Conectar Dominio
- [ ] Custom domains → Set up custom domain
- [ ] Agregar tu dominio
- [ ] Esperar propagación DNS (1-5 minutos)
- [ ] Verificar HTTPS activo

#### 4.4 Configuración Cloudflare
- [ ] SSL/TLS → Full (strict)
- [ ] Always Use HTTPS → ON
- [ ] Auto Minify → ON (HTML, CSS, JS)
- [ ] Brotli → ON

---

### FASE 5: TESTING COMPLETO (DÍA 5)
**Tiempo estimado: 2 horas**

#### 5.1 Testing Funcional
- [ ] Sitio carga en `https://tudominio.com`
- [ ] Sitio carga en `https://www.tudominio.com`
- [ ] Redirección HTTP → HTTPS funciona
- [ ] Navegación entre páginas funciona
- [ ] Imágenes cargan correctamente
- [ ] Botones funcionan
- [ ] Links externos funcionan

#### 5.2 Testing de Captura de Leads
- [ ] Llenar formulario de contacto de prueba
- [ ] Verificar que llegue a Google Sheets
- [ ] Verificar email de notificación
- [ ] Verificar que se agregue a Brevo
- [ ] Verificar secuencia de emails se active
- [ ] Probar WhatsApp flotante
- [ ] Probar botón de Calendly
- [ ] Agendar cita de prueba en Calendly
- [ ] Probar exit popup (mover mouse fuera de ventana)

#### 5.3 Testing de Analytics
- [ ] Abrir Google Analytics
- [ ] Verificar visita en tiempo real
- [ ] Hacer click en WhatsApp → Verificar evento
- [ ] Abrir Calendly → Verificar evento
- [ ] Enviar formulario → Verificar evento
- [ ] Activar exit popup → Verificar evento

#### 5.4 Testing Multi-Dispositivo
- [ ] Desktop (Chrome, Firefox, Safari)
- [ ] Tablet (iPad, Android)
- [ ] Mobile (iPhone, Android)
- [ ] Modo landscape y portrait en mobile

#### 5.5 Testing de Performance
- [ ] PageSpeed Insights → Objetivo >90
- [ ] GTmetrix → Objetivo A
- [ ] Pingdom → Objetivo <2 segundos

---

### FASE 6: SEO Y OPTIMIZACIÓN (DÍA 5-6)
**Tiempo estimado: 2-3 horas**

#### 6.1 Google Search Console
- [ ] Ir a search.google.com/search-console
- [ ] Agregar propiedad (tu dominio)
- [ ] Verificar con código o DNS
- [ ] Enviar sitemap.xml (crear si no existe)
- [ ] Verificar indexación

#### 6.2 Google My Business
- [ ] Crear perfil en google.com/business
- [ ] Completar información:
  - [ ] Nombre: Caballero De León Advisory Studio
  - [ ] Categoría: Consultoría financiera / Asesoría
  - [ ] Dirección (si aplica)
  - [ ] Teléfono
  - [ ] Sitio web
  - [ ] Horarios
- [ ] Verificar negocio
- [ ] Agregar fotos
- [ ] Descripción del negocio

#### 6.3 Optimización On-Page
- [ ] Verificar meta titles únicos por página
- [ ] Verificar meta descriptions
- [ ] Agregar alt text a imágenes
- [ ] Verificar headings (H1, H2, H3)
- [ ] Crear sitemap.xml
- [ ] Crear robots.txt

---

### FASE 7: LANZAMIENTO Y PROMOCIÓN (DÍA 7)
**Tiempo estimado: Variable**

#### 7.1 Anuncio de Lanzamiento
- [ ] Email a base de contactos existente
- [ ] Post en LinkedIn (personal + empresa si tienes)
- [ ] Post en redes sociales
- [ ] WhatsApp a contactos relevantes
- [ ] Actualizar firma de email con link

#### 7.2 Networking
- [ ] Avisar a colegas del sector
- [ ] Pedir referencias a clientes actuales
- [ ] Conectar con socios estratégicos
- [ ] Unirse a grupos relevantes (LinkedIn, etc.)

#### 7.3 Primeras Campañas (Opcional)
- [ ] Google Ads (Search) - Presupuesto mínimo $300/mes
- [ ] LinkedIn Ads (si B2B) - Presupuesto $500-1000/mes
- [ ] Facebook/Instagram Ads - Presupuesto $200-500/mes
- [ ] Contenido orgánico en redes

---

## 📊 MÉTRICAS A MONITOREAR (DIARIAS - PRIMERA SEMANA)

### Tráfico
- [ ] Visitas totales
- [ ] Fuentes de tráfico (directo, redes, búsqueda)
- [ ] Páginas más visitadas
- [ ] Tasa de rebote
- [ ] Tiempo en sitio

### Conversiones
- [ ] Formularios completados
- [ ] Citas agendadas (Calendly)
- [ ] Clicks en WhatsApp
- [ ] Email popup capturados
- [ ] Tasa de conversión general

### Engagement
- [ ] Emails abiertos (open rate)
- [ ] Emails clickeados (click rate)
- [ ] Respuestas a emails
- [ ] Mensajes por WhatsApp

---

## 🎯 OBJETIVOS PRIMERAS 4 SEMANAS

### Semana 1:
- [ ] Mínimo 50 visitas al sitio
- [ ] Al menos 3 leads (cualquier canal)
- [ ] 1 reunión agendada

### Semana 2:
- [ ] 100+ visitas
- [ ] 5+ leads
- [ ] 2+ reuniones agendadas

### Semana 3-4:
- [ ] 150+ visitas/semana
- [ ] 8+ leads/semana
- [ ] 3+ reuniones/semana
- [ ] Primera propuesta enviada
- [ ] (Objetivo) Primer cliente cerrado

---

## 🚨 TROUBLESHOOTING - PROBLEMAS COMUNES

### "El formulario no envía"
- [ ] Verificar URL de Google Apps Script
- [ ] Verificar permisos del script
- [ ] Ver consola del navegador (F12)

### "Calendly no se abre"
- [ ] Verificar usuario de Calendly en código
- [ ] Verificar link activo
- [ ] Probar en incógnito

### "No llegan emails de notificación"
- [ ] Revisar carpeta spam
- [ ] Verificar email en script
- [ ] Verificar límites de Gmail (500/día)

### "Analytics no registra visitas"
- [ ] Verificar ID de medición
- [ ] Desactivar AdBlock
- [ ] Esperar 24-48h para datos completos

---

## 📞 CONTACTOS DE SOPORTE

### Técnico:
- Cloudflare: https://dash.cloudflare.com
- Google Analytics: https://support.google.com/analytics
- Calendly: https://help.calendly.com

### Marketing:
- Brevo: https://help.brevo.com
- Zapier: https://help.zapier.com

---

## ✅ CHECKLIST FINAL ANTES DE LANZAR

### Todo listo cuando puedas marcar:
- [ ] ✅ Sitio carga correctamente en dominio final
- [ ] ✅ Formulario envía a Google Sheets
- [ ] ✅ Email de bienvenida configurado
- [ ] ✅ Calendly funcionando
- [ ] ✅ WhatsApp funcionando
- [ ] ✅ Analytics rastreando
- [ ] ✅ Testeado en móvil
- [ ] ✅ Velocidad >90 en PageSpeed
- [ ] ✅ SSL activo (HTTPS)
- [ ] ✅ Equipo entrenado para responder leads
- [ ] ✅ Proceso de seguimiento definido

---

## 🎉 ¡LISTO PARA LANZAR!

**Cuando todos los checks estén completos:**

1. Haz un último test completo
2. Respira profundo
3. Comparte el link
4. ¡Empieza a capturar leads!

---

**Próximo paso:** Descargar archivos y empezar con Fase 1 ⬇️

¿Necesitas ayuda con algo específico? ¡Adelante! 🚀
