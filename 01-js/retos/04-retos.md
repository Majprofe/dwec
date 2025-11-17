# Desarrollo Web en Entorno Cliente - UD04: Eventos, Formularios y Local Storage - Retos

## 1. `u4e1_cartas.html`
Diseña un juego de cartas que contenga, al menos, la siguiente funcionalidad:
- Descripción del juego en la página.
- Contador de puntos.
- Cartas que se dan la vuelta (imágenes que se sustituyen una por otra).
- Cartas que cambian su aspecto (tamaño, bordes, transparencia…).
- Varios manejadores asociados al mismo evento.

Si no se te ocurre ningún juego, puedes hacer un juego de memoria con al menos 4 parejas de cartas dadas la vuelta. El jugador, al pulsar sobre una carta se mostrará su imagen; al pulsar sobre una segunda carta, si son iguales se mantendrán con su imagen mostrada y un reborde; si son diferentes se darán la vuelta tras un segundo.

## 2. `u4e2_formulario.html`
Diseña un formulario con los siguientes campos y valídalos antes de enviarlo:
- **Identificador**: 1 letra, 8 cifras y 1 letra. Obligatorio.
- **Nombre y apellidos**: cadena de 50 caracteres. Obligatorio.
- **Fecha de nacimiento**: campo con formato dd/mm/yyyy. Obligatorio.
- **Correo electrónico**: con formato específico.
- **Teléfono**: formato + y dos o tres cifras seguido de guión y 9 cifras.
- **Edad**: desplegable con opciones niño / adulto / jubilado.
- **Club de ski**: checkbox que activa otros campos adicionales.

Si hay errores, muestra mensajes en rojo junto al campo y marca el borde en rojo. Los mensajes deben persistir si el error continúa tras otro intento.

## 3. `u4e3_expresionesregulares.html`
Crea una web que valide los siguientes códigos para control de producto:
- **Fecha y hora de creación**: formato "dd/mm/aaaa hh:mm".
- **Cocinero**: dos letras mayúsculas, símbolo, y cuatro dígitos (ej. WW$1234).
- **Destinatario**: dos o tres letras mayúsculas, guión bajo, ciudad en minúsculas, dos puntos, y código de distrito de 4 dígitos (ej. NM_alburquerque:1234).
- **Gramos**: número del 1000 al 5000.
- **Composición**: estará formado por una cantidad en gramos seguida de dos conjuntos de una o dos letras seguidas o no de un número. (ej. 200gC3OH7).
- **Número de cuenta de EEUU**: supongamos que un número de cuenta estadounidense tiene el siguiente formato:
1. 	Dos letras: suponemos que el valor de cada letra es del 1 al 26 (no hay ñ ni ll).
2. 	Dos dígitos: debe corresponderse con la suma de la primera letra y la segunda: en caso de que sea menor que 10 se pone el 0 delante.
3. 	Un guión.
4. 	Doce dígitos de cuenta
5. 	Un guión.
6. 	Dos dígitos de control: el primer dígito debe ser la suma de los 6 primeros dígitos de la cuenta dividido entre 6 y extrayendo solamente su parte entera; y el último dígito exactamente igual, pero con los 6 siguientes.
7. 	Si el número está correcto se colocará en un campo de texto al lado del anterior, pero sin guiones: solamente los números y las letras.
Ejemplo: AA02-123400001200-10 


## 4. `u4e4_localStorage.html`
Al formulario que hiciste en el reto u4e2 le falta una pequeña gestión de usuarios registrados diarios para que los de las taquillas lleven el control.
Para ello deberás incluir en la parte superior derecha de la página dos pequeños contadores:
-	El primero contabiliza el número de forfaits registrados ese día. Para ello guarda ese valor en una cookie que expirará a las 23:59:59 de ese mismo día. Por tanto, cada vez que el formulario sea válido, sumará uno al contador. ¡Cuidado con las fechas!
-	El segundo será similar al primero pero solo contabilizará aquellos socios que son del club de ski.
Además, cada contador incluirá a su lado un botón «Resetear» que permitirá ponerlo a 0 en cualquier momento. 

