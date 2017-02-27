**********************************
Leaflet - Visualizar una capa WMTS
**********************************

.. note::

	=================  ====================================================
	Fecha              Autores
	=================  ====================================================
	14 Febrero 2017    * Wladimir Szczerban
	=================  ====================================================

	©2017 Wladimir Szczerban

	Excepto donde quede reflejado de otra manera, la presente documentación se halla bajo licencia: Creative Commons (Creative Commons - Attribution - Share Alike: http://creativecommons.org/licenses/by-sa/3.0/deed.es)

Leaflet - Visualizar una capa WMTS
==================================

Utilizaremos la librería **Leaflet** para crear un cliente *ligero* web donde visualizar servicios WMS.

#. Crear una carpeta llamada *visor* dentro del directorio htdocs del Apache. ::

		C:\ms4w\Apache\htdocs\visor

#. Crear el archivo *index.html* dentro de la carpeta visor. En este archivo crearemos la estructura básica del nuestro html y cargaremos la librería Leaflet. Para ello escribir los siguiente: ::

		<html>
		<head>
			<meta charset="UTF-8">
			<title>Visor simple con Leaflet</title>
			<link rel="stylesheet" href="https://unpkg.com/leaflet@1.0.3/dist/leaflet.css" />
			<style type="text/css">
			  #mapid { height: 600px; width: 600px;}
			</style>
		</head>
		<body>
			<div id="mapid"></div>
			<script src="https://unpkg.com/leaflet@1.0.3/dist/leaflet.js"></script>
		</body>
		</html>

#. Agregar el código para crear el mapa. Debajo de donde cargamos la librería de Leaflet escribir lo siguiente: ::

		<script>
			//Creamos el objeto mapa.
			var map = L.map('mapid').setView([41.68, 1.85], 9);
		</script>

#. Agregar la capa WMTS. Luego de la declaración del objeto mapa escribir: ::

		var wmtsOpenStreetMap = L.tileLayer('http://{s}.tile.osm.org/{z}/{x}/{y}.png', {
		  attribution: '&copy; <a href="http://osm.org/copyright">OpenStreetMap</a> contributors'
		}).addTo(map);

#. Abrir el navegador y ver que nuestro visor está funcionando correctamente. ::

		http://localhost:81/visor/index.html


Ejercicio:
##########

#. Agregar la capa WMTS de la ortofoto o topográfico del servicio WMTS del ICGC (http://icgc.cat)
