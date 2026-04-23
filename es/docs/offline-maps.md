# Mapas sin conexión

ApexGPS funciona sin señal si los mosaicos del área ya están en el teléfono. Dos formas: caché automática y descarga manual previa.

## Caché automática

Todo lo que hayas mirado con señal se guarda en la caché de mosaicos del teléfono. Volver al mismo sitio sin conexión → cargan al instante.

La caché es **por fuente** — OpenTopoMap y Satélite son almacenes separados. Mirar una zona en OpenTopoMap no ayuda si pasas a Satélite sin conexión.

El tamaño se muestra en **Ajustes → Almacenamiento** con desglose por fuente.

## Descarga manual previa (recomendado para salidas)

Antes de ir a un sitio sin señal, descarga la región de forma deliberada:

### Elegir el área

1. Mueve/zoom el mapa para cuadrar la zona.
2. **Menú → Mapas** → toca **Descargar nueva zona**.
3. Un pequeño mapa de vista previa muestra el área. Ajusta si hace falta.

### Rango de zoom

Un **slider** define los niveles a guardar. Más zoom = más detalle pero exponencialmente más mosaicos.

- **Fin de semana**: 10–16 suele bastar.
- **Expedición / semana**: 10–17 o 10–18 para máximo detalle.
- Zoom 19+ raramente vale la pena al aire libre — muchos mosaicos, poco extra.

La UI muestra **mosaicos estimados** y **tamaño MB** al mover el slider. Compara con tu espacio libre.

### Descargar

Toca **Descargar**. Aparece una notificación en primer plano; puedes salir de la app, bloquear el teléfono — la descarga sigue. Progreso en la notificación y en el hub Mapas.

Cancelar en curso: hub Mapas → la tarjeta tiene botón **Cancelar**. (Volver atrás NO cancela — intencional, para que puedas explorar rutas mientras baja.)

### Solo la fuente activa

La descarga usa la fuente activa al iniciar. Para otro estilo, cambia primero la fuente (FAB capas) y luego inicia.

## Regiones guardadas (menú → Mapas → Mapas guardados)

Cada descarga completa aparece aquí. Toca una región para abrir su detalle:

- **Nombre** — editable. Por defecto basado en país/región geocodificado del bounding box.
- **Fuente**, **rango de zoom**, **mosaicos**, **tamaño en disco**.
- **Mostrar en el mapa** — cierra el detalle y ajusta el zoom a la región.
- **Eliminar** — libera almacenamiento. Con confirmación.

Eliminar una región guardada quita su bundle pero NO afecta la caché general. El área puede seguir en caché de navegación previa.

## Gestión de caché (menú → Ajustes → Almacenamiento)

- **Tamaño total** de caché sumando fuentes.
- **Desglose por fuente** — MB que ocupa cada estilo.
- **Limpiar toda** — borra mosaicos de navegación de cada estilo. NO elimina regiones guardadas (archivos aparte).
- **Limpiar [fuente]** — solo ese estilo.

Las regiones sin conexión se gestionan en el hub Mapas, no aquí.

## Qué consume red en salida

Aun con todo en caché, algunas cosas pueden intentar red:

- **Cambiar de estilo** si el nuevo no está cacheado para la zona — los mosaicos quedan vacíos.
- **Thunderforest (Outdoors)** — mosaicos vía HTTPS con tu clave.
- Nada más. Rutas, puntos y navegación son totalmente locales.

Sin señal, aparece el **Sin conexión** arriba. Es la señal del dispositivo, no una elección de la app.

## Consejos

- **Descarga siempre antes de una salida.** No confíes en la caché automática — solo cubre lo ya mirado.
- **Dos estilos** puede ayudar: OpenTopoMap para curvas + senderos, Satélite para realidad visual. Descarga ambos en zonas críticas.
- **Más zoom = más espacio, rendimiento decreciente.** Pasado el 17 el detalle extra rara vez ayuda; son sobre todo formas de edificios y etiquetas.
- **Revisa espacio libre antes de descargas grandes.** Una región amplia en zoom 18 puede superar 500 MB.

---

**Relacionado:** [La pantalla del mapa →](map.md) · [Ajustes →](settings.md) · [Copia y restauración →](backup.md)
