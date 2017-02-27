*********
GeoServer
*********

.. note::

	=================  ====================================================
	Fecha              Autores
	=================  ====================================================
	14 Febrero 2017    * Wladimir Szczerban
	=================  ====================================================

	©2017 Wladimir Szczerban

	Excepto donde quede reflejado de otra manera, la presente documentación se halla bajo licencia: Creative Commons (Creative Commons - Attribution - Share Alike: http://creativecommons.org/licenses/by-sa/3.0/deed.es)

GeoServer
=========

Es un servidor de código abierto programado en Java, permite compartir y editar datos geoespaciales. GeoServer sirve de implementación de referencia del estándar Web Feature Service (WFS) de la OGC, también implementa las especificaciones Web Map Service (WMS) y Web Coverage Service(WCS).

http://geoserver.org/

Principales características
###########################

* Fácil utilización y administración a través de una herramienta de administración web. No es necesario tocar archivos de configuración.

* Soporte para edición de datos a través del protocolo WFS transactional (WFS-T).

* Al ser programado en Java está basado en servlets (JEE), puede funcionar en cualquier contenedor de servlets. Es multiplataforma.

* Es compatible para ser usado con extensiones.

* Incluye integrado un cliente OpenLayers que permite visualizar las capas de datos.

* Incluye un componente de cacheado *GeoWebCache* para generar pirámides de teselas (tiles) con la finalidad de acelerar y optimizar la respuesta a la hora de servir mapas. Soporta los estándares WMS-C y WMTS, también soporta otras salidas como TMS, Google Maps KML, Virtual Earth.
