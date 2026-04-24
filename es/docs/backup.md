# Copia y restauración

ApexGPS guarda todo **localmente en tu teléfono**. Sin sincronización en la nube. Si reinicias de fábrica, cambias de teléfono o desinstalas, **tus rutas, puntos y regiones offline se pierden** a menos que hayas hecho una copia.

La copia es manual pero sencilla. Hazla periódicamente si tienes datos que no quieres perder.

## Qué incluye una copia

- **Todas las rutas** (datos GPX, nombre, color, visibilidad).
- **Todos los puntos** (nombre, descripción, coords, altitud, color, símbolo).
- **Todas las regiones guardadas** (bundles de mosaicos — pueden ser grandes).
- **Todos los ajustes** (tema, fuente por defecto, grosor, tamaño de puntos, bloqueo de rotación).

Qué **no** incluye:

- La **caché de navegación** (mosaicos auto-guardados por uso general). No se incluye por regenerable y potencialmente enorme. Las regiones guardadas sí; la caché no.
- La **clave API de Thunderforest** se guarda con los ajustes, así no hay que reintroducirla.

## Crear una copia

1. **Menú → Ajustes → Datos → Copia**.
2. Opcional: desmarca categorías que no quieras (las regiones guardadas son lo más grande — déjalas fuera si solo quieres rutas/puntos).
3. Toca **Crear copia**.
4. El ZIP queda en almacenamiento privado. Se abre un diálogo para compartir:
   - **Google Drive / Dropbox / OneDrive** — resguardo en nube.
   - **Enviármelo** por e-mail / chat.
   - **Guardar en Descargas** por un gestor de archivos.

El ZIP se llama por ejemplo `apexgps-backup-2026-04-19.zip`. La fecha va en el nombre.

**Una copia con regiones offline puede tardar un par de minutos** y generar un ZIP grande (50–500 MB según cuántas regiones). La UI muestra progreso.

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
