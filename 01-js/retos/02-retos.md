## UD02. Sintaxis del Lenguaje JavaScript - Retos

### 1. `u1e1_integracioncodigo.html`

Crea un programa en JavaScript donde integres código en el `<head>`, en el `<body>` y en un archivo externo. Cada código contendrá un mensaje emergente de modo que:
- El primer mensaje muestre el nombre de la localidad más grande de Asturias.
- El segundo mensaje muestre el nombre de la segunda localidad más grande de Asturias.
- El tercer mensaje muestre el nombre de la tercera localidad más grande de Asturias.

### 2. `u1e2_comentarios.html`

En el siguiente código deberás corregir los errores y comentarlo una vez que analices qué realiza el programa:

```html
<!DOCTYPE HTML>
<html>
<head>
  <title></title>
</head>
<body>
  <script>
    y = prompt('INTRODUZCA NÚMERO');
    y = parseInt(y);
    for (var x = ; x <= 10; x++); {
      r = y * x;
      document.write(y + "x" + x + "=" + r + "<br>");
    }
  </script>
</body>
</html>

```
### 3. `u1e3_esfera.html`
Utilizando los operadores que has visto hasta ahora, desarrolla un programa que permita calcular el volumen de una esfera dado un radio almacenado en una variable. Realiza también las mismas operaciones utilizando una sola línea de código.

