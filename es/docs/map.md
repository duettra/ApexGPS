# La pantalla del mapa

Todo gira en torno a esta vista. Esto hace cada control.

## Gestos

| Gesto | Efecto |
|---|---|
| Arrastrar (un dedo) | Desplazar el mapa. |
| Pellizcar | Acercar / alejar. |
| Giro con dos dedos | Rotar el mapa. |
| Toque en una ruta | Abre el panel de ruta (perfil, scrubber). |
| Toque en un punto | Abre el panel del punto (nombre, descripción, editar). |
| Toque en el triángulo azul (tu posición) | Abre el panel **Compartir ubicación**. |
| Pulsación larga en mapa vacío | Añade un punto en esa posición. |

## Arriba a la derecha: la brújula

Una pastilla redonda con aguja roja. Siempre visible. La aguja apunta siempre al norte verdadero, sea cual sea la rotación del mapa — también sirve de indicador permanente de norte.

- **Toque** — orienta suavemente el mapa al norte arriba.
- **Pulsación larga** — alterna el bloqueo de rotación. Pastilla **azul** = los gestos de dos dedos se ignoran; el mapa mantiene la orientación. Pulsa largo otra vez para desbloquear.

Opción de bloqueo al inicio en **Ajustes → Apariencia → Bloquear rotación al iniciar** para quienes no quieren rotar el mapa.

## Columna derecha: los botones de acción

De arriba abajo:

### Medir distancia
**Icono de regla**. Toca para entrar en modo medición; toca en el mapa para dejar pines; una línea los conecta y la barra inferior muestra la distancia total. Arrastra el primer pin a tu posición GPS para medir «desde mí». Toca el icono otra vez para salir.

### Capas de mapa
**Icono de capas**. Seis estilos: OpenTopoMap (por defecto, senderismo), OSM Estándar (general limpio), ESRI Topo, ESRI relieve sombreado, Satélite, Outdoors (Thunderforest — requiere una clave API gratuita en Ajustes → Claves API).

El estilo elegido se mantiene entre sesiones.

### Seguirme (centrado)
Tres estados — el color del botón lo indica:

| Estado | Color | Comportamiento |
|---|---|---|
| **Apagado** | Gris | GPS apagado, sin triangulito en el mapa. |
| **Encendido, bloqueado** | Azul sólido | GPS activo, triángulo visible, el mapa se recentra cada pocos segundos sobre ti. |
| **Encendido, desbloqueado** | Azul pálido | GPS activo, triángulo actualizado, pero el mapa queda donde lo moviste. |

- Toque desde **Apagado** → enciende GPS + bloquea cámara sobre ti.
- Toque desde **Bloqueado** → apaga GPS.
- **Arrastrar el mapa** estando bloqueado → pasa automáticamente a desbloqueado. Triángulo actualizado; el mapa se queda.
- Toque desde **Desbloqueado** → recentra + re-bloquea.
- **Pulsación larga** en cualquier estado activo → apaga el GPS al instante (sin animación de recentrar).

### ¿Dónde está el botón de importar (+)?

Desde la **v1.25.2** el mapa ya no tiene FAB de importar — la importación GPX vive ahora en las pantallas de lista Rutas y Puntos. Ver [Rutas](tracks.md#importar) o [Puntos](waypoints.md#añadir-un-punto).

## Arriba a la izquierda

- **☰ menú** — cajón de navegación (Rutas, Puntos, Mapas, Ajustes).
- **Botón de pánico** — pastilla roja ⚠, solo si está activado en **Ajustes → Apariencia → Botón de pánico**. Toque abre el panel de compartir ubicación (activa GPS si no estaba).

## Barra de estadísticas (abajo)

Tres números:

- **VEL** — km/h actuales del GPS.
- **ALT** — altitud actual en metros.
- **DIST** — contextual:
  - En **modo medición**: longitud total de la línea.
  - Durante **navegación a una ubicación compartida**: distancia en vivo al destino (azul cuando autoactualiza).
  - Si no: vacío.

## Indicador sin conexión

Si el dispositivo no tiene red, arriba aparece una pastilla roja **«Sin conexión»**. Los mosaicos en caché se muestran; los nuevos no cargan hasta que vuelvas a estar en línea. Ver [Mapas sin conexión](offline-maps.md) para descargar regiones antes.

---

**Relacionado:** [Rutas →](tracks.md) · [Puntos →](waypoints.md) · [Compartir tu ubicación →](share-and-navigate.md)
