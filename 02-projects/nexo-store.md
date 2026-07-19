# NEXO Store

## Estado

Producto interno · Vitrine en producción · Nuevas capacidades en desarrollo

---

# ¿Qué es NEXO Store?

NEXO Store es la vitrine pública del ecosistema NEXO Digital: una app store propia donde todos los productos que desarrollamos están organizados como un catálogo navegable.

Hoy reúne 75 productos reales —aplicaciones, TPVs, SaaS, sitios web y plantillas— con búsqueda, filtros por categoría, páginas de detalle, valoraciones y un panel de administración.

Nació con una idea muy sencilla: cada herramienta que desarrollábamos terminaba guardada en diferentes carpetas, repositorios o conversaciones. Decidí construir un lugar donde todos esos activos pudieran vivir organizados.

---

# El problema

A medida que empezamos a desarrollar más proyectos, apareció un problema inesperado.

No era desarrollar software.

Era encontrarlo después.

Plantillas.

Aplicaciones.

Demos.

Versiones de prueba.

Todo terminaba repartido entre distintos repositorios y carpetas.

Sabía que, si seguíamos creciendo, esa desorganización acabaría convirtiéndose en un problema mucho mayor.

---

# Qué hace hoy

* **Catálogo navegable** de 75 productos con búsqueda, filtros sincronizados con la URL y páginas de detalle con capturas, características y stack de cada producto.
* **Sistema de valoraciones** real: las reviews se guardan en Supabase y cada nueva valoración dispara una notificación a Telegram para que Luna pueda responderla.
* **Panel de administración** protegido (clave + lista de IPs permitidas + rate limiting) para gestionar el catálogo: crear, editar y organizar productos, con subida de imágenes.
* **Interfaz en 3 idiomas** (español, portugués e inglés) con un sistema de i18n propio.
* **Solicitud de proyectos personalizados** mediante un asistente de 5 pasos que parte de cualquier producto del catálogo.
* **74 de los 75 productos tienen demo en vivo** enlazada desde su página de detalle.

---

# Cómo se construyó el catálogo

Llenar una tienda con 75 productos no se hace a mano.

Desarrollé un pipeline de ingesta que procesó unas 50 aplicaciones que teníamos archivadas: extrajo la documentación de cada una, infirió su categoría, tipo e industria, generó las miniaturas y produjo el catálogo completo ya tipado y organizado.

Fue un ejercicio de automatización aplicada a nuestro propio caos.

---

# La visión: el ciclo con Landing Page Creator

Aquí es donde NEXO Store se conecta con el resto del ecosistema.

La idea: cuando un usuario crea una landing page en Landing Page Creator, Luna se encarga de sanitizarla —eliminar logotipos, nombres y cualquier dato personal— y la convierte en una plantilla genérica que llega a la Store. Allí puede reutilizarse, y el creador recibe créditos dentro de la plataforma.

Cuanta más gente crea, más plantillas hay. Cuantas más plantillas hay, más útil es la plataforma.

Esa integración ya funciona: el modelo de datos de plantillas (con estados de revisión, precio virtual y tokens de vista previa) y un adaptador que convierte las plantillas del LP Creator al formato de la Store, cubierto por tests, permiten que las plantillas sanitizadas lleguen automáticamente al catálogo. Decenas de plantillas ya han hecho ese recorrido en producción.

---

# Lo que aprendí

Este proyecto reforzó una idea que ya había empezado a descubrir con otras herramientas internas.

Muchas veces el verdadero valor no está únicamente en construir aplicaciones.

Está en construir sistemas capaces de aprovechar todo lo que ya hemos construido anteriormente.

También aprendí la importancia de organizar el conocimiento técnico de una empresa: cuando la información está bien estructurada, resulta mucho más sencillo seguir creciendo.

---

# Tecnologías utilizadas

* Next.js 16 (App Router).
* React 19.
* TypeScript estricto.
* Tailwind CSS v4.
* Zustand.
* Framer Motion.
* Zod.
* Supabase (valoraciones).
* Vitest (34 tests).
* Docker, PM2.
* i18n propio (ES / PT / EN).

---

# Mi papel

* Idea original.
* Diseño del producto.
* Arquitectura.
* Desarrollo Full Stack.
* Pipeline de ingesta del catálogo.
* Panel de administración.
* Integración con el ecosistema de NEXO Digital.

---

# Qué representa este proyecto

NEXO Store representa mi interés por construir herramientas que no solo resuelvan problemas inmediatos, sino que también faciliten el trabajo futuro.

Cada plantilla, aplicación o recurso reutilizable supone una pequeña inversión que puede ahorrar muchas horas de trabajo más adelante.

Es una pieza clave dentro del ecosistema de NEXO Digital y refleja una forma de trabajar basada en la reutilización, la organización y la mejora continua, en lugar de empezar siempre desde cero.
