# UD03. Objetos nativos, objetos, clases, BOM - Retos

## Ejercicio 1: u3e1_string.html (Parte 1)
Diseña un programa que solicite a un usuario en una sola petición su nombre, dos apellidos y año de nacimiento (por ejemplo: «Pepe Perez Sanchez 1990»). El nombre y los apellidos serán una única palabra cada uno, pero no hace falta que lo valides. No habrá nombres compuestos como "Juan Tomás" o "San Salvador". Sobre ese nombre, deberá mostrar la siguiente información para crear un nombre de usuario:
- Transformación de la cadena a todos mayúsculas.
- Muestra de nombre, primer apellido, segundo apellido y año, cada uno en una línea.
- Nombre de usuario: estará formado por la inicial del nombre, el primer apellido, la inicial del segundo apellido y las dos últimas cifras del año de nacimiento, todo en minúsculas (ej. pperezs90).

## Ejercicio 2: u3e1_string.html (Parte 2)
Diseña un programa que solicite a un usuario en una sola petición su nombre, dos apellidos y año de nacimiento. Sobre ese nombre, deberá mostrar la siguiente información:
- Tamaño de la cadena que contiene únicamente nombre y dos apellidos.
- Continuará…

## Ejercicio 3: u3e1_string.html (Parte 3)
Diseña un programa que solicite a un usuario en una sola petición su nombre, dos apellidos y año de nacimiento. Sobre ese nombre, deberá mostrar la siguiente información:
- Número de vocales que contiene la cadena de nombre y apellidos.
- Continuará…

## Ejercicio 4: u3e2_number.html
Crea un conversor de bases que solicite al usuario en qué base está el número que va a introducir (binario, decimal, octal, hexadecimal) y muestre el número en las 4 bases. Trata de hacerlo de la manera más optimizada posible.

## Ejercicio 5: u3e3_math.html
Realiza un programa que permita elegir al usuario un tipo de lotería del estado y genere los números aleatorios en la propia página (no en un alert). Se mostrarán los siguientes tipos de loterías:
- Lotería Nacional (los ceros a la izquierda deben mostrarse).
- Quiniela.
- Primitiva (con complementario y reintegro).

## Ejercicio 6: u3e4_date1.html
Realiza un programa que sea capaz de calcular cuántas veces cae en sábado el solsticio de verano desde el año 2000 hasta el año 2100.

## Ejercicio 7: u3e4_date2.html
Realiza un archivo en JavaScript con tres funciones que te permitan realizar los siguientes formatos de fecha, recibiendo como parámetro la fecha en milisegundos o en números (usa `arguments` para saber el número de parámetros que ha introducido el usuario):
- Fecha en formato corto: 17/02/2016.
- Fecha en formato largo: Miércoles, 17 de febrero de 2016.
- Fecha en formato inglés: Wednesday, February 17, 2016.

## Ejercicio 8: u3e4_date3.html
Completa el archivo con dos funciones más que te permitan mostrar la hora en los siguientes formatos:
- Hora en formato corto: 14:30.
- Hora en formato largo: 14:30:25.
- Hora con PM/AM: 02:30 AM si es antes de mediodía, o 02:30 PM si es después de mediodía. No se utilizan horas mayores que 12 ni menores que 1 (no existe 00:30).

## Ejercicio 9: u3e5_window.html
Realiza un programa con una ventana principal y tres botones:
- **Abrir**: abrirá una pequeña ventana pop-up sin barras, scroll y no permitirá redimensionarse.
- **Cerrar**: cerrará la ventana creada.
- **Imprimir**: permitirá imprimir la ventana principal.

En la ventana secundaria (pop-up) habrá:
- 6 botones con nombres de colores que, al pulsarse, imprimirán en la pantalla principal un párrafo con el color indicado.
- Un botón para cerrar la ventana.
- Un botón para mover la ventana a una posición indicada por el usuario (se solicitarán dos valores separados por coma para la posición desde arriba y desde la izquierda).

## Ejercicio 10: u3e6_windowtiempo.html
Crea un reloj con cronómetro en JavaScript. El cronómetro tendrá:
- Un botón para poner a 0 el contador.
- Un botón para arrancar el cronómetro.
- Un botón para parar el cronómetro.
- Un botón para escribir el valor del cronómetro parado en la página.

