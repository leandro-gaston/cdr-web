---
layout: post					# Lo que siga a un hash es un comentario
title:  "[P014] cdrPrinter"				# Obligatorio.
date:   2017-09-05 17:49:00 -0300		# Obligatorio. Creo que la hora y zona no, pero bue...
descripcion: "Este proyecto consiste en el desarrollo de la impresora 3D del CDR. Se realizó el diseño de las piezas necesarias y se reutilizaron materiales para abaratar costos. La impresora se encuentra actualmente en funcionamiento."	# Obligatorio.

categoria: Proyecto					# Obligatorio. Como está.
permalink: /proyectos/014/			# Obligatorio. XXX = Num del Proyecto
estado: "Finalizado"				# Obligatorio. "Finalizado" o lo que quieran. 

img: "/img/proy/014.jpg"				# Obligatorio. XXX = Num del Proyecto
portada: "/img/proy/portadas/014.jpg"	# Obligatorio. XXX = Num del Proyecto

github:   "https://github.com/ClubDeRobotica-UNLP/cdrPrinter.git"	
facebook: "https://www.facebook.com/pg/cdrunlp/photos/?tab=album&album_id=718283848369251"
youtube: ""						# Opcional. Direccion a la playlist de YouTube.
---

Primera versión de una impresora 3D para el CDR. Proyecto cdrPrinter, alias "Pinocho".

### Presentación

