# FAQ y solución de problemas

## «Mi triángulo azul no aparece»

Tres razones posibles:

1. **GPS apagado.** Toca el botón de centrado en la columna derecha. Pasa de gris a azul. Ver [La pantalla del mapa → Seguirme](map.md#seguirme-centrado).
2. **Permiso de ubicación no concedido.** Ajustes del teléfono → Apps → ApexGPS → Permisos → Ubicación → **Permitir solo al usar la app**, ubicación **Precisa**. Luego reabre ApexGPS.
3. **Aún sin fix GPS.** En interiores, cerca de edificios altos o en cañones, la primera adquisición puede tardar 30 s o más. Sal al exterior si puedes.

## «El mapa vuelve a mí cada pocos segundos»

Ese es el seguimiento bloqueado. Arrastra el mapa una vez — el botón de centrado pasa a azul más claro y el mapa se queda donde lo dejes. El triángulo sigue actualizándose; solo la cámara deja de seguirte. Para recentrar: toca el botón de centrado.

Ver [La pantalla del mapa → Seguirme](map.md#seguirme-centrado).

## «¿Cómo apago el GPS por completo?»

**Pulsación larga** en el botón de centrado. GPS apagado, triángulo fuera, batería ahorrada.

El toque para alternar desde bloqueado también apaga, pero la pulsación larga se salta la animación de recentrado — útil cuando has paneado lejos y no quieres que el mapa salte antes de apagar.

## «Alguien me envió un enlace de ubicación — ¿cómo lo veo?»

Si el enlace es como `https://apexgps.duttra.de/loc?lat=...&lon=...`, tócalo desde tu mensaje. Con ApexGPS instalado abre la app con una diana roja. Sin ApexGPS abre una página web con vista previa + enlace para instalar.

Otros enlaces de mapas (Google Maps, etc.) abren tu app favorita de mapas — no se vinculan a ApexGPS.

Ver [Compartir → Recibir una ubicación compartida](share-and-navigate.md#recibir-una-ubicación-compartida).

## «¿Puedo grabar una nueva ruta mientras camino?»

En esta versión no. La grabación en vivo está planeada para una versión futura. Ahora las rutas vienen de importar GPX (las tuyas de otra app o las de alguien más).

## «¿Cuánto espacio usa la app?»

La app en sí es pequeña (~10 MB). El almacenamiento crece por:

- **Caché de navegación** — mosaicos de zonas miradas. Ver **Ajustes → Almacenamiento**.
- **Regiones offline guardadas** — mosaicos pre-descargados vía hub Mapas. Pueden ser grandes (50–500 MB por región según zooms).
- **Rutas + puntos** — diminutos, normalmente <1 MB incluso con cientos.

Limpiar caché en Ajustes → Almacenamiento → Limpiar. Eliminar regiones en hub Mapas → tocar una → Eliminar.

## «El mapa va lento al hacer zoom / pan»

Cosas que probar:

1. **Demasiadas rutas cargadas.** Lista Rutas → filtro visibilidad → oculta las que no uses hoy. O borrado masivo de imports viejos.
2. **Rutas muy detalladas.** **Ajustes → Datos → Optimizar todas** — los puntos caen ~90 % sin cambio visible.
3. **Zoom bajo con muchos puntos.** Los puntos se agrupan automáticamente a zoom bajo (un solo círculo con contador) — toca para hacer zoom. Si el teléfono aún sufre, el umbral de agrupar es fijo en código; oculta rutas en su lugar.
4. **Teléfono antiguo.** ApexGPS apunta a Android moderno. En dispositivos previos a 2020, hay limitaciones inevitables con 500+ rutas en pantalla.

## «No veo la nueva versión en Play Store»

Eres tester cerrado y te notificaron una actualización. Si no aparece:

1. Play Store → icono perfil (arriba derecha) → **Gestionar apps y dispositivo** → **Actualizaciones disponibles** → refrescar. Si ApexGPS aparece, **Actualizar**.
2. ¿Aún nada? Abre de nuevo el enlace de invitación testeador original. Fuerza detener Play Store, reabre, busca ApexGPS.
3. ¿Aún nada? **Ajustes → Apps → Google Play Store → Almacenamiento → Limpiar caché**. Reabre, busca.
4. El CDN de Google tarda 2–24 h tras «auto-publicado». Si te avisaron hace poco, espera unas horas.

## «¿Puedo usar ApexGPS sin darle permiso de ubicación?»

En gran medida sí. Puedes importar GPX, ver rutas, planear rutas, medir distancias, gestionar puntos y pre-descargar regiones — todo sin ubicación. Lo que pierdes:

- Triángulo en vivo.
- Seguirme / orden «más cercanos».
- La función Compartir ubicación (no hay ubicación que compartir).
- Navegación a destino (no hay «tú» del que trazar la línea).

## «¿La app envía mi ubicación a algún sitio?»

No. ApexGPS no hace solicitudes de red con tu ubicación. La única actividad de red saliente es traer mosaicos, indistinguible de consultar un mapa — los servidores ven una IP + coordenadas de mosaico, nada sobre ti. Ver la [política de privacidad](/privacy.html).

Compartir por el botón Compartir es totalmente a iniciativa del usuario — tú eliges la app (WhatsApp, etc.) y el destinatario.

## «El teléfono Android de mi amigo abre el enlace en el navegador, no en ApexGPS»

El enlace solo abre directo en ApexGPS en dispositivos con la verificación de App Links de Google completada. Una instalación nueva a veces necesita un primer arranque de la app antes de que la verificación se active. Pide a tu amigo:

1. Abrir ApexGPS una vez, dar permiso de ubicación, cerrar.
2. Tocar de nuevo tu enlace compartido.

Ahora debería abrir en la app. Si sigue en el navegador, Android puede ofrecer un selector — puede elegir «Abrir siempre en ApexGPS».

## «¿Puedo restaurar una copia de ApexGPS en iPhone?»

No. ApexGPS es solo Android. El formato de copia es específico de la app.

## «¿Dónde están mis datos físicamente?»

En tu teléfono, en el almacenamiento privado de ApexGPS (`/data/data/com.apexgps.app/` con acceso root — si no, no se alcanza directamente). Rutas + puntos en una base SQLite; ajustes en un archivo de preferencias; mosaicos como imágenes.

Nada se sube a ningún sitio. Para copia, usa [Copia y restauración](backup.md).

---

**¿Aún atascado?** [sandwalker.one@proton.me](mailto:sandwalker.one@proton.me) — informes de fallos bienvenidos.
