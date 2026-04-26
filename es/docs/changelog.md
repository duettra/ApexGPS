# Novedades

Cambios visibles para el usuario, más recientes primero. Para refactors internos / subidas solo de versión, ver el repo privado.

---

## 1.32.2 — 26 abr. 2026 — Tiempo activado por defecto + traducciones completas + botón atrás de Mapas

- **El tiempo viene activado de fábrica.** El chip de previsión y la línea «Tiempo aquí» en los waypoints se ven sin tener que activar un ajuste antes. Puedes desactivar el tiempo en **Ajustes → Tiempo** si prefieres no hacer llamadas de red — las instalaciones existentes mantienen tu ajuste anterior.
- **Traducciones completas para la función del tiempo.** Todos los textos del tiempo — el chip, la hoja (panel actual, franja de 24 horas, tendencias de humedad / presión, franja de 7 días, etiquetas de ocaso / UV / presión / rocío), las filas de Ajustes y el título del capítulo de la Guía — están ahora traducidos al alemán, francés, español, polaco y árabe. Las condiciones meteorológicas («Lluvia ligera», «Tormenta con granizo», «Parcialmente nublado», …) siguen el vocabulario meteorológico estándar de cada idioma.
- **Menú Mapas: el botón atrás cierra ahora una tarjeta abierta antes de salir.** Cuando **Descargar nueva zona** o **Mapas guardados** estaba desplegado, atrás se saltaba el menú Mapas y te devolvía directo al mapa. Ahora atrás cierra primero la tarjeta abierta; otra pulsación te lleva al mapa. Coincide con el comportamiento en otros sitios (subpantallas de Ajustes, multi-selección en las listas de rutas / waypoints).

---

## 1.32.1 — 25 abr. 2026 — Tiempo: pequeñas correcciones

- **Iconos de sol / luna correctos al cruzar medianoche.** La franja de tiempo de 24 horas mostraba glifos de luna en las horas de tarde del *día siguiente* (11:00, 14:00, 17:00) al abrir la hoja de noche. Cada hora elige ahora su propio orto / ocaso, así las horas diurnas siempre muestran los iconos lado sol.
- **La previsión del waypoint usa de verdad su altitud.** Cuando un waypoint en cumbre estaba prácticamente en la misma coordenada que tu lectura GPS, a veces se devolvía la previsión cacheada de la posición actual en lugar de una consulta fresca consciente de la altitud. En una cumbre de 1480 m la previsión salía ~9 °C demasiado cálida. La caché ahora también incluye la altitud como clave, así la altura guardada del waypoint se respeta siempre.

---

## 1.32.0 — 25 abr. 2026 — Tiempo: pulido por punto, sin overlays de mapa

Tras 1.31.0, los overlays de tiempo en rejilla no pasaron la prueba visual a niveles de zoom de senderismo — se veían como cuadrados de color sin alineación real con el terreno, y la fila inferior de controles (deslizador de overlay + chip + barra velocidad / altitud / distancia) ocupaba demasiada pantalla. Esta versión despeja el mapa y refuerza la hoja por punto, donde está el detalle útil.

- **Overlays de mapa retirados.** Sin radar de precipitación ni overlay de nubosidad sobre el mapa base, sin deslizador temporal. La pantalla **Ajustes → Tiempo** se reduce a un único interruptor maestro.
- **Hoja por punto más rica.** La hoja de tiempo (toca el chip o la línea «Tiempo aquí» de un waypoint) muestra ahora: panel actual con emoji del tiempo, temperatura, «sensación»; filas para viento / humedad / punto de rocío / presión / UV / ocaso; franja de 24 horas con iconos horarios + temperatura; tendencia de humedad (azul claro) y tendencia de presión (verde); y franja de 7 días con máxima / mínima + icono. Diseñada para caber en una pantalla de móvil normal.
- **La altitud del waypoint llega a la previsión.** Los waypoints con altitud guardada la pasan al modelo, así las previsiones de cumbre usan la altura real en vez de la altitud media del modelo. Igual para el chip de la posición actual — usa tu altitud GPS.
- **Chip alineado con la tarjeta del waypoint.** El texto del chip de la barra de stats coincide ahora con lo que ves al tocar un waypoint: emoji + temp + viento. Se añadió un fino separador entre el chip y la fila velocidad / altitud / distancia para que se lean como un solo panel.

---

## 1.31.0 — 25 abr. 2026 — Tiempo

ApexGPS muestra ahora información meteorológica de nivel senderismo desde APIs públicas gratuitas, totalmente opt-in.

- **Chip de previsión en la barra de stats.** Una vez actives el tiempo en **Ajustes → Tiempo**, un pequeño chip sobre la barra velocidad / altitud / distancia muestra las condiciones actuales en tu posición GPS: temperatura, viento, humedad. El chip se actualiza cada 15 minutos en línea e indica cuándo los datos están viejos o estás sin red (gris + reloj).
- **Hoja desplegable.** Toca el chip (o la nueva línea «Tiempo aquí» de un panel de waypoint) para el desglose — lecturas actuales, próximas 24 horas como curva de temperatura + barras de precipitación, y franja de 7 días con máx/mín e iconos.
- **Refresco manual.** Un botón ↻ en la cabecera fuerza una consulta fresca tras reconectar.
- **Overlays animados en el mapa.** Una nueva sección **Overlays** en el hub de Mapas añade dos interruptores independientes: radar de precipitación (lluvia animada con código de color, últimas 2 h + nowcast 30 min) y satélite de nubes (cima de nubes IR geoestacionario). No envían tu posición — son solo teselas, independientes del chip de tiempo.
- **Privacidad primero.** Toda la función está desactivada por defecto. Las previsiones vienen de Open-Meteo y el radar de RainViewer; ambas APIs públicas gratuitas, sin cuenta ni clave. Tu posición solo se envía si activas el chip explícitamente.