La idea surgió a fines de 2015. Se propuso generar una impresora 3D con estructura similar a la de este [proyecto](http://www.mydiycnc.com/) utilizando varillas y maderas recicladas. 

### Implementación estructural y mecánica

Lo primero a realizar fue el diseño de la estructura mecánica con las piezas requeridas. Para ello, se utilizó un programa de CAD 3D en el cual se diseñó cada pieza independientemente y luego se las integró en un mismo ensamblaje con las relaciones de posición adecuadas, tal cual se verían en la realidad.

Para el eje x se utilizó una madera de 40 cm x 37 cm. En ella se ubicaron 4 sostiene varillas, amuradas a la madera con dos tornillos cada una. Las varillas utilizadas para el desplazamiento de los carros fueron de 12 y 10 mm de diámetro. Se diseñó y se mandó a cortar en láser una superficie que haga de carro del eje x, de las dimensiones adecuadas para que la cama caliente de una impresora 3D típica (20cm x 20cm) pueda acoplarse sin problemas. Para el movimiento del carro se utilizó un motor con correa dentada, necesitando piezas de sostén del motor en un extremo y una pieza de sostén para una rueda libre en el otro. Para tensar la correa se colocó una pieza debajo de la madera MDF del carro. El carro se desplaza sobre las varillas utilizando rodamientos lineales, por lo que se diseñaron piezas tipo receptáculo para dichos rodamientos. En la siguiente Figura se muestra un render 3D del diseño del eje x completo.

<img src="/img/proy/P014/ejex.png" width="1200" height="600">

Para el eje z se utilizó una estructura de maderas, a modo de arco. A diferencia de algunas impresoras (como las Prusa 3i) que tienen los motores apoyados en la base de la impresora, se decidió colocar los motores del eje z sobre el travesaño de la impresora. Para ello, se diseñaron una pieza que sujetara el motor al travesaño y se replicó para el otro lado. En cada pieza se colocó una varilla de 10 mm de diámetro y de 35 cm de largo. Dichas varillas apoyan sobre unas maderas de MDF cortadas a láser que facilitan su correcta alineación vertical. De los motores surgen varillas roscadas de 5 mm, sujetas a los mismos con acoples lineales. Finalmente, este eje cuenta con dos piezas que se mueven hacia abajo o arriba, de forma nivelada, que forman parte de lo que es el eje y de la impresora. A continuación se muestra un render 3D del diseño del eje z completo.

<img src="/img/proy/P014/ejez.png" width="1200" height="600">

El eje y consiste básicamente en un carro que debe sujetar al hot-end, que es el encargado de derretir el filamento de plástico. El carro, implementado en una pieza diseñada específicamente, utiliza para su deplazamiento una correa al igual que el eje x y dos varillas de 10 mm de diámetro. El carro cuenta con compartimientos para 3 rodamientos lineales y una extensión de plástico para tensar la correa adecuadamente. El eje y se encuentra graficado a continuación.

<img src="/img/proy/P014/ejey.png" width="1200" height="600">

### Hot-end, extrusor y cama caliente

Uno de los elementos fundamentales de una impresora 3D es el hot-end. Es el encargado de derretir el filamento de plástico para crear una pieza 3D.  Para ello porta una resistencia calefactora y una unidad refrigerante, en general un ventilador. Un agregado en la unidad refrigerante del hot-end que mejora la calidad de las piezas es lo que se conoce como "fan de capa". Básicamente son ventiladores comandados por la unidad de control de la impresora que refrigeran levemente la capa impresa por el hot-end para lograr una mejor terminación de la pieza. Actualmente la cdrPrinter utiliza un modelo similar a [este](https://www.thingiverse.com/thing:2131351).

El extrusor es el encargado de proveer al hot-end del plástico necesario a la velocidad apropiada. Para ello, cuenta con un motor paso a paso que mueve el rollo de filamento la cantidad justa para que el hot-end tenga un flujo continuo de plástico y pueda crear piezas de buena calidad. Hay dos grandes clases de extrusores: directos o indirectos. Los directos se colocan sobre el carro que porta al hot-end mientras que los indirectos se colocan sobre alguna superficie de la estructura de la impresora y se conectan al hot-end a través de una manguera, en general de teflón. En el caso de nuestra impresora, la misma utiliza [este](https://www.thingiverse.com/thing:1359717) extrusor de tipo indirecto.

La cama caliente sirve de superficie para la creación de la pieza 3D. Su temperatura es regulada desde la electrónica de control de la impresora. La temperatura de la cama varía según el tipo de filamento (ABS, PLA, etc) y según el número de capa.

### Electrónica de control y alimentación

Para el control de la impresora se utilizó un Arduino Mega en conjunto con un shield RAMPS 1.4. El shield mencionado posee conexiones para la resistencia calefactora, para la cama caliente, para los motores, para los fines de carrera además de otras conexiones para dispositivos auxiliares (display, tarjeta SD, etc). Los drivers utilizados por los motores fueron los DRV8825. Los fines de carrera utilizados fueron obtenidos de fotocopiadoras en desuso, y se acoplaron a cada eje utilizando piezas diseñadas apropiadamente. La impresora es controlada por una PC, utilizando un software slicer a través de un cable USB tipo B, no teniendo la opción de utilizar una tarjeta SD. El Arduino con su shield fueron ensamblados dentro de una caja contenedora, que permite mantener el cableado de manera prolija y guardar de la suciedad a la electrónica. Para ello, se utilizó un modelo disponible en la [web](https://www.thingiverse.com/thing:1640870). 

Para la alimentación de los motores y de la resistencia calefactora del hot-end se utilizó una fuente de PC reciclada. La tensión de alimentación utilizada fue de 12 V. Para alimentar la cama caliente se utilizó otra fuente de PC reciclada debido a que el consumo necesario excedía la capacidad de una sola de las fuentes disponibles.

### Conclusiones y resultados

La impresora se encuentra operativa desde mediados de 2016 aunque a partir de 2017 es que cuenta con todas las mejoras mencionadas en este post. Es utilizada para proyectos del CDR, para la construcción de proyectos de robótica. A continuación, algunas creaciones de la impresora.

<img src="/img/proy/P014/creaciones.jpg" width="1200">
<img src="/img/proy/P014/creaciones2.jpg" width="1200">
<img src="/img/proy/P014/creaciones3.jpg" width="1200">


Cualquier interesado puede acercarnos su consulta o acercarse a la oficina del CDR para verla en funcionamiento.