# Puntos

Un **punto** es un lugar con nombre en el mapa — inicio de sendero, cumbre, buen lugar para foto, refugio, dónde está el coche. Cada uno tiene nombre, color y uno de 32 símbolos.

## Añadir un punto

### En un sitio concreto (pulsación larga en el mapa)

Pulsa largo en el mapa donde quieras el punto. Se abre un sheet con:

- **Nombre** — opcional. «Punto» por defecto si lo dejas vacío.
- **Notas** — descripción opcional.
- **Latitud / Longitud** — autorrellenadas del punto tocado; **editables** si quieres ajustar.
- **Elevación (m)** — opcional. Déjala en blanco si no la sabes; rellénala cuando quieras que el punto lleve una altitud concreta (p. ej. la altura de una cumbre que consultaste).
- **Símbolo** — elige entre 32 iconos.
- **Color** — paleta de 16 colores.
- **Guardar** / **Cancelar**.

### Escribiendo coordenadas

Abre **menú → Puntos** → FAB **+** azul abajo a la derecha. Mismo sheet, pero Lat / Lon empiezan vacíos. Escribe coordenadas (o pega una cadena `lat, lon` en Latitud — la app las separa automáticamente).

### Importando un GPX

Abre **menú → Puntos** → FAB **carpeta azul** abajo a la derecha. Elige uno o más `.gpx`. Todos los puntos en los archivos se importan. Los duplicados (mismo nombre, a menos de ~11 m) se omiten automáticamente.

### En tu posición actual

Activa el GPS (botón de centrado si el triángulo no aparece), pulsación larga sobre el propio triángulo (o muy cerca), y el diálogo se abre con tu posición.

### Desde un GPX recibido (compartir / abrir con)

Los GPX abiertos desde otra app (adjunto WhatsApp, Gmail, gestor de archivos) también importan sus puntos. Si un punto no tiene nombre (algunos exportadores meten las coordenadas en el nombre), ApexGPS lo detecta y muestra «Punto».

## Ver un punto

Toca un punto. Un panel sube desde abajo con:

- Icono + nombre.
- Coordenadas (lat/lon a 6 decimales).
- Altitud (si está definida).
- Distancia desde tu posición GPS (azul — en vivo).
- Descripción (si la escribiste).
- Botón **Navegar** (persona caminando, azul) — inicia navegación en línea recta al punto. Ver abajo.
- Botón **Compartir** — envía el punto por WhatsApp / SMS / e-mail. El destinatario recibe texto con nombre, coords, altitud y dos enlaces (ApexGPS App Link + Google Maps). Si tiene ApexGPS, el toque abre la app con una diana roja en el sitio — puede guardarlo como su propio punto.
- Botón **Editar**.

Cerrar deslizando hacia abajo.

## Navegar a un punto

Toca el icono **Navegar** (persona caminando, teñida primario) en el panel. El panel se cierra y:

- Una **línea punteada azul claro** se dibuja desde tu GPS al punto.
- La barra inferior pasa a: *«Navegando · 0,42 km · 045° NE · [Detener]»* — distancia en vivo (azul cuando autoactualiza), rumbo en grados + cardinal (N, NE, E, SE, S, SO, O, NO).
- El campo **DIST** de la barra inferior también muestra esa distancia en azul.
- Se detiene automáticamente a **20 metros** del punto (mensaje «Llegaste»).
- Toca **Detener** para terminar manualmente. El punto sigue — toca para reabrir el panel.

Es el mismo modo ir-a que usan las ubicaciones compartidas. Rumbo en línea recta, no giro a giro — en senderismo fuera de pista suele ser lo que buscas.

Toca el punto de nuevo durante la navegación para reabrir el panel (la navegación sigue en segundo plano).

## Editar un punto

Toca el punto → **Editar** en el panel, o abre **menú → Puntos** y toca una fila.

Mismo sheet que al añadir. Nombre, Notas, **Latitud**, **Longitud**, Símbolo, Color son editables. Al guardar, la app valida las coordenadas (lat ∈ [−90, 90], lon ∈ [−180, 180], deben ser números) y muestra un error en rojo si están fuera de rango.

## Mover un punto

**Pulsación larga y arrastrar** sobre el punto en el mapa. Arrástralo a la nueva posición. Al soltar, abajo aparece una barra:

- **Mover** — confirma la nueva posición.
- **Cancelar** — lo devuelve al sitio original.

Nada se guarda hasta que pulses Mover. Útil si el arrastre fue accidental.

## Los 32 símbolos

Agrupados por propósito para navegarlos en el selector:

| Grupo | Símbolos |
|---|---|
| **Navegación / genérico** | Bandera · Lugar · Estrella · Favorito |
| **Exterior / senderismo** | Cumbre · Collado · Mirador · Foto · Bosque · Fuente · Cascada · Agua potable · Camping · Refugio · Picnic · Hito · Ruinas |
| **Informativo** | Info · Advertencia |
| **Servicios** | Aparcamiento · Gasolinera · Restaurante · Hotel · Hospital · Aseos |
| **Transporte** | Coche · Bicicleta · Caminata · Tren · Barco · Avión · Gas |

Todos se pueden seleccionar al añadir o editar. El símbolo se guarda con el punto y sobrevive a exportar → reimportar.

## La lista de puntos (menú → Puntos)

Todos los puntos, contador en el título.

### Filtrar

**Icono filtro** → dos secciones:

- **Color** — toca un color para ver solo ese. **Todos** para limpiar.
- **Símbolo** — lista desplazable de los 32 con sus iconos. Toca uno para filtrar.

Filtros activos = icono azul.

### Ordenar

**Icono ordenar**:

- **Más recientes** — por fecha de importación / creación (por defecto).
- **Por nombre** — alfabético.
- **Más cercanos** — al GPS. «(sin GPS)» si no hay fix en caché.

### Buscar

Escribe en el campo para filtrar puntos cuyo nombre O descripción contenga tu texto.

### Selección múltiple

Mantén pulsado un punto en la lista → modo selección. Marca más, luego borrado masivo. No hay cambio masivo de color/símbolo para puntos (aún) — usa Editar por punto.

### Eliminar duplicados

Si has reimportado el mismo GPX varias veces con versiones antiguas, puedes tener duplicados apilados (mismo nombre en las mismas coords). Toca **⋮** → **Eliminar duplicados**. Conserva el más antiguo y borra el resto; indica cuántos fueron eliminados.

## Eliminar

Individual: desliza / papelera en una fila, o botón Eliminar del diálogo de edición.

Múltiple: modo selección + borrado masivo.

Sin deshacer. Ten una [copia](backup.md) si dudas.

## Mostrar un punto en el mapa

Desde la lista, toca un punto → la app vuelve al mapa y se desplaza al punto. El seguimiento queda en pausa para que no se sobrescriba con el siguiente fix GPS.

---

**Relacionado:** [Rutas →](tracks.md) · [Copia y restauración →](backup.md) · [La pantalla del mapa →](map.md)