### 4. `u1e4_operadores.html`
A partir del siguiente código, sustituye las almohadillas (#) por operadores de comparación o lógicos para que las sentencias den verdadero o falso según se indique en cada línea.

```html
<html>
<head>
  <script type="text/javascript">
    function mostrarMensaje() {
      var a, b, c, d, eTexto;
      a = 3;
      b = 5;
      c = true;
      d = false;
      eTexto = '1';
      alert('VERDADERO' + (a+b # 8 && a-b # 1));
      alert('FALSO: ' + (a+b == 8 # a-b ==-2));
      alert('VERDADERO: ' + (c # d));
      alert('FALSO: ' + (c # d));
      alert('FALSO: ' + (#a));
      alert('FALSO: ' + (eTexto # 1));
      alert('FALSO: ' + (eTexto # 1 # eTexto != "Zapato"));
      alert('VERDADERO: ' + ('Zapato' # 'avellano'));
    }
    mostrarMensaje();
  </script>
</head>
<body>
</body>
</html>
```
### 5. `u1e5_geometría.html`
Crea un archivo en JavaScript que contenga únicamente fórmulas (con los parámetros necesarios) para calcular los siguientes valores de cuerpos geométricos:

Área del triángulo
Perímetro del triángulo equilátero, isósceles y escaleno
Área y perímetro de un cuadrado
Área y perímetro de un rectángulo
Área del círculo y longitud de la circunferencia
Crea un archivo HTML que cree las variables necesarias (base, altura, lado1, lado2, lado3 y radio) y llame a todas las funciones declaradas en el archivo anterior.

### 6. `u1e6_funcionesanonimas.html`

Modifica el último programa realizado de modo que todas las funciones sean creadas y llamadas en el HTML:

- Las funciones relacionadas con el triángulo deben ser definidas e invocadas como funciones anónimas.
- Las funciones relacionadas con paralelogramos deben ser definidas e invocadas con el constructor `function`.
- Las funciones del círculo y la circunferencia deben ser funciones anónimas autoinvocadas.

### 7. `u1e7_funcionesvariables.html`

Modifica el código de `u1e5` y crea una nueva función que se llame `perimetroTriangulo`. Si recibe un solo parámetro, mostrará su valor e invocará a la función del perímetro del triángulo equilátero; si recibe dos parámetros, mostrará sus valores e invocará a la función del triángulo isósceles; si recibe tres, al del triángulo escaleno.

Crea otra función llamada `perimetroParalelogramo`. Si recibe un parámetro invocará a la función del perímetro del cuadrado; si no, a la del rectángulo.

**Reto adicional**: Crea una función llamada `areaPoligono` para calcular el área según el número de lados.

### 8. `u1e8_condicionales.html`

Diseña un juego que permita adivinar qué tipo de malware está pensando un usuario a partir de 3 preguntas de sí o no. Ejemplos de malware:

- **Gusano**: Se puede borrar con antivirus y se multiplica.
- **Bug**: No se puede borrar con antivirus; se soluciona con una actualización.
- **Troyano**: Se puede borrar con antivirus y no se multiplica.
- **Spam**: No se puede borrar con antivirus ni con actualizaciones del sistema.
- **Exploit**: No se puede borrar con antivirus; se soluciona con una actualización.

### 9. `u1e9_buclesFor.html`

Crea un programa que permita mostrar por pantalla las horas del día desde las 08:00 hasta las 20:30 en intervalos de 30 minutos. Las horas y minutos deben ser de dos dígitos (08:30, 14:00).

### 10. `u1e10_buclesForIn.html`

Un equipo de baloncesto tiene una lista de jugadores. Muestra la lista de los jugadores y su dorsal, comenzando por el número 3 y sumando de 3 en 3 (3, 6, 9...).

**Reto adicional**: Hazlo de tres modos diferentes.

### 11. `u1e11_bucles.html`

Crea una función que permita mostrar un control parental que impida entrar a la página hasta que el usuario introduzca la respuesta correcta.

- Pregunta: "¿Cuál fue el primer presidente de la democracia española?".
- Si la respuesta es incorrecta, muestra mensajes de error.

### 12. `u1e12_breakContinue.html`

Crea una función que muestre los números del 1 al 100 excepto los múltiplos de 3. 

Crea otra función que muestre una lista con los meses del año excepto los meses de verano.

**Reto adicional**: Realiza ambas funciones de dos maneras diferentes.

### 13 `intervalo15.js`
Crea un programa que muestre por consola todas las horas que van desde las 15:00 a las 17:00 de 15 en 15 minutos (ej. 15:00, 15:15, 15:30, 15:45, 16:00, 16:15, 16:30, 16:45, 17:00).

### 14 `intervaloalacarta.html`
Vamos a mejorar el ejercicio anterior creando un programa que pida al usuario:
- la hora de inicio (ej. 15:00)
- la hora de finalización (ej. 17:00)
- el intervalo de minutos (sólo el número, ej. 15)

Y muestre por consola todas las horas que van desde la hora de inicio a la de finalización de X en X minutos (ej. 15:00, 15:15, 15:30, 15:45, 16:00, 16:15, 16:30, 16:45, 17:00).

Debes controlar:
- las horas de inicio y fialización deben ser una hora válida (la hora un número entero entre 0 y 24 y los minutos un número entero entre 0 y 59, ambos separados por el carácter ":")
- el intervalo de minutos deben ser un número entero mayor que 0
- si un valor introducido no es correcto se muestra al usuario un mensaje informando del error (un alert) y se le vuelve a pedir el valor
- en la consola las horas y los minutos se deben mostrar siempre con 2 números (09:03 y no 9:3)

### 15 `contraseña.html`
Crea un programa que pida al usuario que introduzca una contraseña y compruebe si es o no segura. Para ello comprobará:
- que su longitud sea mayor o igual de 8 caracteres
- que contiene alguna mayúscula
- que contiene alguna minúscula
- que contiene algún número
- que contiene alguno de estos caracteres: guión, barra baja, igual, asterisco, mas, dólar, arroba o almohadilla

Si cumple todos los requisitos se informará por consola que la contraseña introducida es segura. Si no cumple 1 o 2 se le dirá que es poco segura y si no cumple más de 2 se le dirá que es una contraseña débil.

### 16. `u1efinal_trivial.html`

Crea un juego de Trivial donde el jugador debe responder 6 preguntas de distintas categorías. El juego termina cuando el jugador acierta 4 preguntas o falla 3.
