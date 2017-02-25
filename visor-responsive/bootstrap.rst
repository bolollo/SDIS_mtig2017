*********
Bootstrap
*********

.. note::

	=================  ====================================================
	Fecha              Autores
	=================  ====================================================
	14 Febrero 2017    * Wladimir Szczerban
	=================  ====================================================

	©2017 Wladimir Szczerban

	Excepto donde quede reflejado de otra manera, la presente documentación se halla bajo licencia: Creative Commons (Creative Commons - Attribution - Share Alike: http://creativecommons.org/licenses/by-sa/3.0/deed.es)

Bootstrap
=========

Bootstrap es un framework de desarrollo de HTML, CSS y JS pensado para desarrollar aplicaciones Web responsivas que se adapten al móvil. 

Bootstrap y todos sus complementos (plugins) dependen de la librería jQuery[#]_, por lo tanto en nuestras aplicaciones Web es necesario agregar la librería jQuery antes que la librería de Bootstrap.

Bootstrap basa el diseño de la página en un sistema de cuadrículas para crear distribuciones de página por medio de una serie de filas y columnas que albergan su contenido. El sistema de cuadrículas está basado en 12 columnas que varian su tamaño dependiendo del dispositivo. Se basa en cuatro clases que dependen del tamaño del dispositivo.

+----------------------------------------------+-----------------------------------------+--------------------------------------------+-----------------------------------------+
| Dispositivos muy pequeños Teléfonos (<768px) | Dispositivos pequeños Tabletas (≥768px) | Dispositivos medianos Escritorios (≥992px) | Dispositivos grandes Escritorios(≥1200px) |
+----------------------------------------------+-----------------------------------------+--------------------------------------------+-----------------------------------------+

Bootstrap tiene una serie de componentes y complementos Javascript que facilitan el desarrollo de las aplicaciones Web. Algunos de los componentes son: botones, barras de navegación, ventanas de dialogos, listas, control de pestañas, etc.

A continuación crearemos una página web secilla utilizando Bootstrap.

#. Crear una carpeta llamada *visor* dentro del directorio htdocs del Apache. ::
   	
		C:\ms4w\Apache\htdocs\visor

#. Crear el archivo *movil.html* dentro de la carpeta visor. En este archivo crearemos la estructura básica del nuestro html y cargaremos las librerías jQuery y Bootstrap. Para ello escribir los siguiente: ::

		<!DOCTYPE html>
		<html>
			<head>
				<title>visor reponsivo con Leaflet</title>
				<meta charset="utf-8">
				<meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1">
			    <meta name="description" content="Demo project with jQuery">
				<meta name="viewport" content="width=device-width, initial-scale=1">
				<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css" integrity="sha384-BVYiiSIFeK1dGmJRAkycuHAHRg32OmUcww7on3RYdg4Va+PmSTsz/K68vbdEjh4u" crossorigin="anonymous">
				<style type="text/css"></style>
			</head>
			<body>
				<h1>Hola mundo, Bootstrap!</h1>
			</body>
			<script src="https://code.jquery.com/jquery-3.1.1.min.js" integrity="sha256-hVVnYaiADRTO2PzUGmuLJr8BLUSjGIZsDYGmIJLv2b8="
		  crossorigin="anonymous"></script>
			<script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js" integrity="sha384-Tc5IQib027qvyjSMfHjOMaLkfuWVxZxUPnCJA7l2mCWNIpG9mGCD8wGNIcPD7Txa" crossorigin="anonymous"></script>
		</html>

#. Abrir el navegador y ver que nuestra aplicación está funcionando correctamente. ::
   
		http://localhost:81/visor/movil.html

.. [#] https://jquery.com/