# Fuentes, precisión y método

## Propósito

El proyecto intenta construir un recorrido 3D del casco urbano de San Patricio del Chañar usando datos abiertos y fuentes que puedan citarse. No es una medición catastral ni una réplica fotográfica. Se distingue entre ubicación publicada, geometría aproximada y detalle pendiente de verificación.

## Hitos iniciales incluidos en la escena

| Hito | Coordenadas (latitud, longitud) | Base documental | Estado |
|---|---|---|---|
| Municipalidad de San Patricio del Chañar | -38.62619, -68.29793 | Fuente cartográfica secundaria basada en OpenStreetMap | Referencia inicial; contrastar en campo |
| Hospital de Área Dra. Alicia Cruz | -38.62957, -68.29623 | Fuente cartográfica secundaria basada en OpenStreetMap | Referencia inicial; contrastar en campo |
| Plaza de los Derechos de las Infancias | -38.63272, -68.29632 | Coordenada cartográfica; denominación contrastada con Ordenanza 1203/20 | Referencia inicial; comprobar cartelería y geometría actual |

Fuentes:
- Municipalidad: https://mapcarta.com/es/W218470639
- Hospital: https://mapcarta.com/es/W922791579
- Plaza: https://mapcarta.com/W120609368
- Ordenanza 1203/20: https://boletinoficial.neuquen.gov.ar/BoletinDetalle?Id=23

Estas coordenadas son una base inicial, no puntos topográficos certificados. Las páginas cartográficas citadas se basan en OpenStreetMap y otros datos; cuando sea posible, se debe guardar el objeto original de OSM y la fecha de consulta para cada actualización.

## Cartografía dinámica

La aplicación consulta Overpass API y dibuja:
- huellas de edificios etiquetadas como building;
- trazas viales etiquetadas como highway;
- lugares etiquetados con categorías como amenity, tourism, shop, leisure o historic.

La presencia o ausencia de una forma depende de la cobertura de OpenStreetMap. La altura de edificios sin atributo height es estimada, por lo que no se debe interpretar como medida real.

## Relieve

El IGN publica el modelo digital de elevaciones MDE-Ar v2.1, de resolución aproximada de 30 metros y precisión vertical informada de aproximadamente 2 metros. Puede servir para el relieve regional, pero su resolución no describe veredas, cordones ni cambios pequeños dentro de una parcela.

Referencias:
- IGN, MDE-Ar v2.1: https://www.ign.gob.ar/content/nuevo-modelo-digital-de-elevaciones-para-la-rep%25C3%25BAblica-argentina
- IGN, preguntas frecuentes de modelos digitales de elevación: https://www.ign.gob.ar/NuestrasActividades/Geodesia/ModeloDigitalElevaciones/faq

El relieve no está incorporado todavía al motor 3D. La siguiente implementación debería utilizar un archivo de elevaciones procesado para el área de interés, con unidades y sistema de coordenadas documentados.

## Protocolo de verificación local

Para cada nuevo lugar:
1. Guardar nombre tal como aparece en una fuente local u oficial.
2. Registrar latitud y longitud y el enlace a la fuente.
3. Separar el punto aproximado del polígono del edificio o del espacio público.
4. Anotar la fecha de revisión y si fue verificado visualmente en terreno.
5. Si no hay fuente suficiente, etiquetarlo como pendiente; no inventar fachada, altura o uso.
6. Revisar las condiciones de licencia y atribución antes de redistribuir los datos.

## Atribución

Los datos cartográficos de OpenStreetMap se distribuyen bajo la licencia ODbL. La aplicación muestra atribución visible. Antes de distribuir extractos o una base de datos derivada, revisar los requisitos de atribución y compartir igual de la ODbL: https://www.openstreetmap.org/copyright.

## Limitaciones actuales

- No se ha ejecutado una prueba de navegador en el equipo del usuario.
- El terreno es plano.
- La escena necesita conexión a internet para descargar Three.js y consultar Overpass.
- Los marcadores iniciales y sus coordenadas necesitan contraste local.
- Las geometrías de calles no incluyen veredas, señales, mobiliario, circulación ni colisiones.
- Los datos públicos pueden contener omisiones, geometrías simplificadas o etiquetas antiguas.
