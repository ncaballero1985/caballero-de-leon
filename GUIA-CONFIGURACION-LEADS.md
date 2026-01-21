# 🎯 GUÍA COMPLETA: SISTEMA DE CAPTURA DE LEADS
## Caballero De León - Advisory Studio

---

## 📋 ÍNDICE
1. Configuración de Calendly
2. Configuración de Google Sheets (Leads Database)
3. Configuración de Google Analytics
4. Configuración de Meta Pixel (Facebook)
5. Sistema de Email Marketing
6. Pipeline de Automatización con Zapier/Make
7. Checklist final antes de lanzar

---

## 1️⃣ CONFIGURACIÓN DE CALENDLY

### Paso 1: Crear cuenta en Calendly
1. Ve a https://calendly.com
2. Crea cuenta gratuita (o Pro si quieres más funciones)
3. Configura tu disponibilidad horaria

### Paso 2: Crear tipo de evento
1. Crea un evento llamado "Primera Consulta"
2. Duración: 30 minutos
3. Descripción: "Primera conversación sin costo para conocer tu situación"
4. Ubicación: Google Meet o Zoom

### Paso 3: Personalizar
1. **Preguntas personalizadas** (muy importante para calificar leads):
   - Nombre completo
   - Email
   - Teléfono
   - ¿Qué servicio te interesa? (Financial, Property, Architecture)
   - ¿Cuál es tu principal desafío actualmente?
   - ¿Cómo nos conociste?

### Paso 4: Integrar en tu web
1. En Calendly, ve a tu evento → "Copy link"
2. Tu link será algo como: `https://calendly.com/tu-usuario/30min`
3. Reemplaza en el código HTML línea 221 y 369:
   ```javascript
   data-url="https://calendly.com/TU-USUARIO/30min"
   ```

### Paso 5: Configurar notificaciones
- Email confirmación → Cliente
- Email recordatorio → 24h antes y 1h antes
- Notificación a ti cuando alguien agenda

---

## 2️⃣ GOOGLE SHEETS - BASE DE DATOS DE LEADS

### Paso 1: Crear la hoja de cálculo
1. Ve a https://sheets.google.com
2. Crea nueva hoja llamada "Leads - Caballero De León"
3. Columnas (fila 1):
   - A: Timestamp
   - B: Nombre
   - C: Email
   - D: Teléfono
   - E: Servicio
   - F: Mensaje
   - G: Origen (formulario/exit-popup/calendly)
   - H: Estado (Nuevo/Contactado/Calificado/Propuesta/Cerrado/Perdido)
   - I: Notas
   - J: Próximo seguimiento

### Paso 2: Crear Google Apps Script
1. En tu hoja, ve a **Extensiones → Apps Script**
2. Borra todo el código y pega esto:

```javascript
function doPost(e) {
  try {
    var sheet = SpreadsheetApp.getActiveSpreadsheet().getActiveSheet();
    var params = e.parameter;
    
    // Obtener valores del formulario
    var timestamp = new Date();
    var nombre = params.nombre || '';
    var email = params.email || '';
    var telefono = params.telefono || '';
    var servicio = params.servicio || '';
    var mensaje = params.mensaje || '';
    var origen = params.tipo || 'formulario-web';
    
    // Agregar fila
    sheet.appendRow([
      timestamp,
      nombre,
      email,
      telefono,
      servicio,
      mensaje,
      origen,
      'Nuevo', // Estado inicial
      '', // Notas vacías
      '' // Próximo seguimiento vacío
    ]);
    
    // OPCIONAL: Enviar email de notificación a ti
    MailApp.sendEmail({
      to: "tu-email@gmail.com", // CAMBIA ESTO
      subject: "🎯 Nuevo Lead - " + nombre,
      body: "Nombre: " + nombre + "\nEmail: " + email + "\nTeléfono: " + telefono + 
            "\nServicio: " + servicio + "\nMensaje: " + mensaje
    });
    
    return ContentService.createTextOutput(JSON.stringify({result: 'success'}))
      .setMimeType(ContentService.MimeType.JSON);
      
  } catch(error) {
    return ContentService.createTextOutput(JSON.stringify({result: 'error', error: error}))
      .setMimeType(ContentService.MimeType.JSON);
  }
}
```