Recuerda que el código html deberá estar separado del código javascript, y que cada archivo javascript debería almacenar funciones que solamente hagan referencia a un tema.


## 5. `u4e5_modificarelementos.html`
Diseña una página informativa que contenga varios personajes. Pueden ser personajes de una serie o película, miembros de un grupo de música, personajes históricos, etc.
Por un lado, dispondrás de un conjunto de imágenes de los personajes, mínimo 8 (puedes alojarlas en una tabla). Por otro lado, tendrás un panel informativo que alojará textos. Y, por último, una serie de botones (mínimo 3).
Al poner el ratón sobre cada una de las imágenes se mostrará información del personaje pulsado en el panel informativo.
Además, al pulsar los botones, permitirá modificar el aspecto de ciertas imágenes que formen parte de una clase determinada y mostrará un texto diferente en el panel. Habrá imágenes que tengan más de una clase. 
Por ejemplo, si decides hacerlo sobre personajes de los Simpson, puedes poner un botón que seleccione los personajes de la Familia Simpson; otro que seleccione los personajes que van al instituto; otro de los personajes que trabajan en la central nuclear… de tal manera que, por ejemplo, Bart es de la familia Simpson y además va al instituto; o Hommer es de la familia Simpson y trabaja en la central nuclear. Recuerda que el código html deberá estar separado del código javascript, y que cada archivo javascript debería almacenar funciones que solamente hagan referencia a un tema.

## 6. `u4e6_crearborrarelementos.html`
Basada en la temática del ejercicio anterior, crea una página en la que, haciendo uso de todo lo aprendido hasta ahora, puedas crear un catálogo de personajes/artículos/etc. a modo de fichas o cartas.
Para ello crearás un pequeño formulario que te permitirá añadir los valores que quieras (al menos un título, una imagen, una url y un pequeño texto), y un botón que, al pulsarlo, generará la ficha o carta y la añadirá a tu página web.

## 7. `u4e7_recorrerElementos.html`
Diseña un analizador de formularios que te permita extraer toda la información de un formulario, independientemente de cómo se encuentre diseñado.

Para ello, crea una página que incluya un formulario cualquiera, un div y un botón. Al pulsar el botón deberá realizar las siguientes acciones:
-	Recorrerá desde el primero al último todos los elementos del formulario, numerándolos.
-	Por cada elemento input que encuentre, indicará, en el div, que se ha encontrado un input, de qué tipo es, qué clase tiene, qué id tiene, qué nombre tiene, y su valor. Por ejemplo: «1. INPUT. Tipo: text. Nombre: usuario. Clase: no tiene. Id: no tiene. Valor: sandiego».
-	Por cada elemento textarea/button que encuentre, indicará, en el div, que se ha encontrado un textarea/un button, su clase, id y nombre, si tiene, y su valor.
-	Por cada label que encuentre, indicará, en el div, que se ha encontrado un label, su clase, id y nombre, si tiene, y su atributo «for».
-	Por cada select, indicará, en el div, que se ha encontrado un select, su clase, id y nombre, si tiene, y cada uno de los valores de los option que contiene.
-	Si hay un elemento de tipo comentario (ver enlace: http://www.w3schools.com/jsref/prop_node_nodetype.asp) mostrará simplemente, que se ha encontrado un elemento de tipo comentario, y su valor.
-	No se tendrán en cuenta elementos de tipo fieldset, datalist, keygen u output.

Por ejemplo: «1. INPUT. Tipo: text. Nombre: usuario. Clase: no tiene. Id: no tiene. Valor: sandiego».

Ten en cuenta que el código que crees debe servir para todos los formularios, independientemente de los elementos que contengan.

