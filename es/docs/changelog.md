# Novedades

Cambios visibles para el usuario, más recientes primero. Para refactors internos / subidas solo de versión, ver el repo privado.

---

## 1.41.1 — 16 de junio de 2026 — Precisión y navegación

- **Desnivel realista en rutas importadas** — las rutas importadas desde otro dispositivo (p. ej. un reloj GPS) mostraban un ascenso total enormemente exagerado. Ahora indican una cifra realista, acorde con lo que registra la misma excursión en tu teléfono.
- **Optimizar más inteligente** — el cuadro Optimizar ahora te sugiere el nivel de detalle adecuado (puedes cambiarlo), mantiene una ruta igual de suave tanto si es corta como larga, y funciona también en grabaciones más cortas, no solo en importaciones enormes.
- **Mejor brújula de navegación** — apunta en la dirección correcta al conducir (sigue tu sentido de marcha por GPS, en lugar de la brújula que el metal del coche distorsiona), se mueve con más suavidad, y la hora de llegada (ETA) se vuelve verde cuando te acercas y roja **«se aleja»** cuando te alejas del destino.

---

## 1.41.0 — 9 de junio de 2026 — Guía por ruta

- **Seguir una ruta** — elige cualquier ruta guardada o importada y ApexGPS te guía por ella. Si te desvías, la app te avisa con un pitido y una vibración, incluso con la pantalla apagada, y una barra muestra la distancia que queda. Las flechas a lo largo de la ruta y una bandera en el destino indican el camino; toca el botón de invertir para cambiar de sentido.
- **Volver al inicio** — durante una grabación, un toque te guía de vuelta al punto de partida: rehaz tu trayecto exacto o vuelve en línea recta.
- Corregido: el botón de centrar mi ubicación quedaba oculto tras la barra de guía.

---

## 1.40.2 — 6 de junio de 2026 — Corrección de la altitud grabada

- Corregido un error en teléfonos sin barómetro donde las vibraciones (p. ej. en bicicleta de montaña) podían arrastrar la altitud grabada hacia valores imposibles — la altitud ahora queda anclada a mediciones GPS reales.
- Las altitudes físicamente imposibles (por debajo de −500 m o por encima de 9000 m) ya no pueden grabarse, sea cual sea su origen.

---

## 1.40.1 — 5 de junio de 2026 — Correcciones de la tarjeta de estadísticas de grabación

- La tarjeta de estadísticas de grabación en vivo ahora mantiene su reloj al día incluso con la grabación en pausa.
- Mejor rendimiento en grabaciones largas — las estadísticas en vivo solo se recalculan mientras la tarjeta está abierta.

---

## 1.40.0 — 4 de junio de 2026 — Tarjeta de estadísticas de grabación en vivo

- **Toca el cronómetro de grabación para abrir una tarjeta de estadísticas en vivo** — duración, distancia, altitud actual (con su fuente), ascenso total y el reloj, todo actualizándose sobre la marcha.
- Pausar, Finalizar y Eliminar son ahora botones de icono claros, cada uno con su confirmación.
- El menú de grabación y los demás menús del mapa ahora coinciden: redondeados, translúcidos y siguen tu ajuste de Tamaño de texto en la app.

---

## 1.39.1 — 4 de junio de 2026 — Correcciones de regreso al mapa y de la Guía de usuario

- Corregido un **mapa en negro** ocasional al volver al mapa desde un menú — ahora se redibuja al instante en lugar de quedarse en blanco hasta que desplazabas.
- El texto de la **Guía de usuario** sin conexión ahora escala con el ajuste **Tamaño de texto** de la app, como el resto de la app.

---

## 1.38.0 — 3 de junio de 2026 — Tamaños de texto y de controles ajustables

- Nuevo deslizador **Tamaño de texto** en Ajustes → Apariencia (50–150 %) que escala todo el texto de la app sobre tu ajuste de fuente de Android.
- Nuevo deslizador **Tamaño de los controles del mapa** — redimensiona los botones del mapa, la brújula y la pastilla de grabación; redúcelos para recuperar área de mapa en un teléfono pequeño.
- El ajuste de tamaño de waypoint es ahora también un deslizador suave.

---

## 1.37.15 — 2 de junio de 2026 — La altitud del waypoint funciona sin conexión

- Añadir un waypoint en el mapa ahora **rellena previamente su altitud a partir de tu altitud GPS actual**, así funciona en modo avión o sin señal. Puedes editarla, o consultar el valor preciso más tarde cuando tengas conexión.

---

## 1.37.14 — 2 de junio de 2026 — Las grabaciones nuevas empiezan sin actividad

