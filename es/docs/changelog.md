# Novedades

Cambios visibles para el usuario, más recientes primero. Para refactors internos / subidas solo de versión, ver el repo privado.

---

## 1.28.0 — 24 abr. 2026

- **Árabe añadido.** العربية se une al alemán, francés, español y polaco junto al inglés. Seis idiomas de interfaz en **Ajustes → Apariencia → Idioma**.
- **Panel de punto ahora traducido.** Tocar un punto mostraba antes «Elev 145 m · Dist 0,42 km» en inglés — sin importar el idioma de la app. Ahora cambia con él (p. ej. «Alt 145 m · Dist 0,42 km»).
- **Los números siguen siendo dígitos occidentales en todos los idiomas.** Coordenadas, distancias, altitudes, rumbos — siempre `25.165`, `145`, `0.42`. Coherente con Google Maps / WhatsApp.

---

## 1.27.0 — 23 abr. 2026

- **Cinco idiomas de interfaz.** Alemán, francés, español, polaco e inglés. Elígelo en **Ajustes → Apariencia → Idioma**, o «Idioma del sistema» para seguir el del teléfono.
- **Guía sin conexión en tu idioma.** Los 11 capítulos de la guía (Ajustes → Acerca de → Guía) están traducidos.
- **El idioma sobrevive a una restauración.** El idioma elegido está incluido en el ZIP.
- **Barra de stats también traducida.** VEL / ALT / DIST cambian con el idioma.

---

## 1.26.2 — 22 abr. 2026

- **Clave API de Thunderforest cifrada en reposo.** La clave que pegas en **Ajustes → Avanzado** se guarda en una bóveda respaldada por Android Keystore, ya no en texto plano. Las claves existentes migran automáticamente al primer inicio. Las copias que incluyen ajustes llevan la clave en el ZIP (necesario para portabilidad) — un nuevo aviso rojo en el diálogo de copia lo recuerda.
- **Restauración más segura.** La restauración rechaza ZIPs con directory traversal, limita entradas a 100 000, tamaño por entrada a 500 MB y total descomprimido a 2 GB. Copias malformadas ya no pueden llenar tu almacenamiento ni salir del directorio de copia.
- **Botón Cancelar en la copia.** Durante una copia en curso puedes tocar **Cancelar** bajo el botón ocupado para abortar sin esperar.
- **Progreso de import GPX.** Snackbar «Importando GPX…» durante imports grandes — la app ya no parece congelada.
- **Servicio de ubicación más fiable en Android 14+.** El servicio GPS arranca correctamente en Android 14 y 15 (antes, silenciosamente cerrado en ciertos casos). Alcance de wake-lock más ajustado — debería mejorar la batería en sesiones largas.
- **Corrección de vista previa de mosaico + higiene en segundo plano.** La vista previa en la pantalla detalle de mapa guardado carga sin bloquear la UI. Interno: el servicio de descarga de mosaicos ya no puede ANR al cerrarse. Las builds de release ya no expulsan logs de depuración.
- **Eliminado:** el enlace Buy-me-a-coffee en Ajustes → Acerca de. ApexGPS sigue siendo gratis sin anuncios, sin tracking, sin nube.
- **Interno (para curiosos):** Room ahora trae migraciones explícitas (1→2→3); las actualizaciones preservan tus rutas y puntos aunque cambie el esquema. El wipe en downgrade sigue — sideloadear un APK más viejo sobre uno más nuevo reinicia la base.

---

## 1.26.1 — 22 abr. 2026

- **Vista previa del detalle de mapa offline — sesgo corregido.** La vista previa en **Menú → Mapas offline guardados → [toca una región]** se pintaba fuera de sus límites, solapando filas de estadísticas y el botón «Mostrar en el mapa». Ahora se recorta correctamente a su rectángulo 1,6:1.
- **Enlace «Ver en línea» in-app** en Ajustes → Acerca de apunta a `apexgps.duttra.de/docs/` (la guía renderizada) en lugar de la vista cruda de GitHub.
- **Buy me a coffee.** Nueva sección Soporte en **Ajustes → Acerca de**. ApexGPS sigue siendo gratis sin anuncios ni tracking — si te resulta útil, una propina ayuda a seguir añadiendo funciones.

---

## 1.26.0 — 21 abr. 2026

- **Guía de usuario sin conexión.** La guía completa de 10 capítulos va incluida en la app — abre **Ajustes → Acerca de** y toca cualquier capítulo para leer sin internet. Los enlaces entre capítulos funcionan dentro de la app; los externos abren el navegador.
- **Cargar datos de ejemplo.** Nuevo botón en **Ajustes → Datos** carga 3 puntos (Cumbre / Mirador / Inicio de sendero) y 3 rutas de distintas longitudes y perfiles. Para probar la app sin GPX propios. Borrables después — tras importar son rutas/puntos normales.
- **Navegar activa el GPS automáticamente.** Tocar Navegar en una ubicación compartida o un punto ahora activa la ubicación en vivo si estaba apagada. Se acabaron los bloqueos «Adquiriendo GPS…» cuando querías arrancar la navegación.
- **El pan del mapa vuelve a desbloquear el seguimiento.** Regresión de builds 1.2x: con actualizaciones GPS continuas, el mapa regresaba a ti cada segundo incluso tras arrastrar. Arrastra el mapa → la cámara se desbloquea (FAB en azul medio) como antes; tu triángulo sigue en su sitio.
- **Símbolos de punto que antes crashaban.** Importar un GPX con símbolos Mirador / Collado / Cascada / Picnic / Agua potable / Hito / Ruinas / Aseos podía crashear la app al renderizar. Corregido — los 32 símbolos se renderizan correctamente.

---

