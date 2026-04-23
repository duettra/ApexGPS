# Ajustes

**Menú → Ajustes** está organizado en cuatro subpantallas: Apariencia, Almacenamiento, Datos, Claves API. Cada una tiene un botón ⓘ junto a los títulos de sección que explica la función.

## Apariencia

### Tema
- **Sistema** (por defecto) — sigue el claro/oscuro del teléfono.
- **Claro** — siempre claro.
- **Oscuro** — siempre oscuro.

### Mapa predeterminado
Estilo usado al iniciar. Seis opciones; ver [La pantalla del mapa → Capas](map.md) para detalles. Puedes cambiar de estilo en cualquier momento con el botón de capas.

### Grosor de línea
Slider, 4–24 dp. Líneas gruesas se ven mejor cuando hay muchas rutas solapadas; finas lucen más limpias en zoom alto. Por defecto ~6 dp.

### Tamaño de puntos
Pequeño / Normal / Grande / XL. Multiplicador sobre el tamaño adaptativo al zoom — los marcadores ya encogen a zoom bajo y crecen a zoom alto para ser legibles; esto desplaza toda la escala. Por defecto Normal (1,0×).

### Bloquear rotación al iniciar
- **Desactivado** (por defecto) — los gestos de dos dedos funcionan desde el inicio.
- **Activado** — rotación bloqueada al abrir; pulsa largo la brújula para desbloquear. Útil si a menudo rotas el mapa sin querer.

### Botón de pánico
- **Desactivado** (por defecto) — sin botón de pánico.
- **Activado** — pastilla roja ⚠ arriba a la izquierda (reflejo de la brújula a la derecha). Toque → abre el panel de compartir, activando GPS si hace falta. Ver [Compartir → Botón de pánico](share-and-navigate.md#botón-de-pánico-opcional).

## Almacenamiento

### Uso de caché
Tamaño total del caché de navegación + desglose por fuente.

### Limpiar caché
- **Limpiar todo** — borra mosaicos cacheados en todos los estilos. NO elimina regiones guardadas.
- **Limpiar [fuente]** — por estilo. Útil si uno ocupa mucho (imagen satelital pesa más que mapa de curvas).

La caché de navegación se reconstruye al mirar zonas con señal. Limpiar no afecta datos explícitamente guardados desde el hub Mapas.

## Datos

### Copia de seguridad
Crea un ZIP con rutas, puntos, regiones guardadas y ajustes. Los interruptores permiten excluir categorías (las regiones son lo más grande — a menudo fuera para copias rápidas «solo mis rutas»). Ver [Copia y restauración](backup.md).

### Restaurar
Abre un `apexgps-backup-*.zip`. Elige **Combinar** (añadir) o **Reemplazar** (sobreescribir). Ver [Copia → Combinar vs Reemplazar](backup.md#combinar-vs-reemplazar).

### Optimizar todas las rutas
Ejecuta Douglas-Peucker en todas las rutas. Reduce puntos sin cambiar visualmente la forma. Útil si has importado muchos GPX densos y el mapa va lento en un teléfono viejo. Muestra el total afectado.

Las rutas individuales también se pueden optimizar desde la pantalla detalle.

### Cargar datos de ejemplo
Importa 3 puntos (Cumbre / Mirador / Inicio de sendero) y 3 rutas de longitudes y perfiles variados (5 km / 12 km / 25 km, con +260 m a +3030 m). Útil para explorar la app sin tener GPX propios. Tras el import son rutas/puntos normales — bórralos cuando quieras.

## Claves API

### Thunderforest
Requerida para el estilo **Outdoors (Thunderforest)**. Plan «Hobby» gratuito: 150 000 solicitudes al mes, sin tarjeta. Regístrate en [thunderforest.com](https://www.thunderforest.com/), copia la clave, pégala aquí → **Guardar**.

Sin clave, Outdoors muestra un placeholder; los otros cinco estilos funcionan sin clave.

## Acerca de

**Ajustes → Acerca de** muestra versión, atribuciones y e-mail de contacto — además de la **Guía**: entradas tocables para cada capítulo de esta documentación, incluida en la app para consultar sin conexión. Toca un capítulo → se abre un lector y renderiza el capítulo en la app. Los enlaces entre capítulos se respetan; la flecha de retorno vuelve a la lista. Un enlace **«Ver en línea»** abajo lleva a la misma doc en [apexgps.duttra.de/docs](https://apexgps.duttra.de/docs/) en el navegador. Para soporte: [sandwalker.one@proton.me](mailto:sandwalker.one@proton.me).

---

**Relacionado:** [FAQ →](faq.md) · [Copia y restauración →](backup.md)
