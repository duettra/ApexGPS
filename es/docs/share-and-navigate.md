# Compartir tu ubicación, rutas y puntos — y navegar a un destino

## Compartir tu ubicación actual

### Versión rápida

1. Asegúrate de que el GPS está activo (botón de centrado → triángulo azul).
2. Toca el **triángulo azul** en el mapa.
3. Sube un panel con tus datos. Toca **Compartir**.
4. Elige WhatsApp, SMS, e-mail. Envía.

### Qué muestra el panel

```
Altitud 145 m · ±5 m · 19:42
Batería 87%
ApexGPS: https://apexgps.duttra.de/loc?lat=25.165183&lon=55.409717
Google Maps: https://maps.google.com/?q=25.165183,55.409717
```

- **Altitud** — metros sobre el nivel del mar según el GPS (ausente si el teléfono no pudo determinarla).
- **±precisión** — confianza del GPS en metros. Árboles, edificios y cañones aumentan el valor.
- **Hora** — cuándo se tomó la posición.
- **Batería** — para que el receptor sepa si te queda poca.
- Dos **URL** — la primera abre ApexGPS (si está instalado), la segunda cualquier app de mapas.

### Qué ve el receptor

El mensaje añade un saludo antes de los detalles:

```
Hola, esta es mi ubicación actual.

Altitud 145 m · ±5 m · 19:42
Batería 87%
ApexGPS: https://apexgps.duttra.de/loc?lat=...
Google Maps: https://maps.google.com/?q=...
```

En WhatsApp y similares ambas URL son clicables. En SMS son texto copiable.

### Si aún no hay fix GPS

El panel se abre pero muestra «Adquiriendo GPS…» y el botón Compartir está deshabilitado. Al llegar el primer fix, el panel se actualiza y Compartir se activa — no hace falta cerrar y reabrir.

## Compartir rutas y puntos

ApexGPS te deja enviar tus rutas y puntos a quien quieras como archivos `.gpx` estándar — ábrelos en GaiaGPS, Strava, Garmin BaseCamp, wikiloc u otra copia de ApexGPS. Tres caminos para hacerlo:

### Una sola ruta o un solo punto

- **Ruta** — toca una ruta en el mapa → botón **Compartir** del panel. O abre la pantalla de detalle (Rutas → toca una fila) → **icono compartir** de la barra superior.
- **Punto** — toca un punto en el mapa → botón **Compartir** del panel. El receptor recibe un mensaje con el nombre, las coordenadas, la altitud y dos enlaces (App Link de ApexGPS + Google Maps).

### Compartir en lote desde las pantallas de lista

Abre **Menú → Rutas** (o **Puntos**), pulsa largo una fila para entrar en modo selección, marca las que quieras y toca el **icono compartir** de la barra superior:

- Rutas → empaqueta cada ruta seleccionada en un único archivo `.gpx`.
- Puntos → empaqueta cada punto seleccionado en un único `.gpx`.

Se abre un diálogo de compartir — elige WhatsApp, Drive, Gmail, lo que quieras. El nombre del archivo incluye la fecha.

### Compartir todo lo visible («Compartir visible»)

El camino más rápido cuando quieres entregarle a alguien «toda la zona que estoy viendo». Tres puntos de entrada, todos llevan a la misma hoja:

- **Pantalla del mapa → icono compartir** en la barra superior (a la izquierda del menú ☰). Usa tu viewport del mapa en vivo.
- **Menú → Mapas → Compartir rutas y puntos visibles** (tercera tarjeta del hub de Mapas, debajo de Descargar / Mapas guardados). Usa el viewport que tenías abierto justo antes de entrar en el hub — así puedes desplazarte, encontrar la zona y luego saltar dentro.
- **Menú ⋮ del mapa → Compartir rutas y puntos visibles**.

Sube una hoja listando cada ruta visible (líneas que cruzan el viewport Y están activadas como visibles) y cada punto visible (dentro del viewport). Cada fila tiene una casilla — **desmarca lo que no quieras enviar**. El nombre por defecto se geocodifica desde el centro del viewport («ApexGPS-Wadi-Bani-Khalid-2026-05-14.gpx» si el geocoder resuelve; «ApexGPS-2026-05-14.gpx» si estás sin conexión o no devuelve nada).

Toca **Compartir** → se construye un único archivo `.gpx` con todas las rutas + puntos seleccionados + una pequeña cabecera de metadatos, y se abre el diálogo de compartir del sistema.

#### Límites de tamaño

Un paquete de «Compartir visible» se mantiene en memoria mientras se construye, así que selecciones muy grandes pueden fallar con un aviso claro:

