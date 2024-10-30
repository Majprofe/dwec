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
- **Composición**: cantidad en gramos y elementos químicos (ej. 200gC3OH7).
- **Número de cuenta de EEUU**: formato con letras, dígitos, guiones, y verificaciones específicas.

## 4. `u4e4_localStorage.html`
Añade al formulario del reto `u4e2` contadores en la esquina superior derecha:
- **Número de forfaits diarios**: usa una cookie que expira a las 23:59:59 de cada día.
- **Número de socios del club de ski**: contador específico para estos usuarios.

Ambos contadores deben incluir un botón "Resetear" para poner el valor a 0.

## 5. `u4e5_modificarelementos.html`
Diseña una página con varios personajes:
- Imágenes de al menos 8 personajes en una tabla.
- Panel informativo con textos y botones para modificar el aspecto de las imágenes y mostrar distintos textos en el panel.
- Los botones deben filtrar imágenes por clases, como personajes de "La familia Simpson" o "trabajadores de la central nuclear".

## 6. `u4e6_crearborrarelementos.html`
Basado en el ejercicio anterior, crea una página con un formulario para añadir fichas de personajes/artículos. Los datos mínimos deben incluir título, imagen, URL y texto, y deben generarse al pulsar un botón.

## 7. `u4e7_recorrerElementos.html`
Diseña un analizador de formularios que extraiga información de cada elemento:
- Numerará cada elemento y mostrará detalles en un `div` para inputs, textareas, botones, labels, selects y comentarios.

El código debe funcionar para formularios con cualquier combinación de elementos.
