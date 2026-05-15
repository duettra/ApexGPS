# Rutas

Una **ruta** es un camino grabado — una secuencia de puntos GPS unidos como una línea en el mapa. Obtienes rutas **grabándolas** en vivo en ApexGPS o **importando** archivos GPX (desde GaiaGPS, Strava, Garmin Connect, wikiloc.com o cualquier otro exportador GPX).

## Grabación

Toca la **pastilla de grabación** roja en la esquina superior izquierda del mapa. El punto se expande a un chip de tiempo en vivo (`00:12:43`) y una línea roja de migas empieza a dibujar tu salida en el mapa a medida que llegan nuevos fixes GPS.

### Mientras grabas

- **Toca el chip del cronómetro** para un menú:
  - **Pausar** — congela el reloj; los nuevos fixes dejan de añadirse a la línea hasta que toques **Reanudar**.
  - **Finalizar** — guarda la salida como nueva Ruta, abre el panel de la ruta para que revises estadísticas + perfil de altitud al instante.
  - **Eliminar** — descarta la grabación actual sin guardar.
- El servicio GPS de primer plano arranca solo cuando empiezas una grabación — no necesitas activar antes el seguimiento.
- **¿Pantalla apagada?** La app relaja la cadencia de fixes GPS para ahorrar batería (≈10 s entre fixes con la pantalla apagada vs 2 s con la pantalla encendida). No hay que hacer nada — cambia automáticamente.

### Si la ubicación del sistema está apagada

Tocar grabar con el interruptor de ubicación del sistema Android apagado muestra un mensaje rápido *«Ubicación del sistema apagada — actívala para grabar»* con un acceso directo a **Ajustes**. La grabación no empieza.

### Si la app se cierra a mitad de la salida

Si Android mata la app durante una grabación activa (recuperación de memoria, forzar detención, reinicio), la línea recogida hasta ese momento se **conserva**. Reabre la app y la pastilla vuelve mostrando el tiempo transcurrido en pausa — toca **Reanudar** para seguir, o **Finalizar** para guardar lo que tengas.

### Tipo de actividad

Cada ruta grabada arranca etiquetada como **Senderismo**. Abre la pantalla de detalle de la ruta (Rutas → toca la fila) y usa el menú **Actividad** para cambiarla a Caminata / Correr / Ciclismo / Todoterreno / Parapente. Las rutas importadas no tienen etiqueta por defecto; puedes asignarla igual.

### Recortar una grabación

¿Ruido de calentamiento de GPS al inicio de tu ruta? ¿Olvidaste tocar **Finalizar** y la ruta se alarga hasta el coche? Abre la pantalla de detalle y toca **Recortar ruta**:

- Se abre un diálogo con una mini-vista previa del mapa de la ruta completa y su perfil de altitud debajo.
- Arrastra los dos manejadores del gráfico de altitud para fijar el inicio y el final del tramo que quieres conservar. La mini-vista se actualiza en vivo — el tramo que se conserva se mantiene en el color de la ruta, las partes descartadas se vuelven grises.
- El indicador **Conservado** muestra la distancia y el número de puntos resultantes.
- Toca **Recortar** para confirmar. Un diálogo de confirmación detalla cuántos puntos caerán de cada extremo. **No se puede deshacer** — guarda un export GPX si dudas.

Recortar también recalcula la distancia, el bounding box y el perfil de altitud de la ruta, así que las estadísticas de la parte superior reflejan la ruta recortada al instante.

## Planificación de una ruta

Si quieres trazar una ruta antes de hacerla — la caminata de mañana, un bucle que viste en un mapa de papel, un enlace entre dos senderos que conoces — puedes esbozarla directamente sobre el mapa y guardarla como Ruta.

Abre **menú → Rutas** → toca el **FAB + azul** abajo a la derecha (encima del FAB de carpeta de importación). La app salta al mapa en **modo planificación**:

- La barra superior cambia a `✕  Planificar ruta  ✓ Guardar`. Un pequeño chip debajo muestra tu cuenta de puntos en vivo y la distancia total.
- **Toca en cualquier punto del mapa** para soltar un vértice numerado verde azulado. Cada toque extiende la ruta hasta la siguiente parada. El primer toque coloca el vértice 1 donde tú toques — la planificación arranca vacía, así que puedes desplazar el mapa a cualquier zona primero y planificar desde ahí.
- **Mantén pulsado un vértice y arrástralo** para moverlo. Mantén pulsado el pequeño punto entre dos vértices y arrastra para insertar un punto nuevo en ese tramo.
- **Arrastra un vértice hasta el icono de la papelera** arriba a la derecha (justo debajo de la brújula) para borrarlo. La línea se vuelve a conectar a través de los vecinos restantes. La papelera se enciende en rojo cuando un vértice está encima.
- Toca el **icono de gráfico** a la derecha para abrir la hoja de **perfil de altitud**. La app obtiene altitudes de Open-Meteo para muestras tomadas cada ~100 m a lo largo de tu ruta, y luego muestra un gráfico con ascenso y descenso totales. Una ruta larga se muestrea con menor densidad (tope de ~500 muestras) para que la descarga no se dispare. Cancelar y cerrar están disponibles mientras carga.
- Toca **✓ Guardar** en la barra superior, ponle nombre a la ruta y confirma. La nueva Ruta aterriza en tu lista de Rutas (ordenable, exportable como GPX, comparable contra una futura grabación). El mapa ajusta el zoom al bbox de la nueva ruta automáticamente.

