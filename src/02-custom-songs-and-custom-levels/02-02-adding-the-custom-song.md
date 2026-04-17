# Añadir la canción personalizada

Al final de [Creando un Chart](02-01-creating-a-chart.md) aprendimos que los archivos `.fnfc` no son más que archivos `.zip`, por lo que basta con cambiarles el nombre y descomprimirlos. Una vez que tengamos estos archivos, solo tenemos que colocarlos en las ubicaciones correctas dentro de nuestra carpeta del mod.

- El archivo `manifest.json` se puede descartar, nuestro mod no lo necesitará.
- Los archivos `metadata.json` y `chart.json` deben ir a la carpeta `data/songs/<songid>`, sustituyendo `<songid>` por el nombre interno de nuestra canción.
- Los archivos OGG deben ir en `songs/<songid>`, sustituyendo de nuevo `<songid>` por el nombre interno de nuestra canción.

El resultado final será algo así.

```
-mods
 |-myMod
   |-data
     |-songs
       |-mychart
         |-mychart-metadata.json
         |-mychart-chart.json
   |-songs
     |-mychart
       |-Inst.ogg
       |-Voices-bf.ogg
       |-Voices-pico.ogg
   |-_polymod_meta.json
```

Cuando se inicia el juego, consulta la lista de canciones disponibles buscando en la carpeta `data/songs` los archivos `<songid>/<songid>-metadata.json`, que luego utiliza para encontrar el archivo de la lista y los archivos de canciones necesarios. ¡Genial! Pero ahora mismo, si inicias el juego, esto no hace nada. Verás que aparece mencionado en los registros sin errores, pero no se puede reproducir en el Modo Historia ni en el Modo Libre, ¿qué pasa?

```
source/funkin/play/song/Song.hx:579: Obteniendo metadatos de la canción para mychart
source/funkin/data/song/SongRegistry.hx:103:   Datos de entrada cargados: Song(mychart)
```

La solución es sencilla: todas las canciones deben formar parte de un nivel del Modo Historia para aparecer en el Modo Libre.