## Ejercicio 11: u3e7_objetos.html
Crea tres objetos que almacenen información de sandkills:
- **sandkill1**: creado como un literal.
- **sandkill2**: creado con la definición `new Object()`.
- **sandkill3**: creado a partir de una clase `Sandkill`.

Los tres objetos tendrán las propiedades: `nombre`, `edad`, `especialidad`, y un método `.mostrar()` que devuelva una cadena con la información en una línea. Posteriormente:
- Añade a `sandkill1` la propiedad `nacionalidad`.
- Añade a `sandkill2` la propiedad `lenguajeFavorito`.
- Elimina de `sandkill3` la propiedad `especialidad`.

Crea una función que muestre todas las propiedades de un objeto `Sandkill` sin usar el método `.mostrar()`.

## Ejercicio 12: u3e8_clases.html
Crea una clase para almacenar información de Sandkills con las siguientes propiedades y métodos:
- **Propiedades**: `nombre`, `edad`, `especialidad` (1: Sistemas, 2: Web, 3: Multiplataforma), y `compañero` (otro objeto de tipo Sandkill).
- **Métodos**:
  - `.mostrar()`: devuelve la información del Sandkill usando los getters.
  - Getters: `.getNombre()`, `.getEdad()`, `.getEspecialidad()`, `.getNombreCompanero()`, `.getCompanero()`.
  - Setters: `.setNombre()`, `.setEdad()`, `.setEspecialidad()`, `.setEspecialidadNombre()`, `.setCompanero()`.

## Ejercicio 13: u3e9_arrays.html
Utilizando la clase `Sandkill` del ejercicio anterior, realiza un programa que permita gestionar un array de sandkills con las siguientes operaciones:
- Insertar un sandkill al principio de la lista.
- Insertar un sandkill al final de la lista.
- Borrar el primer sandkill de la lista.
- Borrar el último sandkill de la lista.
- Mostrar la lista de sandkills.
- Mostrar la lista de sandkills ordenada.
- Buscar un sandkill por su nombre.
- Buscar un sandkill por su posición.

## Ejercicio 14: u3e10_prueba_final_electricidad.html
Diseña un programa que gestione los siguientes datos:
- **Escuela**: nombre, localidad, responsable.
- **Instalación**: tipo (luz exterior, luz interior, enchufes), cantidad, presupuesto.
- **Compañía**: nombre, responsable.

Ten en cuenta que una escuela puede tener varias instalaciones, pero solo una de cada tipo, y cada instalación puede ser realizada por una compañía diferente. Gestiona la inserción, modificación, borrado y visualización de los datos.

## Ejercicio 15: u3e11_prueba_final_hospital.html
Diseña un programa que gestione los siguientes datos:
- **Hospital**: nombre, localidad, responsable.
- **Personal**: nombre, especialidad (médico, enfermera, celador).
- **Paciente**: nombre, personal asignado.

Un hospital puede tener varios pacientes y personal, pero un paciente y un personal solo pertenecen a un hospital. Gestiona la inserción, modificación, borrado y visualización de los datos.

## Ejercicio 16: u3e12_prueba_final_escuela.html
Diseña un programa que gestione los siguientes datos:
- **Escuela**: nombre, localidad, responsable.
- **Profesor**: nombre, tipo (ciencias, letras).
- **Alumno**: nombre, curso, profesor responsable.

Una escuela puede tener varios profesores y alumnos, pero ningún alumno o profesor pertenece a dos escuelas. Gestiona la inserción, modificación, borrado y visualización de los datos.

## Ejercicio 17: u3e13_prueba_final_tanques.html
Diseña un programa que gestione los siguientes datos:
- **Tanque**: número, capacidad, localidad.
- **Localidad**: nombre, número de habitantes, provincia.
- **Habitante**: nombre, edad, localidad.

Cada localidad puede tener varios tanques, pero un habitante solo puede acceder a un tanque. Gestiona la inserción, modificación, borrado y visualización de los datos.

## Ejercicio 18: u3e14_prueba_final_biblioteca.html
Diseña un programa que gestione los siguientes datos:
- **Biblioteca**: nombre, localidad, responsable.
- **Libro**: título, autor, prestado a un socio.
- **Socio**: nombre, biblioteca.

Una biblioteca puede tener varios libros y socios, pero un libro solo puede estar en una biblioteca y prestado a un socio. Gestiona la inserción, modificación, borrado y visualización de los datos.
