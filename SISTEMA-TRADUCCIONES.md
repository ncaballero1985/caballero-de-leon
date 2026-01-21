# 🌍 SISTEMA DE TRADUCCIONES COMPLETO
## Caballero De León - ES / EN / PT

---

## 📝 INSTRUCCIONES

Los botones de idioma (ES/EN/PT) ya están en el navegador.
Este archivo contiene TODAS las traducciones necesarias para implementar el cambio de idioma.

---

## 🔧 IMPLEMENTACIÓN

### Paso 1: Agregar este script al final de cada página HTML (antes de </body>):

```javascript
<script>
    // Sistema de traducciones
    const translations = {
        es: {
            // Navegación
            nav_servicios: "Servicios",
            nav_metodo: "Método",
            nav_nosotros: "Nosotros",
            nav_faq: "FAQ",
            nav_contacto: "Contacto",
            nav_agendar: "Agendar consulta",
            
            // Hero
            hero_title: "Advisory Studio",
            hero_subtitle: "Acompañamos a personas de alto patrimonio y empresas exigentes en la gestión de activos, decisiones patrimoniales y procesos complejos. Con análisis claro, orden y experiencia de primera línea.",
            
            // Servicios
            servicios_title: "Servicios",
            servicios_intro: "Cuando el patrimonio crece —o cuando la operación se vuelve exigente— aparecen tres riesgos: desorden, costo oculto y decisiones sin información. Nuestro trabajo es reducir esos riesgos: ordenar la estructura, dar control y acompañar el proceso de decisión con una mirada integral.",
            
            service1_title: "Financial & Tax Advisory",
            service1_desc: "Acompañamiento en decisiones patrimoniales, estructuras fiscales eficientes, compraventa de activos y análisis de inversiones.",
            service1_link: "Conocer más →",
            
            service2_title: "Property & Asset Management",
            service2_desc: "Gestión integral de inmuebles, control de operaciones, negociación con proveedores y seguimiento de proyectos de obra.",
            service2_link: "Conocer más →",
            
            service3_title: "Architecture & Design Advisory",
            service3_desc: "Diseño de espacios, supervisión de obra, control de plazos y presupuestos en proyectos residenciales y comerciales.",
            service3_link: "Conocer más →",
            
            // Método
            metodo_title: "Cómo trabajamos",
            metodo_step1: "01 — Primera conversación",
            metodo_step1_desc: "Escuchamos la situación y entendemos qué necesita orden, qué genera dudas o qué requiere análisis.",
            metodo_step2: "02 — Propuesta de trabajo",
            metodo_step2_desc: "Presentamos un scope claro, con plazos, entregables y un modelo de honorarios transparente.",
            metodo_step3: "03 — Ejecución y acompañamiento",
            metodo_step3_desc: "Ejecutamos el plan acordado, mantenemos comunicación regular y adaptamos el proceso si surge algo nuevo.",
            metodo_step4: "04 — Entrega y seguimiento",
            metodo_step4_desc: "Entregamos el trabajo final, dejamos documentación ordenada y quedamos disponibles para consultas futuras.",
            
            // Calendly
            calendly_title: "Agenda tu consulta",
            calendly_intro: "Reserva una primera conversación de 30 minutos sin costo. Hablemos de tu situación y veamos cómo podemos ayudarte.",
            
            // Contacto
            contacto_title: "Conversemos",
            form_nombre: "Nombre completo *",
            form_email: "Email *",
            form_telefono: "Teléfono",
            form_servicio: "¿Qué servicio te interesa?",
            form_mensaje: "Mensaje *",
            form_submit: "Enviar consulta",
            form_success: "¡Gracias! Tu mensaje ha sido enviado. Te contactaremos pronto.",
            
            // Footer
            footer_desc: "Advisory Studio especializado en gestión patrimonial, inmobiliaria y arquitectónica.",
            footer_servicios: "Servicios",
            footer_contacto: "Contacto",
            footer_empresa: "Empresa",
            footer_copyright: "© 2025 Caballero De León. Todos los derechos reservados."
        },
        
        en: {
            // Navigation
            nav_servicios: "Services",
            nav_metodo: "Method",
            nav_nosotros: "About",
            nav_faq: "FAQ",
            nav_contacto: "Contact",
            nav_agendar: "Schedule consultation",
            
            // Hero
            hero_title: "Advisory Studio",
            hero_subtitle: "We support high-net-worth individuals and demanding companies in asset management, wealth decisions, and complex processes. With clear analysis, order, and first-class experience.",
            
            // Services
            servicios_title: "Services",
            servicios_intro: "When wealth grows—or when operations become demanding—three risks appear: disorder, hidden costs, and decisions without information. Our job is to reduce those risks: organize the structure, provide control, and support the decision-making process with a comprehensive view.",
            
            service1_title: "Financial & Tax Advisory",
            service1_desc: "Support in wealth decisions, efficient tax structures, asset buying and selling, and investment analysis.",
            service1_link: "Learn more →",
            
            service2_title: "Property & Asset Management",
            service2_desc: "Comprehensive real estate management, operations control, supplier negotiation, and construction project monitoring.",
            service2_link: "Learn more →",
            
            service3_title: "Architecture & Design Advisory",
            service3_desc: "Space design, construction supervision, schedule and budget control in residential and commercial projects.",
            service3_link: "Learn more →",
            
            // Method
            metodo_title: "How we work",
            metodo_step1: "01 — First conversation",
            metodo_step1_desc: "We listen to the situation and understand what needs order, what generates doubts, or what requires analysis.",
            metodo_step2: "02 — Work proposal",
            metodo_step2_desc: "We present a clear scope, with deadlines, deliverables, and a transparent fee model.",
            metodo_step3: "03 — Execution and support",
            metodo_step3_desc: "We execute the agreed plan, maintain regular communication, and adapt the process if something new arises.",
            metodo_step4: "04 — Delivery and follow-up",
            metodo_step4_desc: "We deliver the final work, leave organized documentation, and remain available for future consultations.",
            
            // Calendly
            calendly_title: "Schedule your consultation",
            calendly_intro: "Book a 30-minute first conversation at no cost. Let's talk about your situation and see how we can help.",
            
            // Contact
            contacto_title: "Let's talk",
            form_nombre: "Full name *",
            form_email: "Email *",
            form_telefono: "Phone",
            form_servicio: "Which service are you interested in?",
            form_mensaje: "Message *",
            form_submit: "Send inquiry",
            form_success: "Thank you! Your message has been sent. We will contact you soon.",
            
            // Footer
            footer_desc: "Advisory Studio specialized in wealth, real estate, and architectural management.",
            footer_servicios: "Services",
            footer_contacto: "Contact",
            footer_empresa: "Company",
            footer_copyright: "© 2025 Caballero De León. All rights reserved."
        },
        
        pt: {
            // Navegação
            nav_servicios: "Serviços",
            nav_metodo: "Método",
            nav_nosotros: "Sobre nós",
            nav_faq: "FAQ",
            nav_contacto: "Contato",
            nav_agendar: "Agendar consulta",
            
            // Hero
            hero_title: "Advisory Studio",
            hero_subtitle: "Acompanhamos pessoas de alto patrimônio e empresas exigentes na gestão de ativos, decisões patrimoniais e processos complexos. Com análise clara, ordem e experiência de primeira linha.",
            
            // Serviços
            servicios_title: "Serviços",
            servicios_intro: "Quando o patrimônio cresce—ou quando a operação se torna exigente—aparecem três riscos: desordem, custo oculto e decisões sem informação. Nosso trabalho é reduzir esses riscos: ordenar a estrutura, dar controle e acompanhar o processo de decisão com uma visão integral.",
            
            service1_title: "Financial & Tax Advisory",
            service1_desc: "Acompanhamento em decisões patrimoniais, estruturas fiscais eficientes, compra e venda de ativos e análise de investimentos.",
            service1_link: "Saiba mais →",
            
            service2_title: "Property & Asset Management",
            service2_desc: "Gestão integral de imóveis, controle de operações, negociação com fornecedores e acompanhamento de projetos de obra.",
            service2_link: "Saiba mais →",
            
            service3_title: "Architecture & Design Advisory",
            service3_desc: "Design de espaços, supervisão de obras, controle de prazos e orçamentos em projetos residenciais e comerciais.",
            service3_link: "Saiba mais →",
            
            // Método
            metodo_title: "Como trabalhamos",
            metodo_step1: "01 — Primeira conversa",
            metodo_step1_desc: "Ouvimos a situação e entendemos o que precisa de ordem, o que gera dúvidas ou o que requer análise.",
            metodo_step2: "02 — Proposta de trabalho",
            metodo_step2_desc: "Apresentamos um escopo claro, com prazos, entregas e um modelo de honorários transparente.",
            metodo_step3: "03 — Execução e acompanhamento",
            metodo_step3_desc: "Executamos o plano acordado, mantemos comunicação regular e adaptamos o processo se surgir algo novo.",
            metodo_step4: "04 — Entrega e acompanhamento",
            metodo_step4_desc: "Entregamos o trabalho final, deixamos documentação organizada e ficamos disponíveis para consultas futuras.",
            
            // Calendly
            calendly_title: "Agende sua consulta",
            calendly_intro: "Reserve uma primeira conversa de 30 minutos sem custo. Vamos falar sobre sua situação e ver como podemos ajudar.",
            
            // Contato
            contacto_title: "Vamos conversar",
            form_nombre: "Nome completo *",
            form_email: "Email *",
            form_telefono: "Telefone",
            form_servicio: "Qual serviço te interessa?",
            form_mensaje: "Mensagem *",
            form_submit: "Enviar consulta",
            form_success: "Obrigado! Sua mensagem foi enviada. Entraremos em contato em breve.",
            
            // Footer
            footer_desc: "Advisory Studio especializado em gestão patrimonial, imobiliária e arquitetônica.",
            footer_servicios: "Serviços",
            footer_contacto: "Contato",
            footer_empresa: "Empresa",
            footer_copyright: "© 2025 Caballero De León. Todos os direitos reservados."
        }
    };
    
    // Función para cambiar idioma
    function setLang(lang) {
        // Actualizar botones activos
        document.querySelectorAll('.lang button').forEach(btn => btn.classList.remove('active'));
        event.target.classList.add('active');
        
        // Guardar preferencia
        localStorage.setItem('preferred_lang', lang);
        
        // Aplicar traducciones
        const t = translations[lang];
        
        // Actualizar todos los elementos con data-translate
        document.querySelectorAll('[data-translate]').forEach(el => {
            const key = el.getAttribute('data-translate');
            if (t[key]) {
                if (el.tagName === 'INPUT' || el.tagName === 'TEXTAREA') {
                    el.placeholder = t[key];
                } else {
                    el.textContent = t[key];
                }
            }
        });
    }
    
    // Cargar idioma guardado al cargar la página
    window.addEventListener('DOMContentLoaded', () => {
        const savedLang = localStorage.getItem('preferred_lang');
        if (savedLang && savedLang !== 'es') {
            // Simular click en botón del idioma guardado
            const btn = document.querySelector(`.lang button[onclick*="${savedLang}"]`);
            if (btn) {
                btn.click();
            }
        }
    });
</script>
```

