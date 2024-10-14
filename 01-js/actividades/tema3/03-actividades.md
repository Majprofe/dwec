# UD03 - Objetos Predefinidos - Actividades

## Actividad 1
Realiza un programa que cada 20 segundos (mediante `setInterval`) solicite un DNI hasta que alguien escriba la cadena `-1`. 
En ese momento, el programa debe mostrar seguidas las letras de todos los DNIs introducidos.

[Cómo calcular la letra de DNI](https://es.wikipedia.org/wiki/Número_de_identificación_fiscal)

## Actividad 2
Realiza un programa que, pasados 20 segundos, nos muestre una sola vez la fecha actual del sistema.

## Actividad 3
Realiza un programa que pregunte una letra de la A a la Z. Tras ello, el programa indicará cuántos DNIs de 3 cifras (del 001 al 999) tienen esa letra y luego mostrará el listado de todos los DNIs que tienen esa letra.

## Actividad 4
Realiza un programa que calcule cuántos números son a la vez primos y palíndromos desde el 1 hasta 100,000. Debe guardar todos ellos en un array y al finalizar el proceso imprimir dicho array.

- [Número primo](https://es.wikipedia.org/wiki/Número_primo)
- [Palíndromo](https://es.wikipedia.org/wiki/Palíndromo)

## Actividad 5
Realiza un programa que reciba una cadena con el siguiente formato:  
`nombre:apellidos:telefono:email:codigopostal`

Debe desglosar y mostrar la siguiente información:
- Código postal
- Apellidos
- Email
- Nombre del servidor asociado al email (ej. `direccion@servidor`)


## Actividad 6
Dispones del siguiente archivo de texto (puedes guardarlo en una variable en JavaScript):

```
Cliente;Localidad;Cuota
Laura;Santander;50
Álvaro;Castro;50
Igor;Castro;60
Ivan;Santander;40
Mónica;Zamora;30
Javi;Bilbao;30
David;Bilbao;50
José Luis;Bilbao;60
```

El usuario podrá elegir entre las siguientes opciones:
1. Todos los usuarios: se mostrará una tabla con los valores que están en la variable anterior.
2. Usuarios de una provincia: se mostrarán los nombres y cuotas de las personas de la provincia introducida.
3. Usuarios con cuota mayor o menor que un valor: se mostrarán los nombres, provincias y cuotas de aquellos que cumplen la condición (valroa cuál es el mejor modo de hacerlo).

**Nota:** Recuerda que para recorrer el array sólop uedes utilizar los métodos avanzados.

---

## Actividad 7
Crea un programa que muestre el número de días que quedan desde hoy hasta el fin del curso (por ejemplo, el 22 de junio).

**Pista:** Recuerda que los meses en JavaScript empiezan desde el número 0.

---

## Actividad 8
Gestiona una lista de países haciendo uso de Arrays. Necesitarás crear un archivo `paises.js` con las siguientes funciones:

- Mostrar el número de elementos del array.
- Mostrar todos los elementos del array.
- Muestra los elementos del array en sentido inverso.
- Muestra los elementos del array ordenados alfabéticamente (sin ordenar el array original).
- Añadir un elemento al principio del array.
- Añadir un elemento al final del array.
- Borrar un elemento al principio del array (y decir cuál se ha borrado).
- Borrar un elemento al final del array (y decir cuál se ha borrado).
- Muestra el elemento que se encuentra en una posición que el usuario indica.
- Muestra la posición en la que se encuentra un elemento que le indica el usuario.
- Muestra los elementos que se encuentran en un intervalo que el usuario indica.

Ten en cuenta que el array será una variable global y que se pasará por parámetro en todas las funciones.

Cuando el usuario cargue la página, se cargará un prompt donde se mostrarán (en el prompt, no en la página) las opciones:
- Mostrar número de países.
- Mostrar listado de países (y le preguntará si quiere mostrarlos en el orden que se encuentran en el array, del revés u ordenados alfabéticamente).
- Mostrar un intervalo de países (y le pedirá que introduzca el intervalo en formato inicio-fin; luego deberás extraer el valor inicio y fin).
- Añadir un país (y le preguntará si quiere añadir al principio o al final).
- Borrar un país (y le preguntará si quiere borrar al principio o al final).
- Consultar un país (y le preguntará si quiere consultar por posición o por nombre).
- Todas las operaciones que se realicen se irán mostrando en la página con su título.

---

## Actividad 9
Queremos programar un juego de dados en un página web. El usuario empieza con 50€ para poder apostar. El usuario decide a que número apuesta del 1 al 6, y también que cantidad de euros quiere apostar. Se “lanza” un dado (asignación al azar de un número del a 1 al 6) Si el usuario acierta el número, gana el doble de lo que ha postado. Si no acierta, pierde todo lo apostado. El juego acaba cuando el usuario llega a 0 euros o al llegar a 200 euros

---

## Actividad 10
Crea una librería con las siguientes entidades:

### Autor
- **Propiedades:**
  - nombre (string)
  - nacionalidad (string)
- **Constructor:** Asigna nombre y nacionalidad.
- **Métodos:** Getters para todas las propiedades.

### Libro
- **Propiedades:**
  - ISBN (número) – Generado automáticamente y único.
  - título (string)
  - autor (Autor)
  - precio (número)
  - género (string)
  - stock (número)
- **Constructor:** Genera un id automático y asigna el resto de propiedades.
- **Métodos:**
  - `tieneStock()`: Devuelve `true` si el stock es mayor que 0, `false` en caso contrario.
  - Getters para todas las propiedades.
  - Setters para modificar el precio y el stock.

### Librería
- **Propiedades:**
  - libros (array de `Libro`), inicializa vacío.
  - ganancias (número), inicializa en 0.
- **Métodos:**
  - `agregar(libro)`: Agrega un libro a la librería, comprobando que su ISBN no se repita.
  - `eliminar(id)`: Elimina el libro con el id especificado.
  - `buscarPorId(id)`: Devuelve la información del libro con el id indicado.
  - `buscarPorTitulo(titulo)`: Devuelve la información del libro con el título indicado.
  - `filtrarPorAutor(autor)`: Devuelve un array de libros escritos por el autor indicado.
  - `filtrarPorGenero(genero)`: Devuelve un array de libros del género indicado.
  - `comprarLibros(idLibros)`: Reduce el stock de los libros comprados y suma el precio a las ganancias.
  - `obtenerGanancias()`: Devuelve las ganancias totales.

**Observaciones:**
- El stock y el precio tienen un valor mínimo de 0.

