# Copia y restauración

ApexGPS guarda todo **localmente en tu teléfono**. Sin sincronización en la nube. Si reinicias de fábrica, cambias de teléfono o desinstalas, **tus rutas, puntos y regiones offline se pierden** a menos que hayas hecho una copia.

La copia es manual pero sencilla. Hazla periódicamente si tienes datos que no quieres perder.

## Qué incluye una copia

- **Todas las rutas** (datos GPX, nombre, color, visibilidad, etiqueta de actividad).
- **Todos los puntos** (nombre, descripción, coords, altitud, color, símbolo).
- **Todas las regiones de mapa guardadas sin conexión** — ver [Receta vs mosaicos completos](#receta-vs-mosaicos-completos) abajo para las dos formas de incluirlas.
- **Todos los ajustes** (tema, fuente por defecto, grosor, tamaño de puntos, bloqueo de rotación, ahorro de batería, etc.).

Qué **no** incluye:

- La **caché de navegación** (mosaicos auto-guardados por uso general). No se incluye por regenerable y potencialmente enorme.
- La **clave API de Thunderforest** se guarda con los ajustes, así no hay que reintroducirla.

## Crear una copia

1. **Menú → Ajustes → Datos → Copia**.
2. Elige qué incluir — hay casillas para rutas / puntos / ajustes, más un **selector de tres modos para las regiones de mapa sin conexión** (ver abajo).
3. Toca **Crear copia**.
4. El ZIP queda en almacenamiento privado. Se abre un diálogo para compartir:
   - **Google Drive / Dropbox / OneDrive** — resguardo en nube.
   - **Enviármelo** por e-mail / chat.
   - **Guardar en Descargas** por un gestor de archivos.

El ZIP se llama por ejemplo `apexgps-backup-2026-05-14.zip`. La fecha va en el nombre.

### Receta vs mosaicos completos

Para las regiones de mapa guardadas sin conexión, eliges **uno de tres modos**:

| Modo | Tamaño | Comportamiento | ¿Multiplataforma? |
|---|---|---|---|
| **No incluir** | el menor | Las filas de región no se incluyen. | n/a |
| **Receta** | ~80 KB total | Cada región se guarda como una breve «tarjeta de instrucciones» — nombre, caja envolvente, rango de zoom, fuente de mosaicos. Al restaurar, las regiones aparecen en **Mapas → Mapas guardados** marcadas *«Aún no descargada · X mosaicos»*, con un botón **Descargar** para traer los mosaicos del servidor de mosaicos. | **Sí** — funciona entre Android e iOS. |
| **Mosaicos completos** | 50–500 MB | El paquete MBTiles real de cada región se incrusta en el ZIP. Al restaurar, las regiones se pueden usar sin conexión al instante; sin redescarga. | **Solo Android.** iOS no puede leer los paquetes incrustados (todavía). |

**Elige Receta** para mover entre dispositivos (cambio de teléfono, compartir una copia con un amigo en iOS o una copia «por si acaso» que guardarás en Drive para siempre). La redescarga es rápida por Wi-Fi y usa los mosaicos más actuales.

**Elige Mosaicos completos** si quieres específicamente una copia restaurable en un paso y sin conexión en Android — útil antes de un viaje en el que podrías formatear el teléfono y no tener Wi-Fi en destino.

**Una copia con Mosaicos completos puede tardar un par de minutos** y generar un ZIP grande. La UI muestra progreso.

## Restaurar una copia

### Ruta fácil

Toca un `apexgps-backup-*.zip` en cualquier gestor / Google Drive / adjunto de Gmail. Android ofrece apps que pueden abrirlo; elige ApexGPS. La app se abre en Ajustes → Datos con el diálogo de restauración.

### Desde Ajustes

1. **Menú → Ajustes → Datos → Restaurar**.
2. Elige el ZIP del selector.
3. Elige modo (ver abajo).
4. Confirma.

### Combinar vs Reemplazar

Ambos modos recorren el ZIP por categoría.

| Modo | Qué pasa |
|---|---|
| **Combinar** | Los elementos nuevos se AÑADEN a lo que ya tengas. Las rutas con el mismo nombre no se colapsan — pueden salir duplicados; limpia con **Ajustes → Datos → Optimizar todas** o borrando por ruta. |
| **Reemplazar** | Cada categoría de la copia SUSTITUYE lo que tengas. Si la copia incluye rutas, todas las actuales se borran primero. Las categorías no marcadas al crear la copia NO se tocan al restaurar. |

**Regla:**

- Teléfono nuevo → **Reemplazar** (quieres el estado exacto del viejo).
- Recibes puntos de la copia de un amigo → **Combinar** (conservas los tuyos y añades los suyos).

La restauración va en streaming — rápida incluso con ZIP de cientos de MB. Si falla a medias, algunas categorías pueden estar aplicadas; repite para asegurar.

### Restauración en modo receta — descargar las regiones

Si la copia usó el modo **Receta** para los mapas offline, la restauración es instantánea pero verás las regiones en **Mapas → Mapas guardados** marcadas *«Aún no descargada · X mosaicos»* con un botón **Descargar**. Tócalo para volver a traer los mosaicos del servidor. Si la región usa mosaicos Thunderforest y aún no has pegado tu clave API, la app muestra un aviso único pidiendo añadirla primero en **Ajustes → Claves API**; una vez guardada la clave, vuelve a tocar Descargar.

### Restauración entre versiones de la app

Una copia v2 (creada con esta versión o posterior) no se abrirá en versiones anteriores y mostrará *«La copia con formato v2 es más reciente de lo que soporta esta app. Actualiza ApexGPS.»* — actualiza primero y luego restaura. Las copias v1 antiguas se siguen restaurando con la versión actual sin paso extra.

## Pasar a un nuevo teléfono

1. **En el viejo:** crea una copia con todo marcado. Envíatela por e-mail / guárdala en Drive.
2. **En el nuevo:** instala ApexGPS, ábrelo, da permisos, entra a tu e-mail / Drive.
3. **Descarga el ZIP** al nuevo teléfono, tócalo → restaura con **Reemplazar**.

Hecho. Rutas, puntos, mapas guardados y ajustes están allí.

## Protección ante restablecimiento / desinstalación

La copia automática de Android recupera *parte* de los ajustes (tema, fuente por defecto, clave API, grosor, tamaño de puntos, bloqueo de rotación) desde Google Drive al reinstalar. NO incluye rutas, puntos ni regiones — solo preferencias ligeras.

**La única forma fiable de conservar tus datos de senderismo ante una reinstalación es una copia ZIP.** Hazla antes de cualquier cambio de teléfono o actualización mayor del SO.

---

**Relacionado:** [Ajustes →](settings.md) · [Rutas →](tracks.md) · [Puntos →](waypoints.md)
