# Rutas

Una **ruta** es un camino grabado — una secuencia de puntos GPS unidos como una línea en el mapa. Las rutas vienen de importar archivos GPX (desde GaiaGPS, Strava, Garmin Connect, wikiloc.com, cualquier otro exportador GPX).

**Nota:** ApexGPS no graba rutas nuevas en esta versión. La grabación en vivo llegará en una versión futura.

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
