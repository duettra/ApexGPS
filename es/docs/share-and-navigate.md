# Compartir tu ubicación y navegar a un destino

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