### Paso 3: Publicar el script
1. Haz clic en **Implementar → Nueva implementación**
2. Tipo: Aplicación web
3. Ejecutar como: **Yo** (tu cuenta)
4. Quién tiene acceso: **Cualquier persona**
5. Haz clic en **Implementar**
6. **COPIA LA URL** que te da (Web App URL)
7. Pega esta URL en el código HTML línea 332:
   ```javascript
   const scriptURL = 'TU_WEB_APP_URL_AQUÍ';
   ```

---

## 3️⃣ GOOGLE ANALYTICS

### Paso 1: Crear cuenta
1. Ve a https://analytics.google.com
2. Crea cuenta → Propiedad → Web
3. Nombre: Caballero De León
4. URL: tu dominio

### Paso 2: Obtener ID de medición
1. Copia tu ID (formato: G-XXXXXXXXXX)
2. Reemplaza en líneas 12 y 15 del HTML:
   ```javascript
   gtag('config', 'G-XXXXXXXXXX');
   ```

### Paso 3: Configurar eventos importantes
Ya están configurados en el código:
- ✅ PageView automático
- ✅ Click en WhatsApp
- ✅ Apertura de Calendly
- ✅ Envío de formulario
- ✅ Exit popup mostrado
- ✅ Exit popup email enviado

---

## 4️⃣ META PIXEL (FACEBOOK ADS)

### Paso 1: Crear Pixel
1. Ve a https://business.facebook.com
2. Configuración de eventos → Pixels
3. Crear pixel → Copia el ID

### Paso 2: Implementar
1. Reemplaza en línea 24:
   ```javascript
   fbq('init', 'TU_PIXEL_ID');
   ```

### Eventos que se trackean:
- ✅ PageView
- ✅ Schedule (cuando abren Calendly)
- ✅ Lead (formulario y exit popup)

---

## 5️⃣ EMAIL MARKETING - BREVO (ex-Sendinblue)

### Opción A: Brevo (GRATIS hasta 300 emails/día)
1. Crea cuenta en https://www.brevo.com
2. Crea lista "Leads - Caballero De León"
3. Crea workflow de bienvenida:
   - Email 1: Inmediato - "Gracias por tu interés"
   - Email 2: +2 días - "Casos de éxito"
   - Email 3: +5 días - "Agenda una llamada"
   - Email 4: +10 días - "Oferta especial"

### Opción B: Mailchimp (GRATIS hasta 500 contactos)
Similar a Brevo, con más plantillas visuales

### Secuencia de emails sugerida:

**Email 1 - Inmediato:**
```
Asunto: Gracias por contactarnos, [Nombre]

Hola [Nombre],

Recibimos tu mensaje y nos comunicaremos contigo en las próximas 24 horas.

Mientras tanto, te invito a conocer más sobre cómo trabajamos:
[Link a casos de éxito]

Saludos,
El equipo de Caballero De León
```

**Email 2 - +2 días:**
```
Asunto: ¿Cómo ordenamos el patrimonio de familia X?

[Caso de estudio relevante al servicio que seleccionó]
```

**Email 3 - +5 días:**
```
Asunto: ¿Tienes 15 minutos esta semana?

[CTA para agendar llamada]
```

---

## 6️⃣ AUTOMATIZACIÓN CON ZAPIER/MAKE

### Opción A: Zapier (más fácil)
1. Crea cuenta en https://zapier.com
2. Crea Zap:
   - **Trigger:** New row in Google Sheets
   - **Actions:**
     - Enviar email (Gmail/Brevo)
     - Agregar a lista de email marketing
     - Crear tarea en Trello/Asana
     - Notificación a Slack (si usas)
     - Enviar WhatsApp (con Twilio API)