---

## 📋 CÓMO USAR LAS TRADUCCIONES

### Paso 2: Agregar atributo `data-translate` a los elementos HTML

Para que un texto se traduzca automáticamente, agregar el atributo `data-translate="clave"`:

**Ejemplos:**

```html
<!-- Navegación -->
<li><a href="#servicios" data-translate="nav_servicios">Servicios</a></li>
<li><a href="#metodo" data-translate="nav_metodo">Método</a></li>

<!-- Títulos -->
<h1 data-translate="hero_title">Advisory Studio</h1>
<h2 data-translate="servicios_title">Servicios</h2>

<!-- Párrafos -->
<p data-translate="hero_subtitle">Acompañamos a personas...</p>

<!-- Botones -->
<button type="submit" data-translate="form_submit">Enviar consulta</button>

<!-- Inputs (traduce placeholder) -->
<input type="text" data-translate="form_nombre" placeholder="Nombre completo *">
```

---

## 🎯 PÁGINAS PENDIENTES DE ACTUALIZAR

Para implementar las traducciones completamente, necesitas:

### 1. index.html ✅
- Agregar atributos `data-translate` a los elementos
- El script ya está incluido

### 2. nosotros.html ✅
- Agregar atributos `data-translate`
- Script agregado

### 3. Otras páginas
- preguntas-frecuentes.html
- financial-tax-advisory.html
- property-asset-management.html
- architecture-design-advisory.html

