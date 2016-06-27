---
layout: post
title:  "[P001] Seguidor de Líneas"
date:   2013-08-15 16:07:05 -0300
descripcion: "Este robot sigue el trayecto marcado por una línea blanca sobre una superficie negra. Es un proyecto básico que facilita el aprendizaje de diversos conceptos fundamentales en la robótica."

categoria: Proyecto
permalink: /proyectos/001/
estado: "En optimización"

img: "/img/proy/001.jpg"
portada: "/img/proy/portadas/001.jpg"

github: ""
facebook: "https://www.facebook.com/media/set/?set=a.155479941316314.1073741832.141209272743381"
youtube: ""
---

Robot seguidor de líneas. Consiste en un Arduino UNO, un shield de potencia y polarización de sensores, una placa de sensores reflexivos y un par de motores de continua.
Este proyecto se compone de dos partes:

   1. ***Shield de potencia***: Permite controlar un par de motores de continua con el Arduino.
   
   2. ***Placa de sensores reflectivos***: Permiten que el Arduino identifique cuando se encuentra sobre la línea a seguir.



### Archivos

- Informe del proyecto. [PDF](https://www.dropbox.com/s/54yotg53a4hdbr8/informe_proy_01.pdf?dl=1)

- Circuito shield de potencia (imprimir a escala):
Este shield cuenta con dos capas, por lo que fabricarlo es un poco más difícil que en el caso de la placa de pruebas para Arduino que sólo tenía una capa. Aquí los links: [Capa TOP](https://www.dropbox.com/s/7wt9kfpnbdp446b/pcb_top_proy_01.pdf?dl=1) | [Capa BOTTOM](https://www.dropbox.com/s/w3qnkszjikpjx8b/pcb_bottom_proy_01.pdf?dl=1)

- Esquemático del shield ESQUEMATICO. [PDF](https://www.dropbox.com/s/bamt6iahl51myop/esq_shield_proy_01.pdf?dl=1)

- Proyecto de Eagle del shield: Aquí está el proyecto completo en Eagle para los que deseen ver más en detalle o quieran realizar modificaciones. [ZIP](https://www.dropbox.com/s/uhzk6drn5xy4t5y/shield_potencia_eagle_proy_01.zip?dl=1)

- Circuito placa de sensores (imprimir a escala): Esta placa contempla tres sensores CNY70. [PDF](https://www.dropbox.com/s/uwkenodcp9lsegr/pcb_sensores_proy_01.pdf?dl=1)

- Esquemático de la placa de sensores. [PDF](https://www.dropbox.com/s/4tri1llx4i6mr6c/esq_sensores_proy_01.pdf?dl=1)

- Proyecto de Eagle placa de sensores: Aquí está el proyecto completo en Eagle para los que deseen ver más en detalle o quieran realizar modificaciones. [ZIP](https://www.dropbox.com/s/g5yregc44s37h4h/tres_sensores_eagle_proy_01.zip?dl=1)

#### Notas:

- Al final del informe, está la lista de componentes del shield.

- Para el armado, puede seguirse las fotos de la placa en 3D que se encuentran en el informe y en el esquemático que también se adjunta.

- Los precios colocados en los componentes al final del informe están desactualizados, por lo que no se los debe tomar como referencia.

- Para el soldado, debe tenerse especial cuidado en soldar de ambos lados de la placa todos los pines de la misma. Esto es para conectar ambas caras del circuito, lo cual es necesario para que funcione correctamente el shield.
