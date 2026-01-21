# 🚀 ACTUALIZACIÓN RÁPIDA - Agregar Sistema de Leads

## Ya tengo tu código de Calendly:
```html
<div class="calendly-inline-widget" data-url="https://calendly.com/noel-caballerodeleon/30min" style="min-width:320px;height:700px;"></div>
<script type="text/javascript" src="https://assets.calendly.com/assets/external/widget.js" async></script>
```

---

## 📋 CAMBIOS A HACER EN TU index.html ACTUAL

### 1️⃣ AGREGAR EN EL <head> (después de la línea 7):

```html
    <!-- Google Analytics - REEMPLAZA CON TU ID -->
    <script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
    <script>
        window.dataLayer = window.dataLayer || [];
        function gtag(){dataLayer.push(arguments);}
        gtag('js', new Date());
        gtag('config', 'G-XXXXXXXXXX');
    </script>
```

### 2️⃣ AGREGAR ESTILOS AL FINAL DEL <style> (antes de </style>):

```css
        /* Exit Intent Popup */
        .exit-popup { display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.8); z-index: 9999; align-items: center; justify-content: center; }
        .exit-popup.active { display: flex; }
        .exit-popup-content { background: white; padding: 3rem; max-width: 500px; text-align: center; position: relative; animation: slideDown 0.3s ease; }
        .exit-popup-close { position: absolute; top: 1rem; right: 1rem; background: none; border: none; font-size: 1.5rem; cursor: pointer; color: var(--gris-medio); }
        .exit-popup h3 { font-family: 'Georgia', serif; font-size: 1.8rem; margin-bottom: 1rem; color: var(--negro); }
        .exit-popup p { color: var(--gris-oscuro); margin-bottom: 2rem; }
        .exit-popup input { width: 100%; margin-bottom: 1rem; padding: 1rem; border: 1px solid var(--gris-claro); }
        @keyframes slideDown { from { transform: translateY(-50px); opacity: 0; } to { transform: translateY(0); opacity: 1; } }
        
        /* Success Message */
        .success-message { display: none; background: #4CAF50; color: white; padding: 1rem; text-align: center; margin-top: 1rem; }
        .success-message.show { display: block; }
        
        /* Calendly Section */
        .calendly-section { background: white; padding: 4rem 3rem; margin: 4rem 0; }
```

### 3️⃣ ACTUALIZAR EL BOTÓN "AGENDAR CONSULTA" EN EL NAV:

Busca (línea ~108):
```html
<li><a href="#agendar" class="btn-agendar">Agendar consulta</a></li>
```

Reemplazar con:
```html
<li><a href="#agendar" class="btn-agendar" onclick="document.getElementById('agendar').scrollIntoView({behavior:'smooth'}); return false;">Agendar consulta</a></li>
```

### 4️⃣ AGREGAR SECCIÓN CALENDLY (después de la sección #metodo, antes de #contacto):

```html
    <!-- SECCIÓN CALENDLY -->
    <section id="agendar" class="calendly-section">
        <h2>Agenda tu consulta</h2>
        <p class="intro-text">Reserva una primera conversación de 30 minutos sin costo. Hablemos de tu situación y veamos cómo podemos ayudarte.</p>
        <!-- Calendly inline widget begin -->
        <div class="calendly-inline-widget" data-url="https://calendly.com/noel-caballerodeleon/30min" style="min-width:320px;height:700px;"></div>
        <script type="text/javascript" src="https://assets.calendly.com/assets/external/widget.js" async></script>
        <!-- Calendly inline widget end -->
    </section>
```

### 5️⃣ ACTUALIZAR EL FORMULARIO DE CONTACTO:

Busca el formulario actual (línea ~177) y reemplázalo con:

```html
            <form id="contactForm">
                <div class="form-group">
                    <label for="nombre">Nombre completo *</label>
                    <input type="text" id="nombre" name="nombre" required>
                </div>
                <div class="form-group">
                    <label for="email">Email *</label>
                    <input type="email" id="email" name="email" required>
                </div>
                <div class="form-group">
                    <label for="telefono">Teléfono</label>
                    <input type="tel" id="telefono" name="telefono">
                </div>
                <div class="form-group">
                    <label for="servicio">¿Qué servicio te interesa?</label>
                    <select id="servicio" name="servicio">
                        <option value="">Seleccionar...</option>
                        <option value="Financial & Tax Advisory">Financial & Tax Advisory</option>
                        <option value="Property & Asset Management">Property & Asset Management</option>
                        <option value="Architecture & Design Advisory">Architecture & Design Advisory</option>
                        <option value="Consulta general">Consulta general</option>
                    </select>
                </div>
                <div class="form-group">
                    <label for="mensaje">Mensaje *</label>
                    <textarea id="mensaje" name="mensaje" required></textarea>
                </div>
                <button type="submit">Enviar consulta</button>
                <div id="successMessage" class="success-message">
                    ¡Gracias! Tu mensaje ha sido enviado. Te contactaremos pronto.
                </div>
            </form>
```

