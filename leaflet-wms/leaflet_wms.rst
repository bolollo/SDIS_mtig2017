*********************************
Leaflet - Visualizar una capa WMS
*********************************

.. note::

	=================  ====================================================
	Fecha              Autores
	=================  ====================================================
	14 Febrero 2017    * Wladimir Szczerban
	=================  ====================================================

	©2017 Wladimir Szczerban

	Excepto donde quede reflejado de otra manera, la presente documentación se halla bajo licencia: Creative Commons (Creative Commons - Attribution - Share Alike: http://creativecommons.org/licenses/by-sa/3.0/deed.es)

Leaflet - Visualizar una capa WMS
=================================

Utilizaremos la librería **Leaflet** para crear un cliente *ligero* web donde visualizar servicios WMS.

#. Crear una carpeta llamada *visor* dentro del directorio htdocs del Apache. ::
   	
		C:\ms4w\Apache\htdocs\visor

#. Crear el archivo *index.html* dentro de la carpeta visor. En este archivo crearemos la estructura básica del nuestro html y cargaremos la librería Leaflet. Para ello escribir los siguiente: ::
   
		<html>
		<head>
			<meta charset="UTF-8">
			<title>Visor simple con Leaflet</title>
			<link rel="stylesheet" href="https://unpkg.com/leaflet@1.0.3/dist/leaflet.css" />
			<style>
				#mapid { height: 600px; width: 600px;}
			</style>
		</head>
		<body>
			<div id="mapid"></div>
			<script src="https://unpkg.com/leaflet@1.0.3/dist/leaflet.js"></script>
		</body>
		</html>

#. Agregar el código para crear el mapa. Debajo de donde cargamos la librería de Leaflet escribir lo siguente: ::
   
		<script>
			//Creamos el objeto mapa.
			var map = L.map('mapid').setView([41.68, 1.85], 9);		
		</script>

#. Agregar la capa WMS. Luego de la declaración del objeto mapa escribir: ::
   
		var wmsTopoIcgc = L.tileLayer.wms('http://geoserveis.icgc.cat/icc_mapesbase/wms/service?', {
		  layers: 'mtc5m'
		}).addTo(map);

#. Abrir el navegador y ver que nuestro visor está funcionando correctamente. ::
   
		http://localhost:81/visor/index.html
   

Ejercicio:
==========

#. Agregar la capa pein de nuestro servicio WMS de Pein


