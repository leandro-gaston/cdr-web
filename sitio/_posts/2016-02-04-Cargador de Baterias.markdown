---
layout: post
title:  "[P009] Cargador de Baterías"
date:   2015-04-14 16:07:05 -0300
descripcion: "Este proyecto consiste en un cargador de baterías de celulares de Li Ion. Se ofrece la posibilidad de cargar una sola batería, o dos en serie."
categoria: Proyecto
permalink: /proyectos/009/

img: "/img/proy/009.jpg"
portada: "/img/proy/portadas/009.jpg"

estado: "Finalizado"

github: ""
facebook: ""
youtube: ""
---

Cargador de baterías de Li-Ion. Este proyecto consiste en un cargador de baterías de celulares de Li Ion. Se ofrece la posibilidad de cargar una sola batería, o dos en serie. El integrado principal es el [BQ2057](http://www.ti.com/lit/ds/symlink/bq2057w.pdf) de la empresa Texas Instruments. Según la necesidad, se tienen dos opciones:

Tener en cuenta lo siguiente:

- Reemplazar R2 por una resistencia de 0 Ohms.
- No colocar los componentes R4, R9 y J3.

##### OPCION A

Se necesita un cargador de baterías de 3.7V. El integrado a utilizar es el BQ2057T.

##### OPCION B

Se necesita un cargador de baterías de 7.4V (dos celdas en serie). El integrado a utilizar es el BQ2057W. 

### Funcionamiento

Al conectar una batería descargada, se enciende el LED indicando que comenzó la carga. Una vez concluída la carga, el LED se apaga.

### Archivos

- Circuito (imprimir a escala): [PDF](https://dl.dropboxusercontent.com/s/czv74wesm65a9qx/pcb_proy_09.pdf?dl=0)
- Esquemático: [PDF](https://dl.dropboxusercontent.com/s/uc3gd97zxx81g1k/esq_proy_09.PDF?dl=0)

#### Lista de componentes:

- ***x1*** BQ2057 x 1
- ***x2*** Resistencia SMD 1206 0
- ***x2*** Resistencia SMD 1206 1k
- ***x1*** Resistencia SMD 1206 2.2k
- ***x2*** Resistencia SMD 1206 10k
- ***x2*** Capacitor cerámico 100nF
- ***x1*** LED de 5mm
- ***x1*** Resistencia Trough hole 0.47
- ***x1*** Transistor PNP BD136

#### Notas:

- Guiarse con el esquemático y las fotos del álbum para el armado. R1 colocarla de manera vertical.

- En caso de querer aumentar la corriente de carga, se puede poblar también a R8 que es igual que R1 (pasaría de 200 a 400 mA).

Para más información o para pedir muestras del BQ2057 puede visitarse el siguiente [link](http://www.ti.com/product/bq2057).

