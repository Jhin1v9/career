# Dashboard NEXO

## Estado

Producto interno · En producción, en uso diario

---

# ¿Qué es Dashboard NEXO?

Dashboard NEXO es el sistema operativo de NEXO Digital.

Es la plataforma que centraliza prácticamente todo el funcionamiento diario de la empresa: clientes, leads, finanzas, tareas, e-mail, archivos de proyectos, votaciones y automatizaciones.

No es un proyecto que hice para aprender.

Es la herramienta con la que gestionamos la empresa de verdad, todos los días, desplegada en producción.

---

# El problema

Cuando la empresa empezó a crecer, cada nuevo proyecto generaba más ideas, tareas, clientes, reuniones, documentos y pequeños procesos repartidos entre distintas aplicaciones.

Llegó un momento en el que organizar el trabajo costaba casi tanto como hacer el trabajo.

Además, las herramientas existentes nos obligaban a cambiar nuestra forma de trabajar.

Yo quería exactamente lo contrario: construir una herramienta que se adaptara a nosotros.

---

# Qué hace hoy

El Dashboard creció como un ecosistema modular. Cada módulo nació de una necesidad real:

* **Finanzas completas:** pagos con reparto de ingresos entre miembros y multi-moneda, gastos recurrentes, caja con proyección de flujo, extracto, conciliación y alertas de saldo bajo.
* **CRM de ventas:** captura pública de leads con protección contra spam, pipeline de conversión de lead a cliente y seguimiento de presupuestos.
* **Tareas y colaboración:** tareas personales y de empresa con comentarios y menciones que notifican al equipo.
* **NEXO Mail:** e-mail integrado con Gmail (OAuth), con IA que sugiere respuestas, crea borradores, resume correos y convierte action items en tareas.
* **Gestor de archivos por cliente**, con posibilidad de arrancar y parar los servidores de los proyectos viendo los logs en tiempo real.
* **Banco de ideas** con bloques estilo Notion, roadmaps, votaciones internas, hub de enlaces con vista previa.
* **Auditoría completa:** todo cambio queda registrado, con papelera, restauración y deshacer/rehacer.
* **Notificaciones inteligentes** por Telegram y Discord, con trabajos programados (alertas financieras, gastos recurrentes).

Todo se actualiza en tiempo real: cualquier escritura en la base de datos se transmite al instante a las pantallas abiertas.

---

# La sinergia con Luna

La característica que más me gusta del Dashboard es cómo trabaja junto con Luna.

Cuando estamos fuera o sin tiempo de abrir la plataforma, simplemente hablamos con Luna por Telegram en lenguaje natural:

* "Crea una tarea para mañana."
* "Registra este pago."
* "¿Qué pendientes tengo?"

Luna interpreta el mensaje y ejecuta la acción correspondiente dentro del Dashboard, como si fuéramos nosotros.

Y para las acciones más sensibles, diseñé un sistema de gobierno: las acciones autónomas de la IA se convierten en sesiones de votación, los tres socios votan desde Telegram y, si se aprueban, se ejecutan automáticamente. Todo queda auditado y es reversible.

La IA propone. Las personas deciden.

---

# Cómo está construido por dentro

* **Backend Node.js + Express** con unas 300 rutas de API REST y broadcast en tiempo real por WebSocket.
* **PostgreSQL** con 15 migraciones y unas 33 tablas, desplegado en producción (Render + Neon).
* **Autenticación JWT** con protección global de rutas, listas de IPs de confianza y CORS restringido.
* **84 tests de integración** con Jest y Supertest ejecutándose contra la base de datos real, cubriendo 19 dominios.
* **Seguridad activa:** detección de VPN/Tor/proxy en el inicio de sesión y fingerprinting del dispositivo.
* **Migración de datos sin downtime:** audité el esquema real del sistema anterior y migré 1.228 registros preservando toda la información.
* **Operación real:** 40 versiones publicadas en cinco semanas mientras el equipo lo usaba a diario.

---

# Mi aprendizaje

Este proyecto me enseñó la importancia de pensar en sistemas completos.

No se trataba únicamente de desarrollar pantallas.

Había que diseñar relaciones entre módulos, mantener una experiencia coherente y asegurar que todas las herramientas funcionaran juntas.

También aprendí que una buena herramienta interna puede ahorrar más tiempo que desarrollar una nueva funcionalidad para un cliente.

---

# Tecnologías utilizadas

* Node.js.
* Express.
* PostgreSQL.
* WebSocket / SSE.
* JWT + bcrypt.
* React (frontend compilado con Vite, PWA).
* Gmail API (OAuth2), IMAP/SMTP.
* Bot de Telegram, webhooks de Discord.
* Jest + Supertest.
* Zod.
* node-cron.
* PM2.
* Git.

---

# Mi papel

* Diseño del producto.
* Arquitectura funcional.
* Desarrollo Full Stack.
* Integración con Luna y sistema de votaciones.
* Migración de datos.
* Tests de integración.
* Despliegue y operación en producción.
* Evolución continua.

---

# Qué representa este proyecto

Dashboard NEXO representa mi forma de entender la productividad.

No consiste en utilizar muchas herramientas.

Consiste en construir las herramientas adecuadas.

Es el núcleo operativo de NEXO Digital y uno de los proyectos donde más he aprendido sobre organización, automatización y desarrollo de productos que se usan de verdad, todos los días.
