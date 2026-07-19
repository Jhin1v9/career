# Workspace

## Estado

Producto interno · Desarrollo activo

---

# ¿Qué es Workspace?

Workspace es la plataforma de comunicación y gestión entre NEXO Digital y sus clientes, y al mismo tiempo el monorepositorio donde conviven todos los productos del ecosistema.

Por un lado es una pieza de ingeniería organizativa: un único entorno donde cada proyecto comparte librerías, componentes y herramientas.

Por otro es un producto real: un portal donde el cliente describe lo que necesita en lenguaje natural y sigue su proyecto, mientras el equipo gestiona todo desde un panel de administración.

---

# El problema

Durante los primeros meses de NEXO Digital, cada aplicación evolucionaba de forma independiente.

Esto provocaba situaciones como:

* Componentes duplicados.
* Configuraciones repetidas.
* Dependencias mantenidas por separado.
* Cambios que debían aplicarse manualmente en varias aplicaciones.

Y en la relación con clientes, otro problema clásico: la comunicación dispersa entre WhatsApp, e-mail y conversaciones sueltas, sin un lugar donde el cliente pudiera ver el estado real de su proyecto.

Necesitaba una solución que permitiera escalar el ecosistema sin aumentar la complejidad.

---

# La idea

Un monorepositorio con dos aplicaciones que comparten un mismo dominio de negocio:

* **Portal del cliente** (mobile-first): el cliente entra, describe su necesidad en lenguaje natural y sigue sus proyectos, solicitudes y entregas.
* **Panel de administración** (desktop-first): el equipo gestiona clientes, proyectos, solicitudes, créditos y analíticas.

La clave está en que las reglas de negocio no viven duplicadas en cada aplicación, sino en una capa de dominio compartida.

---

# Cómo está construido por dentro

* **Monorepo con pnpm + Turborepo**, con TypeScript estricto en todo el código.
* **Capa de dominio compartida** con 22 capabilities de negocio: cada operación valida permisos por rol, aísla datos por organización (multi-tenancy) y emite eventos de dominio que alimentan la timeline y las notificaciones.
* **Dos aplicaciones Next.js 14** (App Router) y una base de datos **PostgreSQL con Prisma**: 22 modelos y 12 enums.
* **Autenticación con NextAuth v5** y control de acceso por roles (admin, manager, member, viewer).
* **Chat estilo messenger** con mensajes de texto, imagen, vídeo y archivos, reacciones, confirmación de lectura, indicador de escritura y tiempo real mediante SSE.
* **Sistema de créditos** con transacciones atómicas: débito y saldo se actualizan en la misma operación.
* **API REST dedicada a agentes de IA**: 15 endpoints documentados con autenticación propia, rate limiting y respuestas estandarizadas, para que Luna pueda operar la plataforma como un cliente más.
* **Seguridad aplicada:** verificación HMAC en webhooks, comparaciones timing-safe, aislamiento por organización en cada capability.
* **Tests end-to-end con Playwright** cubriendo ambas aplicaciones, incluyendo casos negativos de permisos.

El proyecto se desarrolló con doc-driven development: 15 documentos de arquitectura (manifiesto de producto, blueprints de dominio, UX y técnica, ADRs) que preceden al código.

En números: unas 88 rutas de API, 30 páginas y 32.000 líneas de TypeScript.

---

# Lo que aprendí

Workspace me hizo comprender que desarrollar software no consiste únicamente en escribir código.

También implica diseñar un entorno donde ese código pueda mantenerse, evolucionar y crecer durante años.

Aprendí que una buena organización puede ahorrar tantas horas como una buena optimización, y que invertir tiempo en el flujo de desarrollo genera beneficios en todos los proyectos futuros.

También fue mi primera experiencia diseñando una API pensada no solo para humanos, sino para agentes de IA como consumidores de primera clase.

---

# Tecnologías utilizadas

* Next.js 14 (App Router).
* React 18.
* TypeScript estricto.
* Turborepo + pnpm workspaces.
* PostgreSQL + Prisma.
* NextAuth v5.
* Tailwind CSS + shadcn/ui.
* Server-Sent Events.
* Playwright (tests e2e).
* Docker Compose.
* Zod.
* Git, GitHub, Vercel.

---

# Mi papel

* Diseño de la arquitectura del monorepositorio.
* Diseño de la capa de dominio y las capabilities.
* Desarrollo completo de ambas aplicaciones.
* Diseño de la API para agentes de IA.
* Tests end-to-end.
* Evolución continua del Workspace.

---

# Qué representa este proyecto

Workspace representa un cambio importante en mi forma de desarrollar software.

Al principio pensaba proyecto por proyecto.

Hoy intento pensar en plataformas.

En ecosistemas.

En herramientas que puedan crecer juntas.

> **Cuando el número de proyectos aumenta, la organización deja de ser una comodidad y se convierte en una necesidad.**

Workspace es la base sobre la que desarrollo la mayoría de mis nuevos productos.
