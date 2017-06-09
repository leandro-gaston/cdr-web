---
layout: post					# Lo que siga a un hash es un comentario
title:  "[P013] Stick USB-UART"	# Obligatorio.
date:   2016-06-22 17:00:00 -0300		# Obligatorio. Creo que la hora y zona no, pero bue...
descripcion: "Este proyecto permite la comunicación entre una PC y un dispositivo que utilice UART (como un microntrolador, por ejemplo) a través de una interfaz USB. Los niveles lógicos permitidos son de 3.3V."	# Obligatorio.

categoria: Proyecto				# Obligatorio. Como está.
permalink: /proyectos/013/			# Obligatorio. XXX = Num del Proyecto
estado: "Finalizado"			# Obligatorio. "Finalizado" o lo que quieran.

img: "/img/proy/013.jpg"			# Obligatorio. XXX = Num del Proyecto
portada: "/img/proy/portadas/013.png"		# Obligatorio. XXX = Num del Proyecto

github: ""					# Opcional. Direccion del repositorio del proyecto.
facebook: ""					# Opcional. Direccion al album de Face.
youtube: ""					# Opcional. Direccion a la playlist de YouTube.
---

Primera versión de un conversor USB-UART para el club utilizando componentes discretos.

### Presentación

Luego de búsqueda de componentes para realizar el conversor, se eligió el [TUSB3410](http://www.ti.com.cn/cn/lit/ds/symlink/tusb3410.pdf).  
A excepción de un regulador de tensión, sólo son necesarios unos pocos componentes sencillos de conseguir: Capacitores, resistencias, leds y un diodo.

### Implementación

Para el diseño se buscó que el prototipo sea lo más pequeño posible pero también que el circuito pueda ser construído a mano con métodos caseros. También se apuntó a una forma tipo "stick", es decir que se conecta directamente a un puerto USB tipo A de una PC convencional. De allí recibe alimentación y mediante unos cables con conectores apropiados, interfacea con el dispositivo elegido para comunicación: microcontrolador, sensor, gps, etc. Además, posee un regulador con la capacidad de corriente suficiente para alimentar dispositivos de bajo consumo como sensores, IMUs, etc. , por lo que cuenta con dos salidas de alimentación de 3.3 V.

El circuito se implementó en una pequeña placa de 2.4cm x 6.7 cm. Doble capa.

El conversor ha sido testeado con diversos dispositivos entregando buenos resultados. Fue testeado hasta un baudrate de 115200 exitosamente.

El proyecto de altium se encuentra disponible como así también los componentes con su footprint en la [Librería de Altium del Club](/files/proyectos/common/Altium_CDR_Lib.rar).

### Para realizar la placa

- Circuito (imprimir a escala): [PDF](/files/proyectos/013/013_PCB.pdf)

- Esquemático: [PDF](/files/proyectos/013/013_Esquematico.pdf)

### Lista de componentes:

| COMP.			  |  ENCAPS.  | ESQUEMATICO  |  CANTIDAD|
| :---: | :---: | :---: | :---: |
| TUSB3410		  | TQFP-32   | 	U1		 | 	  x 1	|
| LP38693MP-3.3   | SOT223-5  | 	REG1	 | 	  x 1	|
| Cristal 12 MHz  | THRU HOLE | 	Y1		 | 	  x 1	|
| Diodo 1N4xxx    | SMD 1206  | 	D1		 | 	  x 1	|
| LED             | SMD 1206  | 	C5		 | 	  x 1	|
| Capacitor 4.7uF | THRU HOLE |  C1,C2,C5	 | 	  x 3	|
| Capacitor 33pF  | SMD 1206  |  C3,C4	     | 	  x 2	|
| Capacitor 10nF  | SMD 1206  |  C6,C7	     | 	  x 2	|
| Resistencia 47k | SMD 1206  |  R1,R3		 | 	  x 2	|
| Resistencia 1.5k| SMD 1206  |     R2		 | 	  x 1	|
| Resistencia 10k | SMD 1206  |     R4		 | 	  x 1	|
| Resistencia 12k | SMD 1206  |     R5		 | 	  x 1	|
| Resistencia 15k | SMD 1206  |     R6		 | 	  x 1	|
| Resistencia 32k | SMD 1206  |     R7		 | 	  x 1	|
| Resistencia 220 | SMD 1206  |     R8		 | 	  x 1	|
| Resistencia 33  | SMD 1206  |  R10, R11	 | 	  x 2	|

### Armado

Pueden guiarse por las siguientes fotos para realizar el armado:

<img src="/img/proy/P013/013_1.jpg" width="600" height="300">
<img src="/img/proy/P013/013_2.jpg" width="600" height="300">

### Comentarios

 - Alinear con cuidado cada capa del circuito la momento de realizar la placa.

 - Deben soldarse cablecitos para las vías. Tener en cuenta antes de soldar los componentes.

 - Ver las limitaciones de potencia del regulador REG1 en su hoja de datos!!

 - Este conversor puede suplantar a los módulos "ftdi" que son conversores USB-UART.