---

## 📝 EJEMPLO COMPLETO

### Antes:
```html
<h2>Servicios</h2>
<p>Cuando el patrimonio crece...</p>
```

### Después:
```html
<h2 data-translate="servicios_title">Servicios</h2>
<p data-translate="servicios_intro">Cuando el patrimonio crece...</p>
```

---

## 💡 VENTAJAS DE ESTE SISTEMA

- ✅ Traducciones guardadas en localStorage (persistente)
- ✅ Cambio instantáneo sin recargar página
- ✅ Fácil de expandir (agregar más idiomas)
- ✅ No requiere servidor ni backend
- ✅ SEO-friendly (contenido base en español)

---

## 🚀 IMPLEMENTACIÓN RÁPIDA

Si quieres implementar rápido:

1. Copia el script completo
2. Pégalo antes de `</body>` en cada página
3. Agrega `data-translate="clave"` solo a los textos principales:
   - Navegación
   - Títulos (H1, H2, H3)
   - CTAs (botones)
   - Formularios

**Textos secundarios pueden quedarse sin traducir inicialmente.**

---

## ✅ ESTADO ACTUAL

- ✅ Botones de idioma agregados a navegación
- ✅ Estructura de traducciones completa (ES/EN/PT)
- ✅ Script funcional listo para usar
- ⚠️ Pendiente: Agregar `data-translate` a elementos HTML

**Tiempo estimado para completar:** 30-45 minutos

---

¿Necesitas ayuda para implementar? Avísame y puedo generar los archivos HTML con las traducciones ya aplicadas.