### Opción B: Make.com (más potente)
Similar pero con más opciones de lógica

### Flujo recomendado:
```
Lead llega → Google Sheets → 
  ├─ Email automático de bienvenida
  ├─ Agregar a lista de email marketing
  ├─ Crear tarea "Contactar en 24h" en tu CRM
  └─ Notificación a WhatsApp Business API (opcional)
```

---

## 7️⃣ PIPELINE DE VENTAS SUGERIDO

### Estados del lead:
1. **Nuevo** - Acaba de llegar
2. **Contactado** - Ya hablaste con él
3. **Calificado** - Es un buen prospecto
4. **Propuesta enviada** - Enviaste cotización
5. **Negociación** - Está en proceso
6. **Cerrado-Ganado** - ¡Cliente nuevo!
7. **Cerrado-Perdido** - No se concretó

### Tiempos de seguimiento:
- Lead nuevo → Contactar en 2-4 horas
- Sin respuesta → Re-contactar en 2 días
- Propuesta enviada → Seguimiento en 3 días
- Después de 3 intentos sin respuesta → Mover a "Nutrición"

---

## 8️⃣ HERRAMIENTAS ADICIONALES RECOMENDADAS

### CRM Gratuito:
- **HubSpot** (Free) - El más completo
- **Zoho CRM** (Free) - Buena opción
- **Google Sheets** - Si prefieres simple

### WhatsApp Business API:
- **Twilio** - Para automatizar mensajes
- **Wati** - Especializado en WhatsApp
- Solo WhatsApp Business App - Manual pero gratis

### Analytics:
- **Hotjar** - Mapas de calor (ver dónde hacen click)
- **Microsoft Clarity** - Gratis, similar a Hotjar

---

## 9️⃣ CHECKLIST ANTES DE LANZAR

### Configuración técnica:
- [ ] Calendly configurado y testeado
- [ ] Google Sheets recibiendo datos correctamente
- [ ] Google Analytics instalado
- [ ] Meta Pixel instalado (si harás ads)
- [ ] Formulario probado y funcionando
- [ ] WhatsApp funcionando
- [ ] Exit popup funcionando

### Contenido:
- [ ] Email de bienvenida escrito
- [ ] Secuencia de nurturing lista (3-5 emails)
- [ ] Respuestas rápidas en WhatsApp preparadas
- [ ] Guía gratuita del exit popup lista (PDF)

### Proceso interno:
- [ ] Definir quién responde leads (horarios)
- [ ] Template de respuesta inicial
- [ ] Proceso de calificación definido
- [ ] Propuesta tipo lista
- [ ] Sistema de seguimiento (alarmas/recordatorios)

---

## 🎯 MÉTRICAS A TRACKEAR

### Semanalmente:
- Leads totales
- Leads por canal (web form / calendly / whatsapp / exit popup)
- Tasa de conversión form → respuesta
- Tasa de conversión respuesta → reunión
- Tasa de conversión reunión → cliente

### Mensualmente:
- Costo por lead (si haces ads)
- Valor promedio de cliente
- ROI de marketing
- Tasa de cierre

---

## 📞 SOPORTE

Si necesitas ayuda técnica:
- Google Sheets: https://support.google.com/docs
- Calendly: https://help.calendly.com
- Zapier: https://help.zapier.com
- Brevo: https://help.brevo.com

---

## 🚀 PRÓXIMOS PASOS INMEDIATOS

1. **HOY:**
   - Configurar Calendly
   - Configurar Google Sheets + Apps Script
   - Probar que el formulario funcione

2. **MAÑANA:**
   - Configurar Google Analytics
   - Configurar email de bienvenida
   - Escribir secuencia de nurturing

3. **ESTA SEMANA:**
   - Crear flujo en Zapier/Make
   - Preparar propuesta tipo
   - Definir proceso de seguimiento
   - Lanzar sitio!

---

**¡Todo listo para no perder ningún lead! 🎯**

Cualquier duda sobre la implementación, avísame.