- Una grabación nueva ya no toma «Senderismo» por defecto — empieza sin actividad seleccionada (mostrada como «Ninguna»), así eliges tú la correcta. Los tracks existentes no cambian.

---

## 1.37.13 — 1 de junio de 2026 — Optimizar muestra una vista previa del trazado

- El diálogo Optimizar ahora muestra una **vista previa del trazado antes/después** (original tenue, resultado optimizado en negrita encima) para que veas el enderezado antes de guardar.

---

## 1.37.12 — 1 de junio de 2026 — Optimizar limpia el ruido GPS de los cañones

- Optimizar ahora **limpia el track antes de simplificarlo** — suaviza la altitud ruidosa y endereza el «garabato» GPS que se forma en cañones profundos, conservando los zigzags reales. Validado contra un reloj con barómetro en una marcha de cañón. La vista previa y Guardar como nuevo siguen manteniendo a salvo tu original.

---

## 1.37.11 — 1 de junio de 2026 — Recortar: Guardar como nuevo

- **Recortar** un track ahora ofrece **Guardar como nuevo** (como Optimizar) — conserva la versión recortada como un track aparte y deja el original intacto.

---

## 1.37.10 — 1 de junio de 2026 — Ascenso y descenso precisos

- Corregido el **ascenso/descenso total** desorbitadamente inflado en teléfonos sin barómetro (una marcha de cañón mostraba +17 000 m en lugar de ~2250 m). La cifra ahora elimina el ruido de la altitud antes de sumarla, igual que calculan el desnivel Strava y Komoot. Se aplica a todos los tracks guardados e importados.

---

## 1.37.5 — 21 de mayo de 2026 — Overlay de diagnóstico GPS (opcional)

- Nuevo overlay opcional de **Diagnóstico GPS** (Ajustes → Avanzado) que muestra en vivo la calidad del fix, la precisión y el detalle de la fuente de altitud — útil para entender grabaciones con señal complicada.

---

## 1.37.0 — 17 de mayo de 2026 — Altímetro barométrico y mejor altitud

- En teléfonos con barómetro, ApexGPS lo usa ahora como **fuente principal de altitud** — estable a nivel submétrico y libre del ruido del GPS y de los cortes en los cañones.
- El ascenso/descenso usa ahora un **umbral de 5 m** (el estándar de Strava/AllTrails); los tracks existentes mostrarán cifras más pequeñas y realistas.
- Además, una serie de mejoras de precisión para teléfonos **sin** barómetro — varias comprobaciones de plausibilidad de la altitud y suavizado para rechazar picos del GPS, y un campo opcional de precisión GPS en los GPX exportados.

---

## 1.36.0 — 17 de mayo de 2026 — Mejor grabación en cañones

- La grabación ahora **captura más puntos en cañones y terreno cerrado** (captura cruda con controles de densidad más inteligentes), así los descensos en cañones profundos no se pierden.
- Nueva opción **Limpiar saltos GPS** en Optimizar para arreglar tracks ruidosos a posteriori.

---

## 1.35.2 — May 15, 2026 — Papelera fiable · El icono solo aparece al arrastrar · Tocar cerca de los puntos intermedios funciona

- **El icono de la papelera ahora es solo para arrastrar — aparece en cuanto mantienes pulsado un vértice o un punto intermedio, se enciende en rojo al pasar por encima y desaparece al soltar.** Antes, el icono estaba siempre visible en los modos de regla y planificación, pero el gesto de mantener pulsado y arrastrar para eliminar no era obvio para la mayoría — veían la papelera pero no acertaban a meter un punto dentro. Ahora la papelera aparece solo cuando has cogido un punto, así la affordance queda clara.
- **Soltar un punto intermedio en la papelera ahora lo elimina de forma fiable.** Dos fallos intermitentes corregidos: (1) la sacudida al soltar dejaba a veces las coordenadas unos píxeles fuera de la zona de la papelera aunque el icono estuviera encendido en rojo — ahora el propio brillo rojo renderizado es la señal, así que si ves rojo al soltar, el punto se elimina; (2) en algunas ocasiones un punto intermedio soltado sobre la papelera se quedaba visualmente aparcado en el icono hasta el siguiente cambio de la lista — ahora la línea vuelve limpiamente a su forma original en cada cancelación.
- **Tocar la línea cerca de un punto intermedio ya no deforma el segmento existente.** Antes, si intentabas tocar la línea para añadir un nuevo vértice pero caías cerca del punto intermedio entre dos vértices existentes, el segmento existente se distorsionaba — tu toque se reinterpretaba como un arrastre casi nulo que insertaba un vértice justo en el punto intermedio. Ahora el toque se reconoce como toque y se añade un nuevo vértice al final de la lista, exactamente igual que al tocar en cualquier otro punto del mapa.

---

## 1.35.1 — 15 de mayo de 2026 — Correcciones de la papelera · La planificación de ruta empieza donde tocas

- **La papelera ya funciona con el mapa rotado.** Antes, arrastrar un pin de la regla o un vértice de planificación hasta el icono de la papelera arriba a la derecha fallaba en silencio si el mapa estaba rotado lo más mínimo — el icono no se encendía en rojo y soltar no borraba. La prueba de colisión lee ahora las coordenadas crudas del dedo en lugar del marco interno del mapa rotado, así la papelera funciona con cualquier orientación.
- **Borrar el primer pin de la regla en modo seguir ya no destruye el siguiente pin.** Al medir con modo seguir activado, el primer pin (pin A) sigue solo tu posición en vivo. Mandarlo a la papelera antes fallaba de forma confusa: A parecía volver con el siguiente fix GPS, y el pin que habías puesto justo después (B) desaparecía en silencio. Ahora mandar A a la papelera lo deja fuera durante el resto de la sesión de medición, y B y los demás pines se quedan donde estaban. Desactiva y reactiva el modo regla para volver a sembrar A en tu posición actual.
- **La planificación de ruta ya no coloca solo el vértice 1 en tu posición actual.** Planificar es un flujo deliberado de zona del mapa — la mayoría de la gente desplaza el mapa hasta la zona que quiere planificar y luego entra en modo planificación. Auto-sembrar el vértice 1 en tu posición GPS sorprendía a quien planificaba rutas remotas. La planificación arranca ahora vacía; el primer toque coloca el vértice 1 exactamente donde tocas, en cualquier zona a la que hayas desplazado el mapa.

---

## 1.35.0 — 14 may. 2026 — Compartir rutas y puntos visibles · Ahorro de batería a alta velocidad · GPX desde apps de mensajería

- **Comparte todo lo visible en el mapa con un solo toque.** Un nuevo **icono de compartir** aparece arriba a la izquierda del mapa, justo a la izquierda del menú ☰. Tócalo y se abre una hoja que lista cada ruta + punto visible dentro de tu área actual. Marca lo que quieras, toca **Compartir**, elige WhatsApp / correo / Drive — todo el paquete sale como un único archivo `.gpx` con el nombre del área que estabas viendo (p. ej. `ApexGPS-Wadi-Bani-Khalid-2026-05-14.gpx`). Hay dos puntos de entrada más que usan la misma hoja: una tarjeta **Compartir rutas y puntos visibles** en el menú Mapas (usa el área que tenías abierta al abrir el menú), y un icono **compartir** en la barra superior de las listas Rutas / Puntos cuando mantienes pulsado para seleccionar varios — empaqueta los elementos seleccionados directamente sin hoja extra.
- **Ahorro de batería a alta velocidad.** Un nuevo interruptor en **Ajustes → Avanzado** (activado por defecto) reduce el muestreo GPS de una vez por segundo a una vez cada 10 segundos cuando te mueves a más de 36 km/h — coche, tren, bicicleta eléctrica rápida. Las rutas en carretera se siguen grabando con limpieza; la precisión de carril se reduce al conducir. Recorta aproximadamente la mitad del consumo GPS en el tramo de autopista de un viaje sin pérdida visible de la forma de la ruta. Desactívalo si necesitas muestreo completo a velocidad.
- **Abrir archivos `.gpx` con un toque desde WhatsApp / Telegram / Signal / Outlook.** Antes, los adjuntos de estas apps caían al visor de texto del sistema porque anuncian el archivo como `application/xml` genérico en vez del tipo MIME GPX canónico. ApexGPS acepta ahora también esos tipos genéricos — toca una sola vez un adjunto `.gpx` en cualquier app de mensajería y el menú «Abrir con» del sistema muestra ApexGPS como opción de primer nivel.
- **Copias de seguridad de mapas sin conexión en modo receta (multiplataforma).** Ajustes → Datos → Copia de seguridad sustituye la única casilla «Regiones de mapa guardadas» por un selector de tres opciones: **No incluir** / **Receta** (pequeño — lista qué regiones volver a descargar, funciona entre Android e iOS) / **Mosaicos completos** (el comportamiento antiguo — incrusta los paquetes de mosaicos, grande pero restaurable sin conexión, solo Android). Una copia en modo receta ronda los 80 KB incluso con una docena de regiones; restaurarla añade filas de marcador en **Mapas → Mapas sin conexión guardados** con un botón **Descargar** para traer los mosaicos reales bajo demanda.
- **El estilo de mapa de pago se oculta sin clave.** La entrada **Outdoors (Thunderforest)** desaparece ahora del selector de estilo del mapa y del selector de descarga de región sin conexión hasta que pegues una clave API en **Ajustes → Claves API**. Antes, elegirlo sin clave caía silenciosamente a OpenTopoMap sin explicación. Pega una clave → la entrada vuelve a aparecer en ambos menús.

---

## 1.34.2 — 14 may. 2026 — Ocultar fuentes de mosaicos de pago sin clave

- **El estilo «Outdoors (Thunderforest)» se oculta ahora por completo hasta que pegues una clave API.** Antes, elegirlo sin clave caía silenciosamente a OpenTopoMap sin explicación — tocabas Outdoors, veías mosaicos de OpenTopoMap y te preguntabas por qué. Tanto el selector de estilo del mapa como el selector de Descargar región sin conexión omiten ahora la entrada Outdoors hasta que **Ajustes → Claves API → Thunderforest** tenga una clave guardada. Pega una clave → Outdoors reaparece al instante en ambos menús.

---

## 1.34.1 — 13 may. 2026 — Copia de seguridad formato v2 (recetas de regiones offline, multiplataforma)

- **Las copias de seguridad ya pueden saltarse los pesados paquetes de mosaicos y guardar una «receta» en su lugar.** Ajustes → Datos → Copia de seguridad sustituye la única casilla «Regiones de mapa guardadas» por un selector de tres opciones: **No incluir** / **Receta** (pequeño — lista qué regiones volver a descargar, funciona entre Android e iOS) / **Mosaicos completos** (grande — el comportamiento antiguo, solo Android). Una copia con receta ronda los 80 KB incluso con una docena de regiones; la equivalente con mosaicos completos podría ser de 50–500 MB. Restaura una copia en modo receta y la lista de mapas guardados se rellena con filas marcadas «Aún no descargada · X mosaicos» más un botón **Descargar** — tócalo para volver a descargar desde el servidor de mosaicos original (usa tu caché actual + una descarga nueva para el resto).
- **Una copia hecha en Android ya se puede restaurar en iOS y al revés — para todo excepto los paquetes de mosaicos completos.** Rutas, puntos, ajustes y recetas de regiones viajan limpiamente. El modo mosaicos completos sigue siendo solo Android porque iOS no incluye un lector MBTiles, pero el modo receta cubre las necesidades prácticas de la mayoría (reconstruir en el teléfono nuevo y aceptar una breve redescarga de las regiones que te importan).
- **Restaurar una receta de estilo Outdoors te recuerda configurar primero la clave API.** Si una receta restaurada apunta a Thunderforest y no tienes clave guardada, tocar **Descargar** muestra un aviso único que te dirige a **Ajustes → Avanzado → Clave API Thunderforest**; con la clave guardada, la descarga arranca con normalidad.

---

## 1.34.0 — 13 may. 2026 — Ajuste de tamaños · Deportes acuáticos · Progreso de restauración en vivo · Plurales correctos

- **Los marcadores de waypoint son aproximadamente un 25 % más grandes por defecto.** «Normal» (1,0×) ahora se renderiza al tamaño que antes tenía «Grande». Si los waypoints parecen pequeños, el selector sigue ofreciendo Pequeño / Normal / Grande / XL — Ajustes → Apariencia → Tamaño de waypoint. Tu ajuste actual se mantiene; quizá bajar un nivel ya que toda la escala ha crecido.
- **Deslizadores de recorte — los tiradores redondos funcionan en cualquier punto.** Antes, sólo la línea vertical de cada tirador respondía; tocar el botón redondo de abajo a menudo no hacía nada porque la zona táctil no llegaba hasta el fondo. Corregido — ambos tiradores redondos ahora se agarran desde cualquier punto del círculo más una pequeña franja debajo.
- **Nuevo tipo de actividad: Deportes acuáticos.** Selecciónalo desde Detalles del track → Actividad para etiquetar sesiones de pádel, vela, surf, kayak o cualquier otro deporte de agua. Mismo icono de ola que el waypoint Cascada.
- **Restaurar una copia de seguridad ahora muestra progreso en vivo.** Una copia grande (cientos de tracks, miles de waypoints) antes bloqueaba la app sobre un indicador durante varios minutos sin señal de progreso — fácil confundir con un fallo. El botón Restaurar ahora está sobre una barra de progreso + leyenda («Restaurando track N de M…» / «Restaurando waypoint N de M…») que avanza por track y cada 100 waypoints.
- **Polaco y árabe ahora muestran etiquetas correctamente pluralizadas.** 13 cadenas con contadores («X tracks», «Y waypoints», «hace Z minutos» etc.) pasan ahora por reglas plurales reales. Polaco obtiene sus 4 formas completas; árabe sus 6. Inglés / alemán / francés / español ya eran gramaticalmente correctos; la mecánica subyacente ahora pasa por el mismo camino de forma coherente.

