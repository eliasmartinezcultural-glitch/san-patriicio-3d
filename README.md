# San Patricio del Chañar 3D

Proyecto abierto para construir, por etapas, un recorrido 3D del casco urbano de San Patricio del Chañar, Neuquén. La prioridad es combinar datos geográficos verificables, una experiencia caminable y rendimiento razonable en una netbook antigua.

## Estado de esta versión

**Prototipo interactivo inicial. No es todavía una réplica exacta del pueblo.**

- Escenario 3D con Three.js.
- Consulta cartografía de OpenStreetMap mediante Overpass API.
- Dibuja huellas de edificios y trazas de calles que estén mapeadas.
- Busca lugares etiquetados con nombre (servicios, turismo, comercios, recreación e historia) y los representa con marcadores y rótulos.
- Permite vista general, modo caminar con WASD/flechas y mouse, y mostrar/ocultar capas.
- La entrada al modo caminar ahora comienza en el punto de referencia central, no en la posición de la cámara aérea.
- Interfaz en español y adaptación básica a pantallas pequeñas.

## Cómo probarlo

1. Abrí el archivo `index.html` en un navegador moderno **con internet**.
2. Permití la carga de contenido externo si el navegador lo pregunta.
3. Esperá a que termine la consulta cartográfica.
4. Usá **Vista del pueblo** para observar el escenario y **Entrar a caminar** para recorrerlo.
5. Si los datos no aparecen, usá **Cargar datos del mapa** más tarde: los servidores públicos pueden estar ocupados.

Para publicarlo, entrá en **Settings → Pages**, elegí **Deploy from a branch**, seleccioná `main` y `/(root)`, y guardá. La URL definitiva debe ser la que confirme GitHub Pages en la configuración del repositorio.

## Límites conocidos

- El centro usado como referencia es aproximado; no representa un levantamiento topográfico.
- La cobertura depende de OpenStreetMap: un lugar que no aparece puede no estar mapeado o no tener nombre.
- Las alturas de edificios sin atributo de altura son estimaciones visuales.
- El terreno es plano en esta versión; no debe confundirse con el relieve real.
- Las calles son trazas cartográficas, no una simulación completa de calzadas, veredas, circulación ni colisiones.
- Las consultas públicas de Overpass pueden fallar o demorarse. No se deben realizar consultas repetitivas innecesarias.
- La versión actual requiere internet para cargar Three.js y los datos; todavía no es una versión sin conexión.
- No se descargan ni se reutilizan imágenes de Google Street View.

## Hoja de ruta

### Fase 1 — Base navegable
- [x] Escena 3D y controles iniciales.
- [x] Edificios y calles desde datos abiertos.
- [x] Marcadores para lugares nombrados disponibles en los datos.
- [ ] Probar en Chrome real y en la netbook; corregir errores observados.
- [ ] Medir el rendimiento con distintas cantidades de edificios.

### Fase 2 — Precisión local
- [ ] Auditar cobertura de calles, edificios y puntos de interés.
- [ ] Crear una lista de hitos locales confirmados, con fuente y coordenadas.
- [ ] Diferenciar datos confirmados, aproximados y pendientes de verificación.
- [ ] Incorporar nombres de calles solo cuando estén respaldados por cartografía o fuente local fiable.

### Fase 3 — Geografía y arquitectura
- [ ] Evaluar un modelo de elevación público compatible con la zona.
- [ ] Mejorar formas de techos y materiales sin inventar detalles de fachadas.
- [ ] Añadir vegetación, mobiliario y elementos urbanos solo cuando haya referencias suficientes.
- [ ] Mantener una opción gráfica sencilla para equipos lentos.

### Fase 4 — Uso sin internet
- [ ] Preparar una copia local de los datos necesarios y recursos autorizados.
- [ ] Evitar depender de consultas a Overpass en cada apertura.
- [ ] Verificar licencias, atribuciones, tamaño total y funcionamiento desconectado.

## Fuentes y atribución

- OpenStreetMap: https://www.openstreetmap.org/
- Overpass API: https://overpass-api.de/
- Documentación Overpass y uso responsable: https://dev.overpass-api.de/overpass-doc/en/preface/commons.html
- Three.js: https://threejs.org/
- Instituto Geográfico Nacional de Argentina, información sobre modelos digitales de elevación: https://www.ign.gob.ar/NuestrasActividades/Geodesia/ModeloDigitalElevaciones/faq

Los datos de OpenStreetMap se distribuyen bajo la licencia ODbL. Al publicar o distribuir datos derivados, hay que respetar sus requisitos de atribución y compartir igual cuando corresponda. Las condiciones de cada recurso externo deben revisarse antes de incorporarlo.

## Criterio del proyecto

No presentar una aproximación como si fuera una medición real. Cada mejora debe indicar qué fuente usa, qué tan precisa es y qué falta comprobar.
