# Creando un Chart

Para crear un chart, accede a la herramienta «Chart Editor». En el juego, puedes encontrarla en el menú «Debug» del menú principal (asignada a `~` por defecto). También puedes acceder a ella añadiendo una tecla de acceso rápido para «Debug Chart» en el menú de opciones (no asignada por defecto) y, a continuación, pulsando la tecla asignada mientras reproduces una canción.

Desde aquí, puedes crear un nuevo chart partir de archivos de audio, importar una de una versión anterior del juego o crear un chart a partir de datos de partituras existentes en el juego.

El uso detallado del Chart Editor merece su propia guía, pero lo básico debería ser bastante intuitivo. Por ahora, supongamos que has creado un chart de tu canción favorita y quieres convertirla en un mod que la gente pueda jugar.

## Desmontando tu archivo FNFC

Cuando guardas tu chart, el juego la empaqueta en un archivo `.fnfc`, lo que facilita compartirla con otros creadores de charts (charters) y colaborar. Incluye el audio de la canción, junto con los datos de las notas y algunos archivos de metadatos que lo acompañan.

Para añadir la canción a nuestro mod, necesitamos extraer esa información. Esto es bastante fácil, ¡porque un archivo FNFC es en realidad, en secreto, un archivo ZIP! Cambia el nombre de tu `mychart.fnfc` a `mychart.zip`, sustituyendo la extensión del archivo para que tu sistema operativo lo reconozca como un ZIP, y extráelo para revelar su contenido, que será algo así:

```
-manifest.json
-mychart-metadata.json
-mychart-chart.json
-Inst.ogg
-Voices-bf.ogg
-Voices-pico.ogg
```