---

## 1.33.8 — 10 may. 2026 — Cola del primer pin de la regla y el planificador de rutas

- **Tocar la herramienta de regla o el FAB de planificación antes de que esté listo tu fix GPS hace que el primer punto se coloque solo en cuanto llega tu posición.** Antes, tocar mientras el GPS aún se calentaba dejaba un inicio vacío — tenías que tocar el mapa a mano para soltar el pin A. Ahora la app muestra «Adquiriendo fix GPS…» en el botón y deja en cola el auto-emplazamiento del primer punto; cuando llega el fix, el pin A aparece en tu posición actual y el seguimiento en vivo toma el relevo con normalidad. Refleja el mismo comportamiento de cola que recibió el FAB de grabación en 1.33.7. Tocar a mano para soltar un pin mientras tanto cancela la cola, así nunca pierdes un toque.

---

## 1.33.7 — 10 may. 2026 — Importación tolerante de GPX · Privacidad en Acerca de · Auto-inicio de grabación

- **Las importaciones de archivos GPX con coordenadas mal formadas ya no fallan por completo.** Un punto de track o waypoint con un valor `lat` / `lon` mal formado abortaba antes la importación entera. La app salta ahora el punto malo y sigue importando el resto — un punto malo en una marcha de 10 000 puntos ya no echa a perder el archivo. Los límites máximos absolutos (10 000 tracks, 100 000 waypoints, 500 000 puntos por track) siguen activos para evitar quedarse sin memoria.
- **Política de privacidad directamente bajo Ajustes → Acerca de.** Una nueva fila «Política de privacidad» se sitúa debajo de Guía de usuario; tócala para leer la política dentro de la app, sin internet. El mismo contenido está espejado en `apexgps.duttra.de/privacy.html` (la URL de privacidad de Play Store) para quien quiera leerla antes de instalar.
- **Toca Grabar antes de tu primer fix GPS y la grabación arranca sola cuando llegue el fix.** Antes, tocar Grabar antes de recibir ningún fix iniciaba al momento un track vacío de migas — si tocabas Detener antes de que llegara ningún fix, guardabas una ruta con cero puntos. Ahora el aviso dice «Adquiriendo fix GPS…» y la grabación se dispara sola en el momento en que llega el primer fix no nulo — no hace falta un segundo toque.

---

## 1.33.6 — 9 may. 2026 — Fiabilidad de la zona-papelera tras volver desde recientes

- **La zona-papelera para borrar un vértice durante la planificación o la medición vuelve a funcionar de forma fiable después de minimizar la app y reabrirla desde Recientes.** Un fallo latente hacía que el gesto de "arrastrar un vértice a la papelera para borrarlo" dejase de funcionar en silencio después de que la ventana de la app se desacoplase y se volviera a acoplar (minimizar → tocar desde Recientes). Los límites de la zona-papelera se quedaban fijados en las coordenadas previas a la minimización mientras la posición del mapa se seguía actualizando, así que los soltados ya no se detectaban. La prueba de colisión ahora lee los límites en fresco en cada evento de arrastre (y solo cuando el icono de la papelera está efectivamente acoplado a la ventana), por lo que la zona-papelera se mantiene operativa a través de cualquier número de ciclos de regreso. Ya no hace falta reiniciar la app como solución alternativa.
- **Interno: limpiezas de build para la revisión de producción de Play Store.** Una dependencia de UI actualizada (`androidx.activity:activity-compose` 1.9.3 → 1.10.1) para resolver los avisos de Vitals señalados en la revisión 1.33.5 ("edge-to-edge puede no mostrarse a todos los usuarios") — pura limpieza, sin cambios de comportamiento. Extracción de símbolos de depuración nativos habilitada para builds release (hoy sin efecto porque las únicas bibliotecas nativas del AAB se entregan sin símbolos por parte de Google — se activa automáticamente si alguna futura dependencia los entrega).

---

## 1.33.5 — 7 may. 2026 — Tamaño de caché ajustable + ruta de bienvenida en la primera instalación

