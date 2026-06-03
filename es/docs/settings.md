# Ajustes

**Menú → Ajustes** está organizado en cinco subpantallas: Apariencia, Almacenamiento, Datos, Claves API, Avanzado. Cada una tiene un botón ⓘ junto a los títulos de sección que explica la función.

## Apariencia

### Tema
- **Sistema** (por defecto) — sigue el claro/oscuro del teléfono.
- **Claro** — siempre claro.
- **Oscuro** — siempre oscuro.

### Mapa predeterminado
Estilo usado al iniciar. Seis opciones; ver [La pantalla del mapa → Capas](map.md) para detalles. Puedes cambiar de estilo en cualquier momento con el botón de capas.

### Tamaño del texto
Slider, 50 %–150 % en pasos de 10 %. Escala **todo el texto de la app** — menús, listas, la barra de estadísticas, diálogos. Se aplica *encima* del tamaño de fuente del sistema del teléfono en lugar de reemplazarlo, así que nunca anula una opción de accesibilidad definida a nivel de sistema; solo desplaza ApexGPS respecto a ese ajuste. Por defecto 100 %. Útil si una fuente grande del sistema desborda los menús, o si quieres texto más grande específicamente en ApexGPS.

### Tamaño de los controles del mapa
Slider, 50 %–150 % (mismos pasos que Tamaño del texto). Cambia el tamaño de los botones del mapa (la columna de FAB, la brújula y la píldora de grabación). Redúcelo para ganar espacio en un teléfono pequeño donde los controles saturan el mapa; auméntalo para tocar más fácil con guantes. Los botones nunca se reducen por debajo de un objetivo táctil cómodo. Por defecto 100 %.

### Tamaño de puntos
Slider, 50 %–200 %. Multiplicador sobre el tamaño adaptativo al zoom — los marcadores ya encogen a zoom bajo y crecen a zoom alto para ser legibles; esto desplaza toda la escala. Por defecto 100 %. (Antes de 1.38.0 era un selector Pequeño/Normal/Grande/XL; ahora es un slider para un control más fino.)

### Grosor de línea
Slider, 4–24 dp. Líneas gruesas se ven mejor cuando hay muchas rutas solapadas; finas lucen más limpias en zoom alto. Por defecto ~6 dp.

### Bloquear rotación al iniciar
- **Desactivado** (por defecto) — los gestos de dos dedos funcionan desde el inicio.
- **Activado** — rotación bloqueada al abrir; pulsa largo la brújula para desbloquear. Útil si a menudo rotas el mapa sin querer.

## Almacenamiento

### Uso de caché
Tamaño total del caché de navegación + desglose por fuente.

### Tamaño del caché de mosaicos
Elige cuánto espacio en disco asignar a los mosaicos guardados automáticamente: **250 MB**, **500 MB** (predeterminado), **1 GB**, **2 GB**. El nuevo límite se aplica al instante en la siguiente descarga de mosaico — no hace falta reiniciar. Las regiones offline guardadas se almacenan aparte y no cuentan en este límite; cambiar el tamaño del caché nunca borra una región que descargaste a propósito.

### Limpiar caché
- **Limpiar todo** — borra mosaicos cacheados en todos los estilos. NO elimina regiones guardadas.
- **Limpiar [fuente]** — por estilo. Útil si uno ocupa mucho (imagen satelital pesa más que mapa de curvas).

La caché de navegación se reconstruye al mirar zonas con señal. Limpiar no afecta datos explícitamente guardados desde el hub Mapas.

## Datos

### Copia de seguridad
Crea un ZIP con rutas, puntos, regiones guardadas y ajustes. Los interruptores permiten excluir categorías. Las regiones de mapa sin conexión tienen un **selector de tres modos**: **No incluir** (saltarlas) / **Receta** (pequeño — solo las instrucciones para volver a descargar cada región, funciona entre Android e iOS) / **Mosaicos completos** (el comportamiento antiguo — incrusta los paquetes de mosaicos en bruto, grande pero restaurable sin conexión, solo Android). Ver [Copia y restauración](backup.md).

