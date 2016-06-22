---
layout: post					        # Lo que siga a un hash es un comentario
title:  "[P012] Elevador Discreto"	    # Obligatorio.
date:   21/06/2016 15:07:00 -0300		# Obligatorio. Creo que la hora y zona no, pero bue...

descripcion: "Primera versión de un elevador DC-DC para el club utilizando componentes discretos. El objetivo del elevador es proveer una tensión de DC mayor a otra que en general provee de una batería. Esto es para no tener que agregar en un robot baterías en serie, lo que agrega peso y es incómodo para cargarlas."	# Obligatorio.

categoria: Proyecto					# Obligatorio. Como está.
permalink: /proyectos/012/			# Obligatorio. XXX = Num del Proyecto
estado: "En optimización"			# Obligatorio. "Finalizado" o lo que quieran. 

img: "/img/proy/012.jpg"			  # Obligatorio. XXX = Num del Proyecto
portada: "/img/proy/portadas/012.jpg" # Obligatorio. XXX = Num del Proyecto

github: "https://github.com/ClubDeRobotica-UNLP/P012_ElevadorDiscreto"
facebook: "https://www.facebook.com/cdrunlp/photos/?tab=album&album_id=515497131981258"
youtube: ""					# Opcional. Direccion a la playlist de YouTube.

---


Primera versión de un elevador DC-DC para el club utilizando componentes discretos.  



### Presentación

Luego de búsqueda de componentes para realizar el elevador, se eligió el LM2577. Link hoja de datos:[link](http://www.ti.com.cn/cn/lit/ds/symlink/lm2577.pdf).  
Sólo son necesarios unos pocos componentes: Capacitores, resistencias, un Diodo shotky y un inductor.

### Implementación

El elevador se implementó en una pequeña placa de 3cm x 2.8 cm. Doble capa.  
Fue diseñado con el mismo footprint que el módulo elevador de texas, el PTN04050CAD. Por lo tanto, es pin compatible con el motivo de intercambiarlos en caso de que sea necesario y usar siempre el mismo footprint. Cabe destacar, que este diseño al ser con componentes discretos es de mayor tamaño que el PTN04050CAD, aunque no por mucho.  
El elevador fue probado con baterías de Ion-Litio de 3.7V logrando tensiones de hasta 9V inclusive. El proyecto de altium se encuentra disponible como así también los componentes con su footprint en la [librería de altium del club](https://www.dropbox.com/sh/wmws3nq52dmwwt4/AAC-t99zivPo3nt4TggKyeRVa?dl=0).


#### Lista de componentes:

| COMP.			  |  ENCAPS.  | ESQUEMATICO  |  CANTIDAD|
|-
| LM2577-ADJ	  | TO220-5	  | 	U1		 | 	  x 1	|
| Inductor 100 UH | THRU HOLE | 	L1		 | 	  x 1	|
| Diodo shotky    | THRU HOLE | 	L1		 | 	  x 1	|
| Resistencia 2.2k| THRU HOLE | 	R2		 | 	  x 1	|
| Capacitor 330nF | LENTEJA	  | 	C5		 | 	  x 1	|
| Capacitor 100nF | SMD 1206  | 	C4		 | 	  x 1	|
| Capacitor>400uF | THRU HOLE | 	C2		 | 	  x 1	|
| Preset 10k      | BOURNE. TH| 	R1		 | 	  x 1	|
| Resistencia 1k  | THRU HOLE | 	R3		 | 	  x 1	|
| Resistencia 1 ohm| THRU HOLE| 	R4		 | 	  x 1	|



### Para realizar la placa

- Circuito (imprimir a escala): [PDF](https://www.dropbox.com/s/lirk5twed956w01/P012_Placa.pdf?dl=0)

- Esquemático: [PDF](https://www.dropbox.com/s/qpsxm90kpokhu8z/P012_Esquematico.pdf?dl=0)

- Proyecto Altium: En git hub! [Link](https://github.com/ClubDeRobotica-UNLP/P012_ElevadorDiscreto).



### Comentarios



 - Deben soldarse cablecitos para las vías. Tener en cuenta antes de soldar los componentes.



 - Ver las limitaciones de potencia del integrado en su hoja de datos!! Puede colocarse un disipador para estirar un poco más el rango de uso.



 - Los capacitores se consiguen fácilmente. Lo más importante es colocar un capacitor considerablemente grande en la tensión de salida, de alrededor de 680 uF.



 - El diodo shotky puede conseguirse en formato SMD, generalmente tamaño 1206 o 3528 de una mother de una PC. Se encuentran cerca de los reguladores de tensión switching de la mother. [Ver foto](http://g01.a.alicdn.com/kf/HTB19wdvIXXXXXXdXXXXq6xXFXXXU/Env&iacute;o-gratuito-One-lote-100-unids-SMA-SS14-1N5819-IN5819-Schottky-diodo.jpg). Si no, puede llegar a comprarse alguno en una tienda de repuestos para fuentes switchings.



 - El inductor, de igual manera puede obtenerse de una mother. Puede ser SMD, en general de tamaño 2020 o más grande. O puede ser thru hole, de distinto footprint aunque son parecidas a [esta foto](http://img.directindustry.com/images_di/photo-m/124023-7954539.jpg).



 - Las resistencias se utilizan para el feedback de tensión. Pueden colocarse dos fijas para tensión fija o una fija y un potenciómetro reemplazando a la segunda.



 - La resistencia R4 se coloca para prevenir sobrecorrientes si se utiliza el elevador para controlar, por ejemplo, motores de continua. El LM2577 posee una protección contra sobrecorrientes que causa que hasta que no se realice un power on no vuelve a funcionar. Para evitar esto, se coloca esta resistencia de 1 Ohm en serie con la salida del elevador.