- **Elige cuánto espacio asignar al caché de mosaicos.** Ajustes → Caché offline ofrece ahora cuatro valores: 250 MB / 500 MB (predeterminado) / 1 GB / 2 GB. El nuevo límite se aplica al instante — no hace falta reiniciar. Las regiones offline guardadas se almacenan aparte y no cuentan aquí, así que cambiar este valor nunca borra una región que descargaste a propósito.
- **Una ruta de bienvenida en cada instalación nueva.** Una grabación real de la **travesía del Watzmann** (Berchtesgaden, Alemania) — Wimbachbrücke → Watzmannhaus → Hocheck → Mittelspitze → Südspitze → Wimbachgrieshütte → Wimbachbrücke, bucle de ~22,6 km / +2250 m / unas 10–12 h de marcha — se importa automáticamente la primera vez que abres la app. Vienen tres puntos destacados (inicio Wimbachbrücke, DAV Watzmannhaus, Watzmann-Mittelspitze). Las instalaciones existentes no se tocan. Si borras los ejemplos y los quieres luego, **Ajustes → Datos → Cargar datos de ejemplo** los reimporta cuando lo desees.

---

## 1.33.4 — 5 may. 2026 — Limpieza de permisos para la ficha en Play Store

- **Lista de permisos más limpia en Play Store.** Se eliminó una declaración heredada de "almacenamiento USB" que nunca se usó — la app guarda los mosaicos en su almacenamiento interno propio, no en USB / almacenamiento compartido. La página de permisos muestra ahora cuatro entradas menos; en tu teléfono no cambia nada.

---

## 1.33.3 — 4 de mayo de 2026 — Altitud correcta sobre el nivel del mar + pantalla de track más limpia + corrección de seguirme

- **La altitud de la barra de stats lee ahora metros reales sobre el nivel del mar.** En la mayoría de teléfonos Android el chip GPS informa la altitud relativa al *elipsoide* — un modelo matemático suave de la Tierra — no al océano real. En el Golfo Pérsico eso son unos 30 m de desfase; de pie en la corniche de Abu Dabi mostraba unos **−27 m** en lugar de cero. La app usa ahora el valor de nivel medio del mar del dispositivo cuando está disponible (Android 14+ en hardware compatible) y recurre a una corrección de geoide global incluida (rejilla EGM96 de 1°, ~128 KB) en los dispositivos que no lo proporcionan (el Vivo X300 Pro es uno). El nivel del mar lee ahora **de +0 m a un par de metros**, en cualquier parte del mundo, sea cual sea el teléfono. La misma corrección se aplica al texto de compartir-ubicación y a la altitud que se pasa a la previsión del tiempo.
- **La velocidad de la barra de stats se fija a 0 km/h cuando estás parado.** Antes, la sacudida del GPS en parado disparaba la lectura de velocidad a 1–3 km/h pese a no haber movimiento real. La pantalla muestra ahora cero hasta que superas el suelo de precisión de velocidad que informa tu teléfono — la grabación en sí sigue usando el valor crudo, así que el movimiento lento legítimo no se enmascara.
- **Grabaciones más limpias en cañones y zonas urbanizadas.** Tres nuevas defensas contra los picos de altitud por multitrayecto (donde un muro refleja la señal GPS): el filtro de grabación ahora descarta las lecturas de altitud cuya precisión vertical es mala, rechaza los saltos bruscos de más de 50 m respecto al último fix bueno sin importar el tiempo transcurrido, y mantiene afilado su control de tasa incluso tras largos tramos sin altitud. Una traza del cañón Wadi Hijr del 3 de mayo tenía ocho saltos de altitud de un segundo de 70–300 m que se colaron por el filtro anterior; las nuevas capas los atrapan.
- **Pantalla de detalle del track — disposición más simple.** El icono de lápiz de la barra de herramientas ya no está — **toca el nombre del track** en la barra para renombrarlo. Una sola fila de tres botones se sitúa bajo el gráfico de altitud: **Recortar · Optimizar track (X pts) · Eliminar track**. La pila de botones de ancho completo anterior y el menú de desbordamiento de 3 puntos se han eliminado; todo cabe en una pantalla de móvil sin desplazamiento.
- **Optimizar es ahora vista previa antes de guardar.** Confirmar la optimización en el diálogo antes la aplicaba al instante sin deshacer. Ahora el track simplificado se renderiza en el gráfico + tarjeta de stats bajo un pequeño diálogo que muestra `3214 → 500 puntos · 12,40 → 12,30 km`. **Guardar** lo escribe; **Descartar** (o el botón atrás del hardware) lo descarta. No hay cambios en la base de datos hasta que Guardas.
- **FAB Seguirme: toca una vez para volver a bloquear.** Un fallo donde panear el mapa (que atenuaba el FAB de seguirme) y luego tocarlo requería **dos toques** para que el FAB se pusiera azul sólido — la animación de recentrado se interpretaba como un paneo de usuario continuado. Ahora un solo toque vuelve a bloquear y recentra, como debió ser siempre.

---

## 1.33.2 — 30 abr. 2026 — Aspecto del mapa renovado + barrido de correcciones

- **Pantalla de mapa más limpia y moderna.** La barra superior, los FAB de Capas / Medir / Seguirme, el botón Grabar, la barra de stats y el chip del tiempo son ahora translúcidos — el mapa se transparenta tenuemente detrás de ellos para que la pantalla se sienta menos encajonada. El propio mapa se extiende ahora de borde a borde, desde lo más alto hasta lo más bajo de la pantalla.
- **Menús modernizados.** El menú de hamburguesa (arriba a la derecha) y el selector de fuente de mosaicos de Capas aparecen ahora como tarjetas emergentes redondeadas con iconos a la izquierda, en vez de los rectángulos planos de antes. Las zonas táctiles son más grandes; la fuente de mosaicos activa se marca con un nombre en negrita + marca de verificación.
- **Árabe / persa / urdu — dígitos occidentales en todas partes.** Distancias, altitudes, coordenadas, horas en la notificación de compartir-ubicación y el reloj horario de la hoja del tiempo ya no se renderizan como numerales árabe-orientales (`٣٫٤ كم`) — se leen como `3.4 km` sin importar el idioma del teléfono. Esto era una inconsistencia de larga data en las etiquetas de los gráficos y en algunos constructores de notificaciones.
- **Gráficos en árabe: los gestos de rastreo en la dirección correcta.** Los gráficos de altitud de detalle del track y de planificación tenían el rastreo invertido en árabe — tocar el borde visual izquierdo saltaba al final de la ruta. Ahora el rastreo sigue tu dedo correctamente sin importar el idioma.
- **El botón atrás del hardware desde la vista previa Guardar / Descartar de altitud descarta ahora la vista previa** en lugar de navegar fuera en silencio y perder la consulta sin guardar. La barra de vista previa refleja el patrón «¿estás seguro?» del modo planificación.
- **Restaurar una copia de seguridad ahora preserva la hora de inicio, la hora de fin y la etiqueta de actividad de tus tracks grabados.** Los tracks GPX importados ya estaban cubiertos (no llevan estos campos de todos modos); los tracks grabados perdían los tres en silencio en cada restauración. Si has restaurado una copia desde que llegó la función de etiquetado de actividad y notaste que tus marchas / salidas perdieron sus insignias — ese es el motivo. Haz una copia fresca ahora y la próxima restauración las conservará.
- **Traducciones completadas (de / fr / es / pl / ar).** Once cadenas en torno al flujo de consulta de altitud («Consultando altitud…», «Guardar», «Descartar», «No se pudo consultar la altitud», etc.) y el tooltip de rastreo del gráfico («Toca el gráfico para explorar») están ahora traducidas. Antes eran solo en inglés en teléfonos no anglófonos.
- **Ajustes varios.** Varios mensajes de estado «Track guardado» / «Adquiriendo fix GPS» aparecen ahora como toasts rápidos (~2 s, no bloquean el mapa) en lugar de snackbars inferiores (~4 s, bloqueaban los toques). La ruta de arranque del servicio de grabación / seguirme se endureció contra una rara condición de carrera que podía registrar un aviso de «el servicio no arrancó». La consulta de altitud de la planificación de rutas es más rápida en rutas largas (las conexiones de red por lote se reutilizan ahora).

---

## 1.33.1 — 28 abr. 2026 — Pulido de orden + consultar altitud para tracks antiguos + ESRI por defecto

