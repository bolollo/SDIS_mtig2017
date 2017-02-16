***********************************
Conceptos básicos Servidor de Mapas
***********************************

.. note::

	=================  ====================================================
	Fecha              Autores
	=================  ====================================================
	14 Febrero 2017   * Wladimir Szczerban
	=================  ====================================================

	©2017 Wladimir Szczerban

	Excepto donde quede reflejado de otra manera, la presente documentación se halla bajo licencia :
  Creative Commons (Creative Commons - Attribution - Share Alike: http://creativecommons.org/licenses/by-sa/3.0/deed.es)

Servidor de Mapas (WMS)
========================

El estándar *Web Map Service* (WMS) creado por el *Open Geospatial Consortium* (OGC) define los elementos necesarios para un servicio de mapas.

Un WMS renderiza datos tanto vectoriales como raster en diferentes estilos y proyecciones cartográficas y devuelve una imagen con información geográfica "mapa".

Un WMS está compuesto por 2 operaciones o interfaces obligatorias y 3 opcionales: GetCapabilities *(obligatoria)*, GetMap *(obligatoria)*,  GetFeatureInfo *(opcional)*, DescribeLayer *(opcional)* y GetLegendGraphic *(opcional)*.

1. **GetCapabilities**: nos permite descubrir cuáles son las capacidades del servidor. Como respuesta obtenemos un archivo en formato xml donde se puede saber cuáles son las versiones de WMS soportadas por el servidor, cuál es el sistema de referencia, las coordenadas, qué formato de imagen soporta y las capas de información que contiene.

  Los parámetros para lanzar la petición:

  *obligatorios:*

  * REQUEST = GetCapabilities

  * SERVICE = WMS

  *opcionales:*

  * VERSION = 1.1.1 *(version del estándar WMS)*

  * FORMATO = text/html

  **Ejemplo**

  http://galileo.icc.cat/arcgis/services/icc_limadmin_v_r/MapServer/WMSServer?REQUEST=GetCapabilities&SERVICE=WMS

2. **GetMap**: una petición GetMap devolverá un mapa en formato imagen, ya sea un PNG, JPEG, GIF, etc.

  Los parámetros para lanzar la petición:

  *obligatorios:*

  * REQUEST = GetMap

  * SERVICE = WMS

  * VERSION = 1.1.1 *(version del estándar WMS)*

  * LAYERS = nombre de la(s) capa(s)

  * STYLES = si no hay estilo se puede dejar en blanco

  * SRS ó CRS = 23031 *(código EPSG del sistéma de referencia)*

  * BBOX = minx,miny,maxx,maxy *(caja de coordenadas del mapa)*

  * WIDTH = número píxeles de ancho

  * HEIGHT = número píxeles de altura

  * FORMATO = image/png *(formato de salida de la imagen)*

  *opcionales:*

  * TRANSPARENT = indica si el fondo del mapa debe ser transparente. Los valores son verdadero (true) o falso (false).

  * BGCOLOR = color de fondo para la imagen del mapa. El valor está en la formato RRGGBB hexadecimal

  * SLD = una URL que hace referencia a un archivo XML StyledLayerDescriptor  que controla el estilo de las capas de mapa


  **Ejemplo**

  http://galileo.icc.cat/arcgis/services/icc_limadmin_v_r/MapServer/WMSServer?REQUEST=GetMap&SERVICE=WMS&VERSION=1.1.1&LAYERS=5&FORMAT=image/png&STYLES=&SRS=EPSG:25831&BBOX=257904,4484796,680304,4907196&WIDTH=768&HEIGHT=768

3. **GetFeatureInfo**: esta petición sirve para mostrar los atributos de los objetos del mapa, vuelve la información en formato de tabla o XML. Si una capa está marcada como "consultable" *(queryable)*, se puede solicitar datos sobre una coordenada de la imagen del mapa.

  Los parámetros para lanzar la petición:

  *obligatorios:*

  * REQUEST = GetFeatureInfo

  * SERVICE = WMS

  * VERSION = 1.1.1 *(version del estándar WMS)*

  * QUERY_LAYERS = nombre de la(s) capa(s)

  * STYLES = si no hay estilo se puede dejar en blanco

  * SRS ó CRS = 23031 *(código EPSG del sistéma de referencia)*

  * BBOX = minx,miny,maxx,maxy *(caja de coordenadas del mapa)*

  * WIDTH = número píxeles de ancho

  * HEIGHT = número píxeles de altura

  * X = valor del píxel a consultar

  * Y = valor del píxel a consultar

  *opcionales:*

  * INFO_FORMAT = text/html *(formato de la respuesta)*

  * FEATURE_COUNT = número máximo de elementos a devolver

  **Ejemplo**

  http://galileo.icc.cat/arcgis/services/icc_limadmin_v_r/MapServer/WMSServer?REQUEST=GetFeatureInfo&SERVICE=WMS&VERSION=1.1.1&LAYERS=5&QUERY_LAYERS=5&INFO_FORMAT=text/html&STYLES=&SRS=EPSG:25831&BBOX=257904,4484796,680304,4907196&WIDTH=768&HEIGHT=768&X=295&Y=580

4. **DescribeLayer**: devuelve los tipos de entidad de la capa o capas especificadas, que se pueden describir adicionalmente mediante solicitudes WFS o WCS.

  Los parámetros para lanzar la petición:

  *obligatorios:*

  * REQUEST = DescribeLayer

  * SERVICE = WMS

  * VERSION = 1.1.1

  * LAYERS = nombre de la(s) capa(s)

  **Ejemplo**

  http://guifi.net/cgi-bin/mapserv?map=/home/guifi/maps.guifi.net/guifimaps/GMap.map&request=DescribeLayer&service=wms&version=1.1.1&layers=Nodes

5. **GetLegendGraphic**: devuelve una imagen de la imagen de la leyenda del mapa de una capa, proporcionando una guía visual de los elementos del mapa.

  Los parámetros para lanzar la petición:

  *obligatorios:*

  * REQUEST = GetLegendGraphic

  * LAYER = nombre de la capa

  * FORMAT = image/png *(formato de la respuesta)*

  *opcionales:*

  * WIDTH = número píxeles de ancho

  * HEIGHT = número píxeles de altura

  **Ejemplo**

  http://wms.guifi.net/cgi-bin/mapserv?map=/home/guifi/maps.guifi.net/guifimaps/GMap.map&version=1.3.0&service=WMS&request=GetLegendGraphic&sld_version=1.1.0&layer=Nodes&format=image/png&STYLE=default
