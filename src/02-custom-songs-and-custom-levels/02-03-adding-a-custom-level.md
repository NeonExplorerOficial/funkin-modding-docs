# Añadir un nivel personalizado

Añade un nuevo archivo, con el nombre interno que prefieras, a tu carpeta de mods, dentro del directorio `data/levels/`, con la extensión `.json`.

*NOTA*: Ten en cuenta que si tu nombre interno coincide con el de una semana del juego base o con el de otro mod, se solaparán entre sí y podrías obtener resultados inesperados.

El resultado final será algo así:

```
-mods
 |-myMod
   |-data
     |-levels
       |-myweek.json
     |-songs
       |-mychart
         |-mychart-metadata.json
         |-mychart-chart.json
   |-songs
     |-mychart
       |-Inst.ogg
       |-Voices-bf.ogg
       |-Voices-pico.ogg
   |-images
     |-storymenu
       |-titles
         |-myweek.png
   |-_polymod_meta.json
```

El archivo JSON de tu semana personalizada tendrá un aspecto similar al siguiente:

```json
{
  "version": "1.0.0",
  "name": "MI SEMANA PERSONALIZADA",
  "titleAsset": "storymenu/titles/myweek",
  "background": "#F9CF51",
  "songs": ["michart"],
  "visible": true,
  "props": [
    {
      "assetPath": "storymenu/props/dad",
      "scale": 1.0,
      "offsets": [100, 60],
      "animations": [
        {
          "name": "idle",
          "prefix": "idle0",
          "frameRate": 24
        }
      ]
    },
    {
      "assetPath": "storymenu/props/bf",
      "scale": 1.0,
      "offsets": [150, 80],
      "animations": [
        {
          "name": "idle",
          "prefix": "idle0",
          "frameRate": 24
        },
        {
          "name": "confirm",
          "prefix": "confirm0",
          "frameRate": 24
        }
      ]
    }
  ]
}
```

¡Hay mucha información aquí! Analicémosla:

- `version`: El número de versión del formato del archivo de datos del nivel. Déjalo en `1.0.0`.
- `name`: El nombre legible del nivel, tal y como se muestra en la parte superior derecha del menú de la historia.
- `titleAsset`: El recurso que se utilizará para el nombre del nivel en la lista de niveles, relativo a la carpeta `images` de tu carpeta de mods.
- `background`: El fondo que se utilizará para el nivel. `#F9CF51` es el amarillo clásico, pero este campo admite tanto un código de color como la ruta de un archivo de imagen (relativa a la carpeta `images` dentro de tu carpeta de mods).
- `songs`: Una lista de ID de canciones que se incluirán en la semana.
- `visible`: Indica si este nivel de la historia es visible en el menú de la historia.
- `props`: Datos de los elementos que se mostrarán en el menú de la historia cuando se seleccione el nivel. Por ejemplo, la Semana 1 (Week 1) mostrará «Daddy Dearest», «Boyfriend» y «Girlfriend».

Cuando el juego se inicia, consulta la lista de niveles disponibles buscando archivos JSON en la carpeta `data/levels`, que luego utiliza para rellenar el menú de la historia y, a continuación, el menú de juego libre (en las vistas no alfabéticas, las canciones del juego libre aparecen ordenadas según el nivel en el que están incluidas).

Si quieres que tu canción personalizada solo aparezca en Juego libre, solo tienes que crear una semana personalizada y establecer la propiedad «visible» en false, ¡y las canciones aparecerán en Freeplay!
