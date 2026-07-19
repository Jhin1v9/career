# Landing Page Creator

## Estado

Producto interno · Desarrollo activo · Desplegado en VPS

---

# ¿Qué es Landing Page Creator?

Landing Page Creator es una plataforma que genera landing pages completas a partir de una conversación con inteligencia artificial.

Describes la página que necesitas y el sistema la construye paso a paso delante de ti: analiza tu intención, diseña la estructura, escribe el código y revisa su propio trabajo antes de entregarlo.

Pero lo que la hace especial no es solo generar páginas.

Es lo que ocurre después.

---

# El problema

En NEXO Digital, crear landing pages es una necesidad constante.

Para nosotros y para nuestros clientes.

Y cada landing page significaba repetir el mismo ciclo: montar el proyecto, estructurar secciones, escribir textos, ajustar estilos, preparar el despliegue.

Era trabajo real, pero también era trabajo repetido.

Me hice la pregunta de siempre:

> ¿Tiene sentido seguir haciendo esto a mano cada vez?

---

# Cómo funciona la generación

El sistema ejecuta un pipeline de 4 fases con IA, con streaming en tiempo real (SSE) para que veas la página construirse:

1. **Intención:** interpreta tu descripción y produce un brief estructurado.
2. **Estructura:** define el diseño — colores, tipografía, secciones — como tokens de diseño.
3. **Código:** genera la página completa en un único HTML con Tailwind.
4. **Revisión:** un paso de QA donde la propia IA evalúa el resultado antes de entregarlo.

Todo el proceso es resistente a fallos: reintentos, continuación automática cuando el modelo responde algo inesperado y rollback a la última versión válida de la página.

La IA funciona a través del mismo puente que Luna: modelos de lenguaje potentes operados por el navegador, sin depender de APIs de pago.

---

# El ciclo completo: de tu página a plantilla reutilizable

Esta es la parte que más me gusta del proyecto.

Cuando decides publicar tu landing page, empieza un segundo pipeline:

1. **Sanitización con IA:** Luna analiza tu página y elimina todo lo personal — nombres, correos, teléfonos, logotipos, marca — sustituyéndolos por marcadores genéricos, sin tocar el diseño.
2. **QA técnico y refinado:** si la revisión encuentra problemas, el sistema los corrige y genera la metadata de la plantilla: categoría, etiquetas, características, casos de uso.
3. **Publicación en NEXO Store:** la plantilla sanitizada viaja automáticamente a nuestra tienda, con su miniatura generada por screenshot, lista para que otros la reutilicen.

Y si la IA falla en algún paso, el sistema no se rompe: aplica una sanitización determinística de respaldo y publica la plantilla como "sin revisar", a mitad de precio.

El resultado es un ciclo que se retroalimenta: cuanta más gente crea páginas, más plantillas existen; cuantas más plantillas existen, más útil es la plataforma.

---

# La economía interna

La plataforma tiene su propio sistema de tres monedas virtuales —estrellas, soles y lunas— con cambio entre ellas.

Generar páginas cuesta monedas. Publicar cuesta monedas. Y comprar la plantilla de otra persona también.

Cuando alguien compra una plantilla, la venta se registra y se notifica al sistema financiero de la empresa, y el comprador desbloquea tanto la plantilla como el prompt original que la generó.

---

# Qué aprendí

Este proyecto me enseñó que la IA generativa es solo la mitad del problema.

La otra mitad es todo lo que la rodea: comprobar que el resultado funciona, proteger los datos personales de los usuarios, convertir cada creación en un activo reutilizable y hacer que el sistema se degrade con elegancia en lugar de romperse.

También aprendí a documentar mis propios errores: este proyecto pasó por una auditoría completa donde encontré y corregí decisiones mal tomadas en versiones anteriores. Esa cultura de revisión honesta es hoy parte de cómo trabajo.

---

# Tecnologías utilizadas

* Node.js + Express (unas 70 rutas de API).
* SQLite con 19 migraciones.
* Svelte 4 + Vite + Tailwind CSS.
* Server-Sent Events (streaming en tiempo real).
* Automatización de navegador con Playwright/CDP (puente con modelos de lenguaje).
* Sistema de economía virtual multi-moneda.
* Integración con la API de NEXO Store.
* Jest + Supertest + Playwright (unos 300 tests).
* Docker, PM2.

Unas 53.000 líneas de código.

---

# Mi papel

* Idea original.
* Diseño del producto y de la economía interna.
* Arquitectura del pipeline de generación y sanitización.
* Desarrollo completo (backend, frontend, tests).
* Integración con NEXO Store.
* Despliegue y operación en VPS.

---

# Qué representa este proyecto

Landing Page Creator representa mi forma de atacar el trabajo repetitivo.

Cuando algo se hace varias veces, merece convertirse en herramienta.

Y cuando esa herramienta además protege a sus usuarios, aprende de cada creación y convierte el trabajo de uno en valor para todos, deja de ser un simple generador.

Se convierte en plataforma.