### Restaurar
Abre un `apexgps-backup-*.zip`. Elige **Combinar** (añadir) o **Reemplazar** (sobreescribir). Ver [Copia → Combinar vs Reemplazar](backup.md#combinar-vs-reemplazar).

### Optimizar todas las rutas
Ejecuta Douglas-Peucker en todas las rutas. Reduce puntos sin cambiar visualmente la forma. Útil si has importado muchos GPX densos y el mapa va lento en un teléfono viejo. Muestra el total afectado.

Las rutas individuales también se pueden optimizar desde la pantalla detalle.

### Cargar datos de ejemplo
Una grabación real de la **travesía del Watzmann** (Berchtesgaden, Alemania): Wimbachbrücke → Watzmannhaus → Hocheck → Mittelspitze → Südspitze → Wimbachgrieshütte → Wimbachbrücke, bucle de ~22,6 km / +2250 m / unas 10–12 h de marcha. Tres puntos destacados en coordenadas reales: inicio Wimbachbrücke (628 m), refugio DAV Watzmannhaus (1930 m), Watzmann-Mittelspitze (el *Hauptgipfel*, 2713 m). Se importa automáticamente al abrir la app por primera vez en una instalación nueva; este botón vuelve a importarlos a demanda si los has borrado y los quieres de vuelta. Tras el import son rutas/puntos normales — bórralos cuando quieras.

## Claves API

### Thunderforest
Requerida para el estilo **Outdoors (Thunderforest)**. Plan «Hobby» gratuito: 150 000 solicitudes al mes, sin tarjeta. Regístrate en [thunderforest.com](https://www.thunderforest.com/), copia la clave, pégala aquí → **Guardar**.

**Sin clave, el estilo Outdoors está oculto** del selector de estilo del mapa (y del selector de Descargar región sin conexión) para que no lo elijas por error y veas los mosaicos de OpenTopoMap como fallback. Pega una clave → la entrada reaparece en ambos menús. Los otros cinco estilos funcionan sin clave.

## Avanzado

### Ahorro de batería a alta velocidad
Cuando te mueves a más de **36 km/h** (≈22 mph) — conduciendo, en tren, en bici eléctrica rápida — la app reduce el muestreo GPS a un fix cada **10 segundos** en vez de uno por segundo. Las rutas en carretera se siguen grabando limpiamente; la precisión a nivel de carril disminuye al conducir. Recorta aproximadamente la mitad del consumo de GPS en el tramo de autopista de un viaje sin pérdida visible en la geometría de la ruta. Desactiva si necesitas muestreo completo a velocidad (p. ej., telemetría de rally).

## Acerca de

**Ajustes → Acerca de** muestra versión, atribuciones y e-mail de contacto — además de la **Guía**: entradas tocables para cada capítulo de esta documentación, incluida en la app para consultar sin conexión. Toca un capítulo → se abre un lector y renderiza el capítulo en la app. Los enlaces entre capítulos se respetan; la flecha de retorno vuelve a la lista. Un enlace **«Ver en línea»** abajo lleva a la misma doc en [apexgps.duttra.de/docs](https://apexgps.duttra.de/docs/) en el navegador. Para soporte: [sandwalker.one@proton.me](mailto:sandwalker.one@proton.me).

Debajo de Guía de usuario, una fila **Política de privacidad** abre el mismo lector dentro de la app en el capítulo de privacidad — sin internet, para leer qué datos recoge la app (ninguno más allá de lo que está en tu teléfono) y cómo se usan. El mismo contenido está espejado en [apexgps.duttra.de/privacy.html](https://apexgps.duttra.de/privacy.html) para quien quiera leerlo antes de instalar.

---

**Relacionado:** [FAQ →](faq.md) · [Copia y restauración →](backup.md)
