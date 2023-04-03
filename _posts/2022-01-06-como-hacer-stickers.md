---
layout: single
toc: true
title: "Cómo hacer stickers con GIMP"
---

En este post voy a enseñaros el procedimiento que sigo yo para hacer stickers con el programa de edición de imágenes [GIMP](https://www.gimp.org/), que es de código abierto y gratuito.

# Crear una nueva imagen

Para crear una nueva imagen basta con ir a la barra de menú y seleccionar `Archivo > Nuevo...` o utilizar el atajo de teclado `Ctrl+n`. Tras esto, aparecerá la ventana de creación de imagen. Esta ventana nos permitirá seleccionar las dimensiones de la nueva imagen. Como el tamaño aceptado por convención para los stickers es de *512x512* (aplicaciones como Telegram o Signal no te dejarán subir imágenes que no cumplan con estas dimensiones), seleccionamos una anchura y una altura de 512 píxeles, como se muestra en la Figura 1.

<figure>
    <img src="/assets/images/20220106/01.PNG"
         alt="Ventana de creación de imagen">
    <figcaption>Figura 1. En la ventana de creación de la imagen, seleccionamos una anchura y una altura de 512 píxeles.</figcaption>
</figure>

Una vez creada la nueva imagen, sólo tendremos una capa de *512x512* con el canal alpha activado. A continuación, tenemos que sobreponer a esta capa la imagen de la cual queremos hacer el sticker. Para ello, basta con arrastrar dicha imagen sobre el fondo (véase Figura 2).

<figure>
    <img src="/assets/images/20220106/02.gif"
         alt="Importación de la imagen">
    <figcaption>Figura 2. Arrastramos al panel principal la imagen de la cual queremos hacer el sticker.</figcaption>
</figure>

Puede que la imagen, como ocurre en este caso, no se ajuste como queramos en el fondo de *512x512*. Por lo tanto, tendremos que escalar la imagen importada para que quepa la parte de la imagen que queremos que aparezca en el sticker. Para ello, tenemos que hacer click derecho en la capa de la imagen (que está en el panel de capas) y seleccionar la opción de `Escalar capa...`. En la Figura 3, se muestra el proceso. Si aún así la zona que nos interesa estuviera fuera del fondo, bastaría con mover la capa de la imagen.

<figure>
    <img src="/assets/images/20220106/03.gif"
         alt="Redimensión de la capa de la imagen">
    <figcaption>Figura 3. Redimensionamos la capa de la imagen para que entre en la capa de Fondo.</figcaption>
</figure>

# Recorte de la imagen

El siguiente paso en la creación de nuestro sticker de Keanu Reeves es el del recorte de la parte de la imagen que nos interese mostrar en el sticker. Para esto, seleccionaremos la herramienta de rutas, que es la que se muestra en la Figura 4. Una vez seleccionada dicha herramienta, tenemos que seleccionar los puntos por los que queremos que pase nuestra ruta. Para cerrar la ruta, el último punto se conecta con el primero haciendo click sobre este mientras pulsamos la tecla `Ctrl`. La Figura 5 muestra cómo se van creando los puntos que formarán parte de la ruta.

<figure>
    <img src="/assets/images/20220106/04.PNG"
         alt="Herramienta de rutas">
    <figcaption>Figura 4. La herramienta de rutas se muestra en el panel de herramientas.</figcaption>
</figure>

<figure>
    <img src="/assets/images/20220106/06.gif"
         alt="Creación de la ruta">
    <figcaption>Figura 5. Seleccionamos los puntos de la ruta con click izquierdo.</figcaption>
</figure>

Una vez cerrada la ruta, basta con pulsar `Enter` para añadirla a la selección. El resultado se muestra en la Figura 6.

<figure>
    <img src="/assets/images/20220106/05.PNG"
         alt="Ruta añadida a la selección">
    <figcaption>Figura 6. La selección se muestra como una línea discontinua.</figcaption>
</figure>

Ahora toca eliminar la parte sobrante. El primer paso es invertir la selección. Esto se puede hacer desde la barra de menú en `Seleccionar > Invertir` o mediante el atajo de teclado `Ctrl+i`. Tras esto, tenemos que añadir el canal alfa a la capa de la imagen. Esto se añade haciendo click derecho sobre la capa de la imagen y seleccionando `Añadir canal alfa`. Una vez hecho esto, pulsamos la tecla `Supr` para eliminar la parte de la imagen que no nos interesa. Por último, tenemos que reinvertir la selección con `Ctrl+i`. El resultado debe ser algo parecido a lo mostrado en la Figura 7.

<figure>
    <img src="/assets/images/20220106/07.gif"
         alt="Recorte del sticker">
    <figcaption>Figura 7. Es muy importante añadir el canal alfa a la capa de la imagen.</figcaption>
</figure>

# Añadiendo el perfil

El siguiente paso es añadir el perfil blanco al sticker. Para esto, tenemos que mantener la selección del paso previo y seleccionar en la barra de menú `Seleccionar > Agrandar...`. Para sticker de carne y hueso, es mejor agrandar poco la selección (en mi caso, suelo elegir 3px), mientras que para dibujos, un poco más de agrandamiento no queda mal. Una vez que veamos que la selección es más grande, seleccionamos la capa de fondo y rellenamos la selección de blanco haciendo click en la barra de menú en `Editar > Rellenar con el color de primer plano` (si el color de primer plano no es blanco, cambiadlo). El proceso se muestra en la Figura 8.

<figure>
    <img src="/assets/images/20220106/08.gif"
         alt="Añadiendo el perfil">
    <figcaption>Figura 8. Para caricaturas se puede agrandar un poco más la selección.</figcaption>
</figure>

# Proyectando la sombra

Para que resulte más estético, podemos proyectar una sombra para darle una sensación de entidad propia al sticker. Esto se lleva a cabo seleccionando en la barra de menú la opción `Filtros > Luz y sombra > Sombra arrojada (heredado)...`. Los valores concretos, siempre que no sean muy extremos, no importan demasiado. Jugando con ellos podemos dar la sensación de que el sticker está más o menos lejos del fondo del chat (y si el fondo es oscuro, ni se verá la sombra). Lo que es muy importante es desactivar el redimensionado (véase la Figura 9), ya que de lo contrario el sticker no cumplirá las dimensiones exigidas y no se podrá subir a aplicaciones como Telegram o Signal. El proceso completo de sombreado se muestra en la Figura 10.

<figure>
    <img src="/assets/images/20220106/10.PNG"
         alt="Ventana de sombra arrojada">
    <figcaption>Figura 9. Es muy importante desmarcar el redimensionado durante el sombreado.</figcaption>
</figure>

<figure>
    <img src="/assets/images/20220106/09.gif"
         alt="Sombreado del sticker">
    <figcaption>Figura 10. La sombra otorga más entidad al sticker.</figcaption>
</figure>