### 6️⃣ ACTUALIZAR WHATSAPP (busca línea ~208):

```html
    <a href="https://wa.me/59893941111?text=Hola,%20estoy%20interesado%20en%20sus%20servicios" 
       class="whatsapp-btn" 
       target="_blank"
       onclick="gtag('event', 'click', {'event_category': 'WhatsApp', 'event_label': 'Floating Button'});">
        💬
    </a>
```

### 7️⃣ AGREGAR EXIT POPUP (antes del </body>):

```html
    <!-- EXIT INTENT POPUP -->
    <div id="exitPopup" class="exit-popup">
        <div class="exit-popup-content">
            <button class="exit-popup-close" onclick="closeExitPopup()">×</button>
            <h3>¡Espera un momento!</h3>
            <p>Déjanos tu email y te enviaremos nuestra guía gratuita sobre "Cómo ordenar tu patrimonio en 5 pasos"</p>
            <form id="exitForm">
                <input type="email" id="exitEmail" placeholder="Tu email" required>
                <button type="submit" style="width: 100%; padding: 1rem; background: var(--bronce); color: white; border: none; cursor: pointer;">Descargar guía gratuita</button>
            </form>
        </div>
    </div>
```

### 8️⃣ AGREGAR JAVASCRIPT (antes del </body>):

```html
    <script>
        // FORMULARIO DE CONTACTO - ENVÍO A GOOGLE SHEETS
        const scriptURL = 'TU_WEB_APP_URL_DE_GOOGLE_SHEETS'; // Ver GUIA-CONFIGURACION-LEADS.md
        const form = document.getElementById('contactForm');
        const successMessage = document.getElementById('successMessage');
        
        form.addEventListener('submit', e => {
            e.preventDefault();
            
            // Track conversión
            if (typeof gtag !== 'undefined') {
                gtag('event', 'conversion', {
                    'event_category': 'Form',
                    'event_label': 'Contact Form Submit'
                });
            }
            
            // Enviar a Google Sheets
            fetch(scriptURL, { 
                method: 'POST', 
                body: new FormData(form)
            })
            .then(response => {
                successMessage.classList.add('show');
                form.reset();
                setTimeout(() => {
                    successMessage.classList.remove('show');
                }, 5000);
            })
            .catch(error => console.error('Error!', error.message));
        });
        
        // EXIT INTENT POPUP
        let exitPopupShown = false;
        document.addEventListener('mouseleave', function(e) {
            if (e.clientY <= 0 && !exitPopupShown) {
                document.getElementById('exitPopup').classList.add('active');
                exitPopupShown = true;
                if (typeof gtag !== 'undefined') {
                    gtag('event', 'show', {
                        'event_category': 'Exit Popup',
                        'event_label': 'Displayed'
                    });
                }
            }
        });
        
        function closeExitPopup() {
            document.getElementById('exitPopup').classList.remove('active');
        }
        
        // EXIT POPUP FORM
        document.getElementById('exitForm').addEventListener('submit', function(e) {
            e.preventDefault();
            const email = document.getElementById('exitEmail').value;
            
            // Guardar en Google Sheets
            fetch(scriptURL, {
                method: 'POST',
                body: new URLSearchParams({
                    'email': email,
                    'tipo': 'exit-popup',
                    'fecha': new Date().toISOString()
                })
            });
            
            // Track conversión
            if (typeof gtag !== 'undefined') {
                gtag('event', 'conversion', {
                    'event_category': 'Exit Popup',
                    'event_label': 'Email Submitted'
                });
            }
            
            alert('¡Gracias! Revisa tu email en unos minutos.');
            closeExitPopup();
        });
    </script>
```

---

## ✅ RESUMEN DE CAMBIOS

- ✅ Calendly ya configurado con tu cuenta: `noel-caballerodeleon`
- ✅ Google Analytics listo (solo falta tu ID)
- ✅ Formulario mejorado que envía a Google Sheets
- ✅ WhatsApp optimizado con mensaje pre-cargado
- ✅ Exit popup para capturar emails
- ✅ Tracking de eventos

---

## 🚀 SIGUIENTE PASO

1. Aplica estos cambios al index.html
2. Configura Google Sheets (ver GUIA-CONFIGURACION-LEADS.md)
3. Obtén tu ID de Google Analytics
4. ¡Sube a Cloudflare!

**¿Quieres que te genere el archivo HTML completo ya con todo aplicado?**
Dime y lo creo en 2 minutos. 😉