Lee el capítulo completo en **Ajustes → Guía → Tiempo**.

---

## 1.30.2 — 25 abr. 2026

- **El tap en la brújula respeta el bloqueo de rotación.** Pulsación larga en la brújula bloquea la rotación del mapa; bloqueada, un solo tap en la brújula ya no devuelve el mapa al norte. (Tendrías que volver a pulsar largo para desbloquear y luego tocar.) Esto restaura la intención del bloqueo — congelar el ángulo contra entradas accidentales, incluido un tap perdido en la propia brújula.
- **Avisos más cortos y menos invasivos.** Los mensajes «Eliminado …» / «Movido …» / «Llegada» / seguir-bloqueado / auto-pausa-localización ahora se muestran como un Toast Android breve (~2 s, overlay de sistema) en vez de un snackbar de 4 s que tapaba la parte baja del mapa. Puedes tocar otro waypoint nada más eliminar uno, sin esperar.

---

## 1.30.0 / 1.30.1 — 25 abr. 2026 — Calidad de grabación

La primera salida tras 1.29 (4 h 10 min, 9,98 km) reveló que la grabación live de track guardaba muchos más puntos de los necesarios y había absorbido una falsa caída de altitud por una lectura de altitud atascada. Ambos arreglados:

- **Grabaciones más ligeras y suaves.** Un nuevo filtro solo conserva un fix si te has movido al menos 5 m, han pasado 15 segundos o la altitud ha cambiado 3 m+. Los fixes muy imprecisos (>25 m) se descartan. En la prueba: ~4600 → ~1500 puntos guardados, sin cambio visible en la línea, distancia igual. Menos almacenamiento; exportes GPX más pequeños; el mismo trazo.
- **No más caídas falsas de altitud.** El fused location provider de algunos Android se atasca y devuelve la misma altitud cacheada (p. ej. `139 m` en una salida a 1200 m) durante minutos. La grabación trata ahora esas lecturas como «sin valor» en vez de persistir el número erróneo. El perfil de altitud muestra un hueco limpio en la ventana fallida en lugar de una bajada a cero, y los stats de subida / bajada solo reflejan cambios reales.
- **Altitud MSL en Android 14+.** Cuando está disponible, la grabación usa la altitud media respecto al nivel del mar, más honesta que el fallback WGS84 propenso al fallo anterior.

Si tienes una grabación previa a 1.30.0 con una altitud incorrecta, puedes regrabarla — pero la pantalla del track usa los puntos persistidos. No hay paso de migración.

---

## 1.29.0 — 24 abr. 2026

- **Grabación de ruta en vivo.** Toca la pastilla roja en la esquina superior izquierda del mapa para empezar a grabar tu salida. Un cronómetro en vivo `HH:MM:SS` reemplaza al punto; tócalo para **Pausar / Finalizar / Eliminar**. Tu trayecto se dibuja como una línea roja mientras te mueves. Al **Finalizar**, la grabación se guarda como nueva Ruta y el panel se abre automáticamente para revisar distancia, ascenso y perfil de altitud al momento.
- **Recortar ruta.** En la pantalla de detalle, **Recortar ruta** abre un diálogo con una mini-vista previa y dos manejadores arrastrables en el gráfico de altitud. Recorta un inicio malo (aún sin fix GPS) o una cola espuria (olvidaste tocar Finalizar) sin perder el resto. Destructivo — un paso de confirmación te dice exactamente cuántos puntos perderás.
- **Etiqueta de actividad por ruta.** La pantalla Detalle de ruta tiene un nuevo menú **Actividad**: Senderismo · Caminata · Correr · Ciclismo · Todoterreno · Parapente. Las grabaciones arrancan por defecto en Senderismo; las importadas sin etiqueta.
- **Elevación de punto.** El sheet de edición de puntos tiene un nuevo campo opcional **Elev (m)** — rellénalo cuando quieras llevar una altitud para una cumbre / collado conocido / etc. En blanco = sin elevación almacenada (igual que los puntos importados sin datos de elevación hoy en día).
- **Detalle de ruta + edición de punto renovados.** Tarjetas agrupadas, encabezados de sección, iconos en cada fila, icono específico de la actividad en el chip Actividad, **Eliminar** con borde rojo para casar con la acción destructiva, nueva estadística **Puntos** en la pantalla de ruta. La edición de puntos es más compacta — el formulario entero cabe ahora sobre la barra de navegación del sistema en la mayoría de teléfonos sin desplazamiento.
- **Recuperación tras muerte de proceso.** Si Android mata la app en plena grabación (poca memoria, forzar detención), la línea se conserva. Reabre la app y la grabación vuelve en pausa — reanudar, finalizar o descartar.
- **Ahorro de batería: cadencia GPS adaptativa.** Mientras grabas con la pantalla apagada, la cadencia de fixes GPS pasa de 2 s a 10 s para ahorrar batería. En cuanto desbloqueas el teléfono vuelve a 2 s para fluidez. Totalmente automático.
- **Protección ubicación del sistema.** Tocar grabar con el interruptor de ubicación del sistema Android apagado ahora muestra un mensaje con un acceso directo a **Ajustes** en lugar de arrancar silenciosamente una grabación muerta.
- **Aviso de no-fix.** Si tocas grabar antes de que el GPS tenga fix, un breve aviso *«Adquiriendo GPS…»* te explica por qué aún no ha empezado la línea. La grabación arranca en cuanto llega el primer fix.
- **Eliminado:** el botón de pánico opcional. La esquina superior izquierda ahora pertenece a la pastilla de grabación.

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
