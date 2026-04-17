# Orden de carga de los mods

Quizás te preguntes qué ocurre cuando varios mods proporcionan un mismo archivo.

La respuesta es sencilla: el orden de los mods es importante. Si tienes instalados dos mods que sustituyen un recurso concreto, el mod que se cargue en último lugar tendrá prioridad sobre los mods que se hayan cargado antes, de forma similar al sistema de paquetes de recursos de Minecraft. Esto se evalúa archivo por archivo, por lo que si el mod A sustituye a Pico y a GF y el mod B sustituye solo a GF, y el mod B se carga después del mod A, verás al Pico del mod A y a la Girlfriend del mod B.

En la versión actual de Friday Night Funkin', no hay ninguna forma accesible de modificar el orden de carga de los mods. Los mods se cargarán por defecto en orden alfabético, cargándose primero las dependencias.
