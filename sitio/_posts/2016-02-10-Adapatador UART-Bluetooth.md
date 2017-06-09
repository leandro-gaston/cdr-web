---
layout:	post
title:	"[P008] Adaptador UART-Bluetooth"
date:	2015-02-04 16:07:05 -0300
categoria:	Proyecto
descripcion: "Un adaptador UART-Bluetooth que permite comunicarse con el puerto serie
de un microcontrolador mediante el protocolo inalámbrico bluetooth."

permalink:	"/proyectos/008/"

img: "/img/proy/008.jpg"
portada: "/img/proy/portadas/008.jpg"

estado:	"Finalizado"

github: ""
facebook: "https://www.facebook.com/media/set/?set=a.165337273663914.1073741834.141209272743381"
youtube: ""
---

Se diseñó el circuito para lograr un adaptador UART a Bluetooth, lo que permite un modo práctico de comunicación de un microcontrolador con algún dispositivo BT, ya sea una PC o un celular. El componente principal es el integrado [LMX9838](http://www.ti.com/lit/ds/symlink/lmx9838.pdf) de Texas Instruments. El resto de componentes son resistencias 1206 de 1k y capacitores electrolíticos de 2uF y cerámicos de 10 nF. El LED smd y su resistencia de 220 Ohms 1206 es opcional. El LED es sólo señalizador.

#### Archivos:
- Circuito para imprimir (imprimir a escala): Tener en cuenta que los componenentes deben soldarse del mismo lado que se colocan. Esto se debe a que se utiliza una sola capa en vez de dos para mayor facilidad en la fabricación del circuito. Además, debe soldarse un puente para conectar los pads que no poseen pistas que los unan (ver las fotos del álbum): [PDF](/files/proyectos/008/008_PCB.pdf)

- Esquemático: [PDF](/files/proyectos/008/008_Esquematico.pdf)

#### Lista de componentes:

- ***1x*** LMX9838
- ***4x*** Resistencia SMD 1206 1k
- ***2x*** Capacitor electrolítico 2.2uF
- ***2x*** Capacitor cerámico 10nF
- Un alambre para puentear 3 pads.

#### Notas:

- Conviene colocar los capacitores del otro lado de la placa y doblarles las patas para que queden "apoyados" sobre la placa. Esto es para que sea más compacto el diseño y además facilita el soldado de los capacitores.

- Depende como y dónde se vaya a usar el conversor, quizás convenga poner la tira de pines a 90° en vez de rectos, como se muestra en las figuras en 3D. Ver las fotos del álbum para más detalles.

Para más información o para pedir muestras del LMX9838 puede visitarse el siguiente [link](http://www.ti.com/product/lmx9838).
