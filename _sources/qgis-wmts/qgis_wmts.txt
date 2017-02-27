*******************************
QGIS - Visualizar una capa WMTS
*******************************

.. note::

	=================  ====================================================
	Fecha              Autores
	=================  ====================================================
	14 Febrero 2017    * Wladimir Szczerban
	=================  ====================================================

	©2017 Wladimir Szczerban

	Excepto donde quede reflejado de otra manera, la presente documentación se halla bajo licencia: Creative Commons (Creative Commons - Attribution - Share Alike: http://creativecommons.org/licenses/by-sa/3.0/deed.es)

QGIS - Visualizar una capa WMTS
===============================

Utilizaremos el programa **QGIS** para visualizar servicios WMTS.

#. Abrir el *QGIS desktop* y crear un nuevo proyecto llamado *mtig_sdi*

#. En el panel explorador del QGIS presionar con el botón derecho del mouse sobre *Tile Server (XYZ)* para desplegar el menú donde debemos seleccionar la opción de *New Connection...* que nos mostrará el diálogo de añadir nueva conexión.

    .. |logo_add| image:: _images/add_wmts.png
      :align: middle
      :alt: añadir un wmts

    +------------+
    | |logo_add| |
    +------------+

#. En el diálogo de añadir nueva conexión debemos escribir la URL de nuestro servicio y presionar el botón de Aceptar. Luego se desplegarán un dialogo donde debemos colocar el nombre que queremos dar a la conexión y presionamos Aceptar.

    .. |logo_wmts_osm| image:: _images/wmts_osm.png
      :align: middle
      :alt: conexión wmts osm

    +-----------------+
    | |logo_wmts_osm| |
    +-----------------+

    En este caso utilizaremos la url del servidor de teselas de OpenStreetMap. ::

        http://c.tile.osm.org/{z}/{x}/{y}.png

#. En el panel explorador ahora debe aparece la conexión definida. Para agregarla al mapa hacemos doble click sobre el nombre de la conexión.

    .. |logo_ver_wmts| image:: _images/visualizar_wmts.png
      :align: middle
      :alt: ver wms

    +-----------------+
    | |logo_ver_wmts| |
    +-----------------+

Ejercicio:
##########

#. Agregar la capa WMTS de la ortofoto o topográfico del servicio WMTS del ICGC (http://icgc.cat)
