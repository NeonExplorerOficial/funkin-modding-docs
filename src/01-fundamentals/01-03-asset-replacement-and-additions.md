# Sustitución y adición de recursos

## Sustitución de recursos

La función principal que te permite Polymod es sustituir recursos. Para ello, basta con añadir esos archivos a la carpeta de mods, en la misma ubicación en la que irían.

Por ejemplo, puedes sustituir los sprites de Girlfriend colocando tus nuevos sprites en la misma ubicación que tienen en la carpeta `assets`, que sería `shared/images/characters/GF_assets.png`.

En otras palabras, estructura tu mod de la siguiente manera:

```
-assets
-manifest
-plugins
-mods
 |-myMod
   |-shared
     |-images
       |-characters
         |-GF_assets.png
         |-GF_assets.xml
   |-_polymod_meta.json
-Funkin.exe
```

Cuando el juego vaya a cargar los sprites de un personaje, realizará una solicitud interna para recuperar el archivo `assets/shared/images/characters/GF_assets.png` que se utilizará para la textura (y el `XML` correspondiente para dividir la imagen en fotogramas individuales). Cuando lo hace, Polymod intercepta esa solicitud y comprueba si hay un archivo con ese nombre entre los mods cargados y, si es así, utilizará ese en su lugar.

## Adición de recursos

Polymod también te permite añadir nuevos archivos al juego. Esto es importante, ya que intentar colocar nuevos archivos en el directorio `assets` no funciona, ya que el juego no los reconocerá.

Aún así, hay que indicarle al juego que cargue esos recursos para que se utilicen, pero hay muchas funciones que cargan todos los archivos de una carpeta determinada (como el Registro de canciones, el Registro de personajes, el Registro de escenarios, etc.). Las veremos con más detalle más adelante.
