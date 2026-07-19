# Luna

## Estado

Proyecto personal · Desarrollo activo · En uso diario

---

# ¿Qué es Luna?

Luna es el proyecto más ambicioso que he desarrollado hasta la fecha.

Es un agente de IA capaz de ejecutar acciones reales en mi equipo: leer y modificar archivos, ejecutar comandos, trabajar con git, consultar APIs y automatizar procesos completos.

La particularidad: lo hace a través de las interfaces web de modelos de lenguaje, sin depender de APIs de pago.

Más que un asistente, Luna funciona como un entorno de trabajo que colabora conmigo durante el desarrollo de software. La utilizo todos los días.

---

# ¿Cómo nació?

La idea apareció mientras trabajaba con modelos locales de inteligencia artificial.

Los modelos que podía ejecutar con mi hardware no ofrecían la calidad necesaria para problemas complejos.

En lugar de aceptar esa limitación, me hice una pregunta diferente.

> ¿Y si pudiera utilizar modelos mucho más potentes sin depender de una API de pago?

Esa pregunta fue el punto de partida de Luna.

---

# La idea

Las interfaces web de los modelos más avanzados ya existen y ya son capaces de razonar.

Lo que no pueden hacer es actuar en el mundo real.

Luna resuelve exactamente eso: convierte la conversación con el modelo en un puente entre su razonamiento y mi máquina.

---

# Cómo funciona por dentro

Luna es una arquitectura de agentes que rodea la conversación con la IA web:

1. **Un agente abre la interfaz web del modelo** (Kimi, DeepSeek) en un Chrome real controlado por Playwright/CDP, e inyecta las instrucciones del sistema: qué herramientas existen, cómo invocarlas mediante bloques JSON estructurados y cómo interpretar los resultados.

2. **Cuando el modelo decide usar una herramienta**, genera un bloque JSON en su respuesta. Un sistema de detección en 3 capas lo captura —extensión de Chrome con MutationObserver, interceptor de red nativo CDP y extracción de estructura DOM, con deduplicación en 4 niveles— para que ninguna llamada se pierda ni se ejecute dos veces.

3. **El kernel ejecuta la acción en mi equipo**: archivos, shell, git, búsqueda web, APIs internas. Son 123 herramientas registradas, protegidas por un Tool Guard con reintentos y backoff exponencial, circuit breakers, claves de idempotencia, validación de esquemas y checkpoints automáticos en git.

4. **El resultado vuelve al chat** para que el modelo continúe razonando, en un bucle multi-turno hasta completar la tarea.

Y lo más importante para la experiencia: **el usuario no ve nada de esa maquinaria**. La interfaz propia de Luna traduce todo el proceso a una conversación visual limpia —burbujas de herramientas, resultados estilizados, estados de ejecución— construida con Svelte y actualizada en tiempo real.

---

# Capacidades reales

* **Bucle agéntico multi-turno** con parseo tolerante de JSON y recuperación de errores.
* **123 herramientas locales** ejecutables por el modelo.
* **Plan Mode:** modo de investigación de solo lectura que analiza el problema y presenta un plan para aprobar, rechazar o revisar antes de tocar nada.
* **Validador de código** posterior a cada escritura: detecta JSX desbalanceado, archivos truncados o imports rotos, con auto-corrección.
* **Compactación de contexto segura:** cuando la conversación crece demasiado, genera un resumen de estado y lo traslada a un nuevo hilo sin perder información.
* **Multi-proveedor:** funciona sobre distintos modelos web con un sistema de descubrimiento de selectores y fallbacks.
* **Bot de Telegram:** permite ejecutar acciones del ecosistema NEXO desde el móvil —crear tareas, registrar pagos, consultar información— con un perímetro de seguridad restringido a herramientas del dashboard.
* **Memoria viva:** un hook post-commit mantiene una base de conocimiento del propio proyecto (`.brain/`) actualizada automáticamente por IA después de cada cambio.
* **Instalador de un comando** y sincronización entre 3 equipos y un VPS.

---

# Mi aprendizaje durante el proyecto

Luna me enseñó mucho más que programación.

Me obligó a investigar arquitecturas diferentes, a hacer ingeniería inversa de interfaces web en tiempo real, y a aceptar que muchas buenas ideas no funcionan a la primera.

También aprendí que construir un producto consiste en iterar constantemente: muchas funcionalidades actuales nacieron después de varios intentos completamente distintos.

---

# Tecnologías utilizadas

* Node.js.
* Playwright / Chrome DevTools Protocol.
* Extensión de Chrome (Manifest V3).
* Express, WebSocket y SSE.
* PostgreSQL.
* Svelte 4 + Vite + Tailwind CSS.
* Bot de Telegram.
* PM2 (5 procesos en producción).
* Git.
* Linux.

Monorepo pnpm con 3 paquetes: kernel, dashboard y web.

---

# Mi papel

Diseño completo del producto.

Arquitectura.

Desarrollo.

Investigación.

Experimentación.

Implementación.

Despliegue.

Mantenimiento.

Evolución continua.

Todo el proyecto ha sido diseñado y desarrollado íntegramente por mí.

---

# Qué representa Luna para mí

Más allá del aspecto técnico, Luna representa mi forma de entender la ingeniería.

Detectar un problema.

Investigar.

Probar distintas soluciones.

Descartar lo que no funciona.

Y seguir iterando hasta construir una herramienta que realmente aporte valor.

Es el proyecto donde mejor se refleja mi forma de pensar como ingeniero y probablemente el que más ha contribuido a mi crecimiento técnico hasta ahora.