## 1.25.x — 21 abr. 2026

- **Importar GPX desde la lista Rutas** (icono carpeta arriba a la derecha). Igual en la lista Puntos. El FAB de importar del mapa se fue — las listas gestionan imports.
- **Añadir punto por coordenadas** — «+» azul en Puntos abre el sheet de edición con Lat/Lon vacíos. Escribe o pega una cadena `lat, lon` en Latitud (se separa automáticamente).
- **Editar las coordenadas de un punto.** Lat y Lon son editables con validación inline (lat ∈ [-90, 90], lon ∈ [-180, 180]).
- **FAB Seguirme movido al fondo** de la columna derecha — más cerca del pulgar. Capas encima, Medir más arriba.

---

## 1.24.x — 19 abr. 2026

- **Brújula de navegación a pantalla completa.** Durante la navegación, toca 🧭 en la barra para abrir una gran brújula analógica: distancia / ETA / velocidad / altitud arriba, esfera rotatoria con aguja azul apuntando al destino, lat/lon/rumbo/precisión abajo. Arrastra hacia abajo para minimizar. Ver [Compartir → La brújula](share-and-navigate.md#la-brújula-de-navegación-pantalla-completa).
- **Compartir un punto.** El panel del punto tiene un botón Compartir junto a Navegar y Editar. Envía el punto por cualquier app de mensajería; con ApexGPS el destinatario lo abre como ubicación compartida, que puede Guardar.
- **Barra de nav + barra inferior más limpias.** La nav muestra rumbo + ETA (rumbo en azul — actualiza), la distancia vive en el campo DIST. Se acabaron los números duplicados.
- La aguja de la brújula se integra suavemente con el pivote central (pulido visual).

## 1.23.0 — 19 abr. 2026

- **Navegar a cualquier punto** directamente desde su panel. Toca el icono de persona caminando junto a Editar — la misma línea punteada azul claro + distancia/rumbo en vivo + auto-stop a 20 m que la nav de ubicación compartida. Ver [Puntos → Navegar a un punto](waypoints.md#navegar-a-un-punto).

## 1.22.2 — 19 abr. 2026

- **Enlace a la guía** en Ajustes → Acerca de. Abre esta documentación en el navegador.

## 1.22.0 — 19 abr. 2026

- **Botón de pánico** (opt-in). Pastilla roja ⚠ arriba a la izquierda. Toque → abre el panel de compartir y activa el GPS si hace falta. Actívalo en **Ajustes → Apariencia → Botón de pánico**. Ver [Compartir → Botón de pánico](share-and-navigate.md#botón-de-pánico-opcional).

## 1.21.0 — 19 abr. 2026

- **Seguirme: panea libremente.** Arrastrar el mapa ya no pelea con el GPS — el triángulo sigue, pero el mapa se queda donde lo pones. Toca el botón para recentrar. Pulsación larga para apagar el GPS al instante. Tres estados visibles (off / bloqueado / desbloqueado).
- **Brújula hacia norte animada** en lugar de saltar. Menos brusco al volver al norte.

## 1.20.0 — 19 abr. 2026

- **Navegar a una ubicación compartida.** Cuando alguien te comparte un enlace `apexgps.duttra.de`, toca Navegar en la barra inferior para dibujar una línea punteada azul claro de tu posición a la suya con distancia y rumbo en vivo. Auto-stop a 20 m. Ver [Compartir → Navegar a una ubicación compartida](share-and-navigate.md#navegar-a-una-ubicación-compartida).
- **Pista visual para ubicaciones compartidas.** Una diana roja aparece en el punto compartido. [Guardar] como punto o [Descartar] para limpiar.

## 1.19.0 — 19 abr. 2026

- **Lista Puntos: filtro + orden.** Filtrar por color o símbolo, ordenar por fecha / nombre / más cercano. Igual que Rutas. Ver [Puntos → La lista de puntos](waypoints.md#la-lista-de-puntos-menú--puntos).
- **Formato del mensaje compartido más limpio** — URLs etiquetadas (`ApexGPS:` / `Google Maps:`) con línea en blanco encima.

## 1.18.x — 19 abr. 2026

- **Compartir tu ubicación actual.** Toca el triángulo azul → panel con altitud, precisión, hora, batería → Compartir por WhatsApp, SMS, e-mail, etc. Flujo completo en [Compartir y navegar](share-and-navigate.md).
- **App Links.** Las ubicaciones compartidas desde ApexGPS abren directamente la app en dispositivos que la tienen, con marcador rojo.
- **Fallback web** — si el destinatario no tiene ApexGPS, el enlace abre una página con vista previa + botón para Google Maps.

## 1.17.6 — 18 abr. 2026

- **Hub Mapas** rediseñado. Descargar nueva zona y mapas offline guardados ahora en una pantalla como tarjetas expandibles. Ver [Mapas sin conexión](offline-maps.md).
- Corrección de esquinas negras al rotar (ya no hay triángulos negros en los bordes).

## 1.16.0 — 17 abr. 2026

- **Ajustes** reorganizados en subpantallas (Apariencia / Almacenamiento / Datos / Claves API / Acerca de) con ayuda inline.
- **Tamaño de puntos** (Pequeño / Normal / Grande / XL) en Apariencia.
- **Rotación bloqueada al iniciar** — para quienes odian las rotaciones accidentales.

## 1.15.0 y anteriores

- App núcleo: import GPX, lista de rutas, puntos con 32 símbolos, descargas offline, brújula + rotación, medir distancia, copia/restauración a ZIP, optimización de ruta.

---

*Para nivel de detalle de bug-report o contexto de desarrollador, ver el [repo privado](mailto:sandwalker.one@proton.me) — contacta al desarrollador para acceso.*