Para abandonar: toca **✕** o pulsa el botón atrás del sistema. Si has colocado algún punto, la app pregunta antes de descartar.

## Importar

### Desde un archivo

Abre **menú → Rutas** → toca el **FAB de carpeta azul** abajo a la derecha. Elige uno o más `.gpx` del almacenamiento (multi-selección permitida). La app vuelve al mapa y ajusta el zoom a las rutas importadas.

### Desde un compartido (WhatsApp, e-mail, otra app)

¿Alguien te envía un `.gpx`? Tócalo en el chat / e-mail / gestor de archivos → el sistema ofrece abrirlo con ApexGPS → la app lo importa automáticamente y te lleva al mapa.

### Qué se importa

- Líneas de ruta (con altitud si el GPX la incluye).
- Puntos incrustados en el archivo (cada uno con su nombre, descripción y símbolo mapeado al más cercano de ApexGPS).

**Protección contra duplicados:** si reimportas el mismo GPX, los puntos ya presentes en esas coordenadas no se añaden de nuevo. Las líneas de ruta SÍ se reimportan (mismo nombre, puedes borrar el duplicado manualmente).

## Ver una ruta en el mapa

Toca una línea de ruta en el mapa. Un panel sube desde abajo con:

- Nombre + distancia.
- **Perfil de altitud** — gráfico pequeño. Arrastra el dedo para desplazarte por la ruta; un puntero muestra el punto correspondiente en el mapa.
- **Ascenso / descenso** totales.
- Botón **Editar** → abre la pantalla de detalle.
- Botón **Compartir** → exporta la ruta como `.gpx` para enviar a quien quieras.
- Botón **Ocultar** → minimiza el panel a una barra fina abajo (para seguir trabajando con la selección sin cubrir el mapa).
- **Cerrar** (deslizar abajo) → cierra el panel.

## La lista de rutas (menú → Rutas)

Lista completa de todas las rutas importadas. Contador en el título.

### Filtrar

Toca el **icono de filtro**. Dos opciones:

- **Visibilidad** — Todas / Solo visibles / Solo ocultas. Las rutas ocultadas con el interruptor de visibilidad siguen en la lista pero no se dibujan.
- **Color** — paleta de 16 colores. Toca un color para ver solo rutas de ese color.

Filtro activo = icono azul. Toca **Todas** en cada sección para limpiar.

### Ordenar

Toca el **icono de ordenar**:

- **Más recientes** — por fecha de importación (por defecto).
- **Por nombre** — alfabético.
- **Más cercanas** — punto central más cerca de tu posición. Usa la última ubicación conocida del teléfono, funciona aunque no hayas activado GPS en ApexGPS en esta sesión. Muestra «(sin GPS)» si no hay permiso o fix en caché.
- **Por puntos** — rutas con más puntos primero (útil para identificar las muy detalladas).

### Buscar

Escribe en el campo de búsqueda para filtrar rutas cuyo nombre contenga tu texto.

### Selección múltiple

Mantén pulsada una ruta → modo selección. Marca las que quieras, luego:

- **Cambio de color masivo** (icono paleta) — asigna un color a todas.
- **Mostrar / ocultar masivo** (iconos de ojo) — visibilidad rápida.
- **Compartir masivo** (icono compartir) — empaqueta cada ruta seleccionada en un único archivo `.gpx` y abre el diálogo de compartir. Ver [Compartir rutas y puntos](share-and-navigate.md#compartir-rutas-y-puntos).
- **Borrado masivo** (papelera roja) — con confirmación.
- **Seleccionar todas** — marca todas las de la vista filtrada.

## Acciones por ruta

Toca una ruta en la lista → abre la pantalla **Detalle**.

- **Nombre** — editable.
- **Color** — toca para abrir el selector.
- **Visibilidad** — mostrar / ocultar en el mapa.
- **Perfil de altitud** — el mismo gráfico del panel en el mapa, pero a tamaño completo.
- **Ascenso / descenso** totales.
- **Número de puntos** — cuántos puntos GPS componen la ruta.
- **Mostrar en el mapa** — cierra el detalle y ajusta el zoom a la ruta.
- **Optimizar** — simplifica quitando puntos redundantes. Útil para importaciones masivas. No destructivo a nivel archivo; reimporta para recuperar el original.
- **Compartir como GPX** — igual que el botón del panel del mapa.
- **Eliminar** — con confirmación.

## Optimización masiva (bibliotecas grandes)

Si has importado muchas rutas muy densas, el mapa puede ir lento en teléfonos antiguos. **Ajustes → Datos → Optimizar todas** aplica la misma simplificación en todas a la vez. La UI muestra cuántas serán afectadas.

## Eliminar

Individual: desliza / toca la papelera en la fila, o el botón Eliminar del detalle.

Múltiple: modo selección + borrado masivo.

No hay deshacer. Ten una [copia de seguridad](backup.md) si dudas.

---

**Relacionado:** [Puntos →](waypoints.md) · [La pantalla del mapa →](map.md) · [Copia y restauración →](backup.md)
