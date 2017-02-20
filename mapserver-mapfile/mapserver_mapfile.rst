*******************
MapServer - Mapfile
*******************

.. note::

	=================  ====================================================
	Fecha              Autores
	=================  ====================================================
	14 Febrero 2017    * Wladimir Szczerban
	=================  ====================================================

	©2017 Wladimir Szczerban

	Excepto donde quede reflejado de otra manera, la presente documentación se halla bajo licencia: Creative Commons (Creative Commons - Attribution - Share Alike: http://creativecommons.org/licenses/by-sa/3.0/deed.es)

MapServer - Mapfile
===================

El *Mapfile* (.map) es el corazón de MapServer, este archivo define las relaciones entre los objetos, la localización de los datos y define cómo debe ser dibujada la cartografía. Para entender el funcionamiento de MapServer hay que tener claro que una capa (LAYER) es la combinación de datos más estilos. A los datos se les da estilos usando directivas CLASS y STYLE, tanto en la forma de atributo como la geometría.

A la hora de crear el archivo map se han de tener en cuenta los siguientes aspectos:

* MapServer **NO** distigue entre mayúsculas y minúsculas.

* El Mapfile se lee de arriba a abajo por MapServer; esto significa que las capas situadas cerca de la parte superior del Mapfile serán dibujadas antes de aquellas cerca del final del archivo. Por lo tanto, los usuarios normalmente colocan imágenes de fondo y otros tipos de capas de fondo cerca de la parte superior de su mapfile, y líneas y puntos cerca de la parte inferior de su mapfile.

* Las cadenas que contienen caracteres no alfanuméricos o una palabra clave de MapServer deben ir entre comillas. Se recomienda poner TODAS las cadenas en comillas dobles.

* El Mapfile se espera que este codificado en UTF-8. Los archivos no UTF-8 tendrán que ser convertidos a UTF-8.

* Los comentarios deben ir precedidos por el carácter #.

* El archivo .map tiene una estructura jerárquica y por sí solo representa el objeto MAP, dentro de este objeto, existen otros objetos que contienen clases y propiedades de clase.

* Las rutas de los ficheros pueden ser dadas como rutas absolutas, o como rutas relativas a la ubicación del archivo .map. Además, los archivos de datos se pueden especificar en relación con el SHAPEPATH.

* Cada objeto tiene un inicio, que es el nombre del objeto y un final, expresado con el parámetro END.

* MapServer acepta colores en valores RGB o como una cadena hexadecimal.

* Los atributos se nombran utilizando la siguiente sintaxis: [NOMREATRIBUTO]. Tenga en cuenta que el nombre del atributo incluido entre los corchetes ES SENSIBLE A MAYÚSCULAS. Por lo general, los conjuntos de datos de forma generados por ESRI tienen sus atributos (nombres de columnas .dbf) todos en mayúsculas, por ejemplo, y para PostGIS, SIEMPRE utilice minúsculas.

* Se recomienda que el archivo Mapfile no esté en ruta accesible desde internet

Principales objetos del archivo .map
####################################

**MAP:** Es el objeto principal del mapfile y contiene a todos los objetos

**NAME:** Nombre del proyecto

**STATUS:** Indica el estado de visualización del proyecto. Sus valores pueden ser ON, DEFAULT o OFF, estos valores pueden ser cambiados en ejecución.

**SIZE:** Tamaño del píxel del mapa.

**EXTENT:** Corresponde al BBOX del mapa.

**UNITS:** Unidades del mapa.

**SHAPEPATH:** Ruta donde se encuentra la cartografía.

**IMAGECOLOR:** Color de fondo de la imagen del mapa.

**IMAGETYPE:** Formato de salida del mapa.

**PROJECTION:** Corresponde al SRS del mapa.

**WEB:** Uno de los principales objetos dentro de WEB es el objeto METADATA, donde describimos parte del proyecto. Esta descripción aparecerá en la petición GetCapabilities.

**SYMBOL:** Posibilidad de definir símbolos e imágenes asociadas con objetos cartográficos.

**LAYER:** Este objeto permite describir cómo son las capas. Sus objetos más importantes son:

  **NAME:** Nombre de la capa.

  **TYPE:** Geometría de la capa.

  **STATUS:** Estado de visualización de la capa.

  **DATA:** Datos asociadas a la capa.

  **TEMPLATE:** Normalmente se pasa el nombre de una página HTML, donde se mostrarían los datos resultados de una consulta. En el caso de una petición GetFeatureInfo no hace falta especificar ninguna página, simplemente se debe pasar un valor vacío.

  **CLASSITEM:** Nombre del campo que se usa en el CLASS.

  **METADATA:** Descripción de la capa.

  **LABELITEM:** Nombre del campo para etiquetar.

  **DUMP:** Sus valores pueden ser true o false y permiten exportar la capa al
  formato GML. *Nota*: desde la version 6.0 no se usa y se debe especificar en el METADATA de la capa.

  **CLASS:** Este objeto se utiliza para crear temáticos o simplemente para dar color a las capas. Sus objeto más importantes son:

    **NAME:** Nombre de la clase.

    **EXPRESSION:** Valor con el que se tematizará.

    **MINSCALEDENOM:** Escala mínima a la que la CLASE se pinta. La escala se da como el denominador de la fracción de escala real, por ejemplo para un mapa a una escala de 1:24.000, usar 24000.

    **MAXSCALEDENOM:** Escala máxima a la que la CLASE se pinta. La escala se da como el denominador de la fracción de escala real, por ejemplo para un mapa a una escala de 1:24.000, usar 24000.

    **LABEL:** Objeto que sirve para etiquetar. Sus objetos más importantes son:

      **MINFEATURESIZE:** El tamaño mínimo de un elemento que debe ser etiquetado. Dado en píxeles.

      **MINDISTANCE:** Distancia mínima entre etiquetas duplicadas. Dado en píxeles.

      **POSITION:** Posición respecto al objeto.

      **SIZE:** Tamaño de la etiqueta.

      **COLOR:** Color del texto.

    **STYLE:** Este objeto se utiliza para indicar los parámetros de simbolización y estilo. Sus objetos más importantes son:

      **COLOR:** Color usado para dibujar las geometrías.

      **OUTLINECOLOR:** Color usado para dibujar el contorno.

      **SYMBOL:** Simbolo usado para representar las geometrías

Estos son algunos de los objetos que se pueden definir en el archivo .map, para ver todos sus objetos: http://www.mapserver.org/mapfile/index.html
