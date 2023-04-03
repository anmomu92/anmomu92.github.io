---
layout: single
toc: true
title: "Tejidos de un conmutador"
---

En esta entrada se van a explicar los diferentes tejidos de los que pueden estar compuestos los conmutadores. *Tejido*, en este contexto, es una traducción personal del término inglés *fabric*. Como no he encontrado si existe una traducción oficial del término, he decidido utilizar la acepción que creo más se ajusta al concepto que pretende representar. Y es que un tejido es la forma/tecnología por la cual los puertos de entrada y salida dentro de un conmutador se conectan entre sí.

## Qué es una FPGA
Una *Field Programmable Gate Array* o *FPGA* es un dispositivo lógico programable. Consta de una serie de componentes que le confieren su capacidad reprogramable, que son los siguientes [1]:
<ul>
	<li>Celdas lógicas programables: también llamadas bloques lógicos (*logic blocks*) o bloques lógicos configurables (*configurable logic blocks o CLB*). Estos bloques son los que llevan a cabo la lógica del dispositivo</li>
	<li>Red de interconexión programable: conecta los diferentes CLB entre sí.</li>
	<li>Celdas de entrada y salida: se encuentran bordeando el dispositivo.</li>
</ul>

Estos tres componentes son programables, dando a las FPGAs la flexibilidad necesaria. Su reconfigurabilidad dependerá de la tecnología utilizada:

<ul>
	<li></li>
</ul>


## Tejido de memoria compartida
En los conmutadores que implementan este tipo de tejido, las entradas están conectadas a las salidas por medio de una memoria central que recibe los datos provenientes de los puertos de entrada y los almacenan hasta que sean recogidos por los puertos de salida para ser enviados fuera del conmutador hacia su destino.

<figure>
    <img src="/assets/images/top-gun-maverick/tom-cruise-moto.png"
         alt="Tom Cruise en la moto">
    <figcaption>Tom Cuise feliz en la moto consciente de que Top Gun Macerick va a ser la pera.</figcaption>
</figure>

## Tejido de anillo compartido

<figure>
    <img src="/assets/images/top-gun-maverick/tom-cruise-avion.jpg"
         alt="Tom Cruise en el avión">
    <figcaption>Tom Cruise apunto de despegar hacia un nuevo éxito.</figcaption>
</figure>

## Banda sonora y efectos de sonido

## Conclusiones

