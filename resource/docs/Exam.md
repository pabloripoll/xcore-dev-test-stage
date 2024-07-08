# Exam

La prueba consiste en modificar un antiguo repositorio que usábamos, llamado core-daemon, el cuál puedes encontrar aquí: [link]

Nuestra antigua red (donde almacenábamos los archivos) funcionaba enviando el contenido a nodos (servidores) anónimos que lo almacenaban.

Este proyecto es el que se instalaban los operadores de nodos que querían unirse a nuestra red, para poder montar un nodo donde se almacenaban los shards que les enviábamos (shard = trozo de un archivo).

En este proyecto, los nodos almacenan los shards utilizando KFS y LevelDB. Son bases de datos binarias de tipo clave-valor. En LevelDB se indexa como clave, el hash del shard y como valor, su contenido.

La prueba consiste en ampliar la funcionalidad de este proyecto de forma que los shards se almacenen en ficheros convencionales, en los que el nombre del fichero sea el hash y el contenido del archivo sea el propio contenido del shard.

Es decir, si almaceno un shard con hash 'aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa', se creará un archivo con ese nombre y su contenido serán los datos binarios recibidos.

Puedes modificar todo lo que quieras, hacer un zip (por favor, recuerda eliminar los node_modules antes de hacerlo) y enviármelo de vuelta cuando lo tengas.

Las instrucciones de instalación están en el README (Usar Node v10, instalar con "yarn —ignore-engines" etc).

Con correr los tests ("yarn run test"), escribir los tuyos sobre el código que has desarrollado y pasarlos, puedes completar la prueba sin necesidad de levantar el servidor del nodo. (Tienes otros tests muy útiles que ya existen, a modo de ejemplo)Dos puntos a tener en cuenta:

Preferimos una solución limpia a una rápida.

El objetivo no es sustituir lo que hay ya implementado, sino implementar cierta interfaz con la funcionalidad que se pide. Esto lo menciono porque hay gente que al hacer la prueba ha cogido el código ya existente y lo ha reemplazado, que no es lo que se busca.

Esta prueba evalúa:
- Conocimientos generalistas en JavaScript.
- Desenvolverse en un entorno nuevo y tal vez, diferente.
- El tiempo máximo para entregar la prueba es de 2 días.


Un saludo y suerte!