| Límite | Tope |
|---|---|
| Rutas por paquete | 100 |
| Puntos por paquete | 1000 |
| Puntos de ruta totales (sumando todas las rutas seleccionadas) | 100 000 |

Si llegas a un tope, el aviso te dice cuál — reduce la selección en la hoja (desmarca alguna ruta grande) o usa **Ajustes → Datos → Copia de seguridad** para exportes muy grandes (esa ruta transmite el ZIP en streaming y no está acotada por estos límites).

## Recibir una ubicación compartida

Alguien te envía un enlace `apexgps.duttra.de/loc?...`.

### Si tienes ApexGPS

Toca el enlace → **ApexGPS se abre directamente**, el mapa se desplaza al punto y aparece una diana roja. Sube una barra con tres botones:

- **Navegar** — inicia modo ir-a (ver abajo).
- **Guardar** — añade ese lugar como punto (eliges nombre, color, símbolo).
- **Descartar** — quita el marcador, no hace nada.

### Si no tienes ApexGPS

Toca el enlace → abre una página web simple con previsualización del mapa más:

- Botón **Abrir en ApexGPS** (solo Android; propone instalar si no lo tienes).
- Botón **Abrir en Google Maps**.

## Navegar a una ubicación compartida

Tras tocar un enlace compartido, pulsa **Navegar** en la barra inferior:

- Una **línea punteada azul claro** se dibuja de tu posición al destino.
- La barra pasa a: *«Navegando · 0,42 km · 045° NE · [Detener]»*.
  - Distancia actualizada en cada fix, en **azul** = autoactualiza.
  - **Rumbo** en grados + una de ocho cardinales (N, NE, E, SE, S, SO, O, NO) — camina en esa dirección.
  - La misma distancia aparece en **DIST** de la barra inferior, azul, durante la navegación.
- Al llegar a **20 metros** del destino, la navegación se detiene automáticamente con «Llegaste».
- **Detener** termina manualmente. La diana se queda; puedes **Navegar** otra vez o **Guardar** como punto.

Es rumbo en línea recta — no giro a giro. En senderismo fuera de pista suele ser lo que quieres; en ciudad, abre el enlace de Google Maps para rutas por calles.

### También funciona con tus puntos

El mismo modo ir-a arranca desde cualquier punto en el mapa. Toca un punto → icono **Navegar** (persona caminando) en su panel → el panel se cierra y la barra de navegación toma el control. Detalles en [Puntos → Navegar a un punto](waypoints.md#navegar-a-un-punto).

## La brújula de navegación (pantalla completa)

Durante la navegación, en la barra aparece un pequeño **icono brújula** 🧭 a la izquierda de Detener. Toca para abrir una vista grande. Arrastra hacia abajo para minimizar.

### Disposición

Fila superior: **Distancia** (azul) · **ETA** · **Velocidad** · **Altitud**.

Esfera analógica central:
- Anillo exterior con marcas cada 15° (mayores cada 30°).
- Etiquetas **N / E / S / O** en la carta.
- Pequeño **triángulo rojo** marcando el norte verdadero.
- **Aguja azul** (triángulo) apuntando al destino en el mundo real.
- **Insignia central** con el rumbo actual del teléfono (`245°`), o la letra **S** con el pie *«Rumbo simulado»* cuando el sensor es poco fiable (metal cerca, imanes, se necesita calibración en 8).

Fila inferior: **Lat · Lon · Rumbo° + cardinal · ±Precisión**.

Abajo: **Detener navegación** (ancho completo, finaliza la navegación).

### Uso

La esfera **rota con la orientación del teléfono** para que el triángulo rojo siempre apunte al norte real. Apunta la parte superior del teléfono hacia la aguja azul para estar de cara al destino.

Con sensor fiable la insignia muestra grados; si no, la «S» estilizada y *Rumbo simulado* — recordatorio de que la dirección puede derivar.

### Qué pasa con la barra inferior

Mientras la brújula está abierta, la barra habitual de VEL / ALT / DIST abajo queda **oculta** — la brújula ya muestra esos valores en grande y duplicar sería ruidoso. La barra reaparece al minimizar la brújula.

### Qué muestra la barra de nav cuando la brújula está cerrada

Brújula minimizada, la barra de abajo muestra:

> *Navegando · **045° NE** · ETA 12 min · 🧭 · Detener*

Rumbo y cardinal van en **azul** porque se actualizan en cada fix. ETA se estima con tu velocidad actual — muestra `--` parado. La distancia ya no está en la barra; está en **DIST** (también azul durante la navegación).

---

**Relacionado:** [La pantalla del mapa →](map.md) · [Ajustes →](settings.md) · [FAQ →](faq.md)
