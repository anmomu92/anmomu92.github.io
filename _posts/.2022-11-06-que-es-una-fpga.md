---
layout: single
toc: true
title: "¿Qué es una FPGA?"
---

Esta es la primera entrada de la que espero que sea una colección de entradas dedicadas a las FPGAs y el diseño digital. Aquí, se va a explicar qué es una FPGA, de dónde vienen, y para qué sirve.

## Qué es una FPGA
Una *Field Programmable Gate Array* o *FPGA* es un dispositivo lógico programable. Consta de una serie de componentes que le confieren su capacidad reprogramable, que son los siguientes [1]:
<ul>
<li>Celdas lógicas programables: también llamadas bloques lógicos (logic blocks) o bloques lógicos configurables (configurable logic blocks o CLB). Estos bloques son los que llevan a cabo la lógica del dispositivo.</li>
<li>Red de interconexión programable: conecta los diferentes CLB entre sí.</li>
<li>Celdas de entrada y salida: se encuentran bordeando el dispositivo.</li>
</ul>

La arquitectura más común en la que se organizan estos elemenots dentro de una FPGA es en la denominada *insular* (*island-style*), en la que los bloques lógicos se disponen en una formación tridimensional, dando la sensación de que son islas rodeadas por la red de interconexión.

<figure>
<img src="/assets/images/20221106/fpga.svg"
    alt="estructura FPGA">
<figcaption>Figura 1. Estructura insular genérica de una FPGA. Los bloques lógicos programables se organizan matricialmente asemejando un archipiélago simétrico.</figcaption>
</figure>

Estos tres componentes son programables, dando a las FPGAs la flexibilidad necesaria. Su reconfigurabilidad dependerá de la tecnología utilizada:

<ul>
<li>Vecino más cercano: en este estilo de comunicación los diferenes bloques lógicos están conectados directamente con sus vecinos inmediatos. Aunque es un estilo que puede estar presente en FPGAs, no es el más utilizado y, cuando se utiliza, lo hace acompañado de otros estilos.</li>
<li>Segmentada</li>
<li></li>
</ul>

### Celdas lógicas reprogramables
El núcleo de estos bloques es la *Tabla de búsqueda* (*Lookup Table* o *LUT*), que son pequeños circuitos electrónicos que implementan tablas de verdad. La tabla de búsqueda puede estar conformada por un multiplexor N:1 y una memoria de N bits. The esta manera, con las tablas de búsqueda se pueden implementar las tablas de verdad resultantes de una función lógica dada. Dentro de cada bloque lógico suelen haber varias de estas tablas. El número concreto depende de la arquitectura del modelo de FPGA. El bloque lógico dispone de otro elemento, en este caso de memoria: el *D flip-flop*, que almacena el resultado obtenido de la tabla de búsqueda [2].

### Red de interconexión
Dependiendo de la red, existen diferentes estilos de interconexión que podemos encontrar en la misma:

<ul>
<li>Vecino más cercano: en este estilo de comunicación los diferenes bloques lógicos están conectados directamente con sus vecinos inmediatos. Aunque es un estilo que puede estar presente en FPGAs, no es el más utilizado y, cuando se utiliza, lo hace acompañado de otros estilos.

<figure>
<img src="/assets/images/20221106/vecino.svg"
    alt="vecino-cercano">
<figcaption>Figura 2. En vecino más cercano los bloques lógicos configurables se conectan directamente.</figcaption>
</figure>

</li>
<li>Segmentado: en este estilo de interconnexión existen un bloque de conexión y un bloque de conmutación (switch block). Los bloques de conexión se sitúan al lado de los diferentes bloques lógicos, conectando sus E/S. El bloque de conmutación recibe los datos provenientes de los bloques de conexión y los conmuta hacia su destino. </li>

<figure>
<img src="/assets/images/20221106/segmentado.svg"
    alt="segmentado">
<figcaption>Figura 3. En el estilo segmentado los bloques lógicos se conectan de manera indirecta, a traves de pequeños conmutadores.</figcaption>
</figure>

<li>Jerárquico: en este caso, la matriz de bloques lógicos se divide en sub-bloques más pequeños, de manera que los sub-bloques de tamaño 2x2 siguen el estilo de conexión de Vecino más cercano, mientras que subloques de tamaño más grande siguen estilo segmentado.</li>

<figure>
<img src="/assets/images/20221106/jerárquico.svg"
    alt="jerárquico">
<figcaption>Figura 4. En el estilo jerárquico se los sub-bloques 2x2 se conectan directamente y los sub-bloques mayores no.</figcaption>
</figure>
</ul>



<ul>
    <li>
</ul>

<figure>
    <img src="/assets/images/top-gun-maverick/tom-cruise-moto.png"
         alt="Tom Cruise en la moto">
    <figcaption>Tom Cuise feliz en la moto consciente de que Top Gun Macerick va a ser la pera.</figcaption>
</figure>

## Efectos especiales

<figure>
    <img src="/assets/images/top-gun-maverick/tom-cruise-avion.jpg"
         alt="Tom Cruise en el avión">
    <figcaption>Tom Cruise apunto de despegar hacia un nuevo éxito.</figcaption>
</figure>

## Banda sonora y efectos de sonido

## Conclusiones

