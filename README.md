# San Patricio del Chañar 3D

Primer prototipo de recorrido virtual 3D del casco urbano de San Patricio del Chañar, Neuquén.

## Qué incluye
- Escenario 3D liviano basado en Three.js.
- Consulta de calles y huellas de edificios de OpenStreetMap mediante Overpass API.
- Modo de recorrido con teclado (WASD o flechas) y mouse.
- Vista general, reinicio al centro y controles para mostrar/ocultar edificios y calles.
- Interfaz en español y adaptación a pantallas pequeñas.

## Probarlo
Abrí `index.html` con un navegador moderno y conexión a internet. La biblioteca Three.js y la cartografía se cargan desde servicios externos.

## Publicarlo con GitHub Pages
1. En GitHub, abrí **Settings** del repositorio.
2. Entrá en **Pages**.
3. En **Build and deployment**, elegí **Deploy from a branch**.
4. Seleccioná la rama `main` y la carpeta `/(root)`; guardá.
5. Esperá la publicación y abrí la URL que indique GitHub Pages.

## Precisión y límites actuales
- Es una primera base interactiva, no una reconstrucción fotogramétrica ni una réplica visual exacta.
- Las geometrías dependen de la cobertura de OpenStreetMap en la zona.
- Cuando no hay altura registrada, los edificios reciben alturas aproximadas.
- El terreno se representa plano por ahora.
- La consulta a Overpass puede fallar temporalmente por límites del servicio o por la conexión.
- No descarga ni reutiliza imágenes de Google Street View.

## Próximas mejoras
1. Verificar cobertura real y corregir edificios/calles con datos abiertos.
2. Incorporar hitos locales verificados y nombres de calles.
3. Mejorar elevación y relieve con una fuente de terreno compatible.
4. Añadir modo de navegación y controles de rendimiento para netbooks antiguas.
5. Documentar fuentes y licencias de cada capa.

## Fuentes
- OpenStreetMap: https://www.openstreetmap.org/
- Overpass API: https://overpass-api.de/
- Three.js: https://threejs.org/

Los datos de OpenStreetMap se publican bajo la licencia ODbL; consultá las condiciones de atribución correspondientes al distribuir una versión pública.
