# El archivo de metadatos

Para empezar, crea una nueva carpeta dentro de tu carpeta `mods`. Aquí es donde se almacenarán los recursos y los scripts de tu mod. A continuación, crea un nuevo archivo de texto y cámbiale el nombre a `_polymod_meta.json`. ¡Asegúrate de no haberlo llamado por error `_polymod_meta.json.txt`!

Dentro de este archivo, pondremos la información que el juego necesita para conocer tu mod. Te recomiendo hacerlo con un programa como [Visual Studio Code](https://code.visualstudio.com/), ya que te corregirá si colocas mal una coma o algo por el estilo.

```json
{
  "title": "Intro Mod",
  "description": "Un mod introductorio.",
  "contributors": [
    {
      "name": "EliteMasterEric"
    }
  ],
  "dependencies": {
    "modA": "1.0.0"
  },
  "optionalDependencies": {
    "modB": "1.3.2"
  },
  "api_version": "0.6.3",
  "mod_version": "1.0.0",
  "license": "Apache-2.0"
}
```

`_polymod_meta.json` tiene los siguientes campos:

- `title`: Un nombre legible para el mod.
- `description`: Una descripción legible del mod.
- `contributors`: Una lista de objetos Contributor.
- `homepage`: Una URL donde los usuarios pueden obtener más información sobre tu mod.
- `dependencies`: Un mapa de ID de mods que son dependencias obligatorias, junto con sus números de versión.
  - Estos son los mods que también deben cargarse para que este mod se cargue.
  - Si el mod no está incluido, fallará.
  - La lista de mods se reordenará de manera que las dependencias se carguen primero.
- `optionalDependencies`: Un mapa de ID de mods que son dependencias opcionales, junto con sus números de versión.
  - No es necesario que estos mods estén instalados para que este mod se cargue, pero sí obligarán a reordenar la lista de mods para que las dependencias se carguen antes que este mod.
- `api_version`: Un número de versión utilizado para determinar si los mods son compatibles con tu copia de Funkin'. Cambia esto por el número de versión de Friday Night Funkin' que quieras admitir, preferiblemente la más reciente (`0.6.3` en el momento de escribir este artículo).
- `mod_version`: Un número de versión específico para tu mod. Elige cualquier versión o déjalo en `1.0.0`.
- `license`: La licencia bajo la que se distribuye tu mod. [Elige una de aquí](https://opensource.org/licenses) o déjala como `Apache-2.0`.

Un colaborador tiene los siguientes campos:

- `name`: El nombre del colaborador.
- `role`: *(opcional)* El papel que desempeñó el colaborador, por ejemplo, «Artista» o «Programador»
- `email`: *(opcional)* Un correo electrónico de contacto
- `url`: *(opcional)* La URL de una página web

Muchos de estos campos están pensados para ser utilizados en el futuro por una próximo menú de selección de mods, que permitirá a los usuarios organizar sus modsr