- **Vuelve a tocar una fila de orden para invertir la dirección.** En las listas Rutas y Puntos, tocar la fila de orden **activa** invierte ahora el orden — `Más recientes primero` cambia a `Más antiguos primero`, `Nombre (A→Z)` a `Nombre (Z→A)`, `Más cercanos primero` a `Más lejanos primero`, `Más puntos` a `Menos puntos`. La fila activa muestra el nombre direccional más un `✓`. Tocar una fila distinta elige la dirección natural de esa clave; volver a tocarla la invierte. Sin interruptor asc / desc aparte — mantiene el menú compacto.
- **Ordena y filtra tus tracks por actividad.** La lista Rutas gana una quinta clave de orden: **Actividad** (alfabética — Ciclismo, Senderismo, Todoterreno, Parapente, Correr, Caminata). Los tracks sin actividad asignada se hunden al fondo en A→Z (y flotan arriba en Z→A) para que veas qué falta por etiquetar. El menú de filtro gana también una sección **Actividad** — seis chips para los tipos de actividad más un chip «Sin actividad» — para aislar «muéstrame solo mis tracks de senderismo» o «muéstrame todo lo que aún no he etiquetado».
- **Toca para consultar la altitud de los tracks que no la tienen.** Los archivos GPX de algunas fuentes no llevan altitud por punto, así que el detalle del track mostraba un gráfico de altitud vacío. Ahora: si un track no tiene altitud, el área del gráfico se sustituye por una tarjeta **Toca para consultar desde el terreno**. Un toque extrae la altitud de un modelo de terreno mundial (precisión de unos 30 m, sin cuenta) para cada punto de tu track. Durante la carga verás un contador de progreso `X / Y` y un botón Cancelar. Al terminar, el gráfico se renderiza con las nuevas altitudes — pero **aún no se guardan**: aparece una barra Guardar / Descartar para que previsualices el resultado y te eches atrás si se ve mal.
- **ESRI Topo es el nuevo mapa base por defecto en instalaciones nuevas.** Las instalaciones existentes no se tocan — lo que hubieras elegido en **Ajustes → Estilo de mapa** se mantiene. Para quien instala la app por primera vez, el mapa abre en ESRI Topo en lugar de OpenTopoMap. Los mosaicos de ESRI renderizan etiquetas más limpias a niveles de zoom de senderismo, sobre todo en pantallas de tipo iPhone. El orden del selector en Ajustes no cambia; volver atrás es un solo toque.
- **Planificación: más fácil agarrar un vértice, soltado en la papelera más fiable.** Las zonas táctiles de los vértices de planificación y los tiradores de los puntos intermedios obtuvieron una zona de colisión circular real de ~28 dp (antes era el rectángulo del icono pelado — fallar con el dedo era común en rutas densas). La zona-papelera obtuvo un pequeño margen de holgura en cada borde, y la comprobación de «¿soltaste sobre la papelera?» usa ahora la posición real del marcador al final del arrastre, no una bandera de «está sobrevolando» a veces obsoleta. Efecto neto: la papelera ya no «deja de funcionar» tras unos pocos vértices, y agarrar el vértice correcto en un plan largo es fiable.

---

## 1.33.0 — 27 abr. 2026 — Planifica un track en el mapa

- **Novedad: planificación de tracks.** Esboza una ruta tocando puntos en el mapa y guárdala como un Track normal — útil para explorar la marcha de mañana, marcar un enlace que viste en un mapa de papel o simplemente dibujar el bucle que recuerdas. Abre **menú → Rutas** y toca el nuevo botón **+** (sobre el botón de carpeta de importación). El mapa abre en modo planificación: toca para añadir paradas numeradas de color verde azulado, mantén pulsada una parada para arrastrarla, mantén pulsado el pequeño punto entre dos paradas para insertar una nueva. Arrastra cualquier parada hasta el **icono de la papelera** (arriba a la derecha, bajo la brújula) para eliminarla — la línea se reconecta a través de los vecinos restantes. La papelera se enciende en rojo cuando una parada está sobrevolándola.
- **Perfil de altitud para rutas planificadas.** Mientras planificas, toca el **icono de gráfico** a la derecha para ver un gráfico de altitud real de tu borrador. La app muestrea tu ruta cada ~100 m y pide a Open-Meteo la altitud del terreno en cada muestra, luego muestra el ascenso y el descenso totales. Las rutas largas se muestrean más grueso para que la consulta sea rápida; verás un contador de progreso `X / Y` y un botón Cancelar mientras carga.
- **Guarda el plan.** Toca **✓ Guardar** en la barra superior, nombra tu ruta, confirma — el track planificado aterriza en tu lista Rutas, exportable como GPX, comparable con una futura grabación. Si habías cargado el perfil de altitud, el track guardado lleva los puntos muestreados densos; si no, solo las paradas que tocaste (con altitud por rellenar más tarde si quieres).

---

## 1.32.4 — 27 abr. 2026 — Corrección del diálogo de recorte para el árabe

- **El diálogo de recorte de track ya funciona en árabe.** Antes, abrir el diálogo de recorte de un track en árabe no mostraba ningún track visible hasta que arrastrabas los deslizadores hacia dentro. Corregido: el marco de coordenadas del gráfico y los manejadores de arrastre de los deslizadores se mantienen ahora coherentes sin importar el idioma.

---

## 1.32.3 — 27 abr. 2026 — Altitud para waypoints con un toque

- **Consulta la altitud desde el terreno.** Al editar un waypoint, el campo Elev (m) tiene ahora un pequeño icono de descarga a la derecha. Tócalo y la app rellena la altitud desde un modelo de terreno mundial (precisión de unos 30 m) usando la latitud / longitud que has escrito. Útil cuando escribes un waypoint a mano, o tras arrastrar uno a un nuevo sitio. El icono está atenuado hasta que tengas coordenadas válidas introducidas; muestra un breve indicador mientras consulta, y un rápido mensaje «No se pudo consultar la altitud» si estás sin conexión. Lo que ya hubieras escrito en el campo se sustituye — lo pediste explícitamente.

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
