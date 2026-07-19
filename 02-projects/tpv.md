# TPV para Restauración

## Estado

Proyecto para cliente · MVP funcional desarrollado

---

# ¿Qué es este proyecto?

Este fue el primer gran proyecto que desarrollé para un cliente dentro de NEXO Digital.

El cliente necesitaba inicialmente un TPV (Terminal Punto de Venta) para gestionar una heladería.

Lo que comenzó como una aplicación relativamente sencilla terminó evolucionando hacia un ecosistema completo pensado para digitalizar gran parte del funcionamiento del negocio.

Aunque finalmente el proyecto no llegó a implantarse por una decisión del cliente, supuso una de las experiencias de aprendizaje más importantes de mi carrera.

---

# El reto

El objetivo inicial parecía claro:

> Construir un TPV.

Sin embargo, mientras hablábamos con el cliente, fui entendiendo que el verdadero problema no era vender productos.

El verdadero reto consistía en hacer más eficiente el funcionamiento del negocio.

Eso cambió completamente mi forma de plantear la solución.

En lugar de desarrollar únicamente una caja registradora, empecé a pensar en todo el recorrido de un pedido.

---

# La solución

Diseñé un ecosistema donde diferentes aplicaciones colaboraban entre sí en tiempo real.

Cada una resolvía una necesidad específica del negocio.

El objetivo era reducir trabajo manual, minimizar errores y facilitar la gestión diaria.

---

# Componentes del sistema

## TPV (punto de venta)

Aplicación principal para gestionar ventas, pedidos y cobros, con interfaz táctil pensada para uso rápido en mostrador.

## Kitchen Display System (KDS)

Pantalla para cocina: cada nuevo pedido aparece automáticamente en el momento en que se realiza, sin imprimir tickets, gracias a la sincronización en tiempo real.

## Panel de Administración

Gestión de productos, categorías, stock, usuarios, configuración del negocio y estadísticas.

## Aplicación del cliente (PWA)

App instalable desde el navegador: el cliente consulta el menú, hace su pedido desde el móvil y este llega directamente a cocina.

---

# Detalles técnicos

* **4 aplicaciones sincronizadas en tiempo real** mediante Supabase Realtime: cuando algo cambia en una, todas las demás reaccionan al instante.
* **Fallback offline:** si la conexión falla, las aplicaciones siguen sincronizándose localmente mediante BroadcastChannel.
* **Internacionalización completa en 4 idiomas** (español, catalán, portugués e inglés), pensando en el público real de la zona.
* **Catálogo real** con 58 productos y fotografías.
* **PWA instalable**, con manifest y funcionamiento tipo app nativa.
* Interfaz animada y responsive con Framer Motion.

---

# Una idea que nació durante el proyecto

Mientras desarrollábamos el sistema apareció una nueva oportunidad.

Observé que muchos clientes esperaban sentados a que un camarero tomara nota de su pedido.

Entonces propuse una alternativa: ¿y si el propio cliente pudiera realizar el pedido desde su móvil?

Escanear un código QR, consultar el menú, pedir, pagar desde el teléfono y enviar el pedido directamente a cocina.

Aunque esta evolución nunca llegó a desarrollarse completamente, me hizo comprender la importancia de cuestionar continuamente la solución inicial.

A veces el mejor producto aparece cuando dejamos de pensar en la petición del cliente y empezamos a entender realmente su problema.

---

# Qué aprendí

Este proyecto cambió mi forma de entender el desarrollo de software.

Aprendí que escribir código es solo una pequeña parte del trabajo.

También hay que escuchar.

Hacer preguntas.

Observar cómo trabaja el cliente.

Entender su negocio.

Y, muchas veces, descubrir problemas que ni siquiera él había identificado.

Fue la primera vez que experimenté cómo una conversación podía cambiar completamente la dirección de un producto.

---

# Tecnologías utilizadas

* React 19.
* TypeScript.
* Vite.
* Tailwind CSS.
* Framer Motion.
* Zustand.
* Supabase (PostgreSQL + Realtime).
* BroadcastChannel (fallback offline).
* Progressive Web Apps (PWA).
* i18n (ES / CA / PT / EN).
* Vercel.
* Git.

---

# Mi papel

* Análisis del problema.
* Diseño de la arquitectura.
* Desarrollo Full Stack.
* Diseño de la experiencia de usuario.
* Integración en tiempo real entre aplicaciones.
* Despliegue de demostraciones funcionales.
* Presentación del producto al cliente.
* Evolución del proyecto según el feedback recibido.

---

# Qué representa este proyecto

Este proyecto representa el momento en el que dejé de pensar únicamente como desarrollador y empecé a pensar como alguien que diseña productos.

El cliente pidió un TPV.

Yo terminé imaginando un ecosistema completo para mejorar el funcionamiento del negocio.

Aunque el proyecto finalmente no se implantó, el aprendizaje obtenido sigue influyendo hoy en la forma en que abordo cada nuevo producto que desarrollo.

Fue el proyecto que me enseñó que las mejores soluciones rara vez aparecen respondiendo directamente a una petición; aparecen cuando entendemos el problema que existe detrás de ella.
