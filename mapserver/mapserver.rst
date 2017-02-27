*********
MapServer
*********

.. note::

	=================  ====================================================
	Fecha              Autores
	=================  ====================================================
	14 Febrero 2017    * Wladimir Szczerban
	=================  ====================================================

	©2017 Wladimir Szczerban

	Excepto donde quede reflejado de otra manera, la presente documentación se halla bajo licencia: Creative Commons (Creative Commons - Attribution - Share Alike: http://creativecommons.org/licenses/by-sa/3.0/deed.es)

MapServer
=========

Es un servidor de código abierto programado en C/C++, permite compartir y editar datos geoespaciales. Originalmente fue desarrollado por la Universidad de Minnesota (UMN) y por eso también se le conoce como *Minnesota MapServer* para diferenciarlo del producto comercial "map server" de Autodesk. Implementa las especificaciones Web Map Service (WMS) *(cliente/servidor)*, Web Feature Service no-transaccional (WFS) *(cliente/servidor)*, Web Map Context (WMC), Web Coverage Service(WCS), Filter Encoding, Styled Layer Descriptor (SLD), Geography Markup Language (GML), Sensor Observation Service (SOS), Observations and Measurements (OM).

http://www.mapserver.org/

Principales características
###########################

* Proporciona una API (MapScript) que permite acceder a las funcionalidades de MapServer desde diferentes lenguajes de programación como PHP, Java, Python, Perl, Ruby y .NET (C#).

* Soporta múltiples formatos de entrada (vectorial/ráster) y salida ya que usa GDAL/OGR.

* Soporta fuentes TrueType (útil para el etiquetado de elementos).

* Configuración "al vuelo" vía parámetros GET pasados por URL.

* Configuración basada en el fichero mapfile *.map*.

* Incluye la posibilidad de usar una plantilla HTML MapServer para generar una página web.

* Es multiplataforma

* Incluye un componente de cacheado *MapCache* para generar pirámides de teselas (tiles) con la finalidad de acelerar y optimizar la respuesta a la hora de servir mapas. Soporta el estándar WMTS, también soporta otras salidas como TMS, VirtualEarth/Bing y peticiones Google Maps.

* Incluye un componente *TinyOWS* que da soporte para edición de datos a través del protocolo WFS transactional (WFS-T).
