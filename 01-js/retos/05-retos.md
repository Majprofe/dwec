# Desarrollo Web en Entorno Cliente - UD05: Ajax. Promesas. SPA - Retos

## Reto 1: Mostrar información en una tabla
1. Utiliza la API pública [REST Countries](https://restcountries.com/) para obtener una lista de países.
2. Muestra en una tabla HTML la siguiente información de cada país:
   - Nombre
   - Capital
   - Región
   - Población
3. Añade un campo de búsqueda (input) que permita filtrar la lista de países por nombre.

### **API endpoint a consumir**
```
https://restcountries.com/v3.1/all?fields=name,capital,region,population
```

### **Requisitos**
- Estiliza la tabla usando CSS.
- Permite al usuario buscar por nombre de país y actualiza la tabla dinámicamente.

---

## Reto 2: Galería de Películas

### **Objetivo**  
Consumir la API de [OMDB](https://www.omdbapi.com/) mostrar las películas del año actual.

### **Descripción**
1. Usa la API de OMDB para obtener:
   - La lista de películas de este año.
2. Muestra las películas en tarjetas que incluyan:
   - Imagen de la película.
   - Título.
   - Fecha de estreno.

### **API endpoints**
- Obtener películas del año 2024:
  ```
  https://www.omdbapi.com/?s=movie&y=2024&page=${page}&apikey=${apiKey}
  ```

### **Requisitos**
- Implementa CSS avanzado para estilizar las tarjetas (incluye sombras, efectos de hover, etc.).
- Gestiona los errores en caso de que la API falle.

### **Mejoras**
- Realizar un buscador para filtrar películas por el título.

---

## Reto 3: Star Wars

## Objetivo

El objetivo de esta prueba es evaluar tus habilidades en JavaScript, especialmente en el manejo de peticiones a APIs, manipulación del DOM y manejo de eventos. Deberás crear una aplicación web que haga una llamada a la API de Star Wars para obtener y mostrar información en función de los datos proporcionados por el usuario.

---

## Reto3 A: Búsqueda de un personaje por ID

### Instrucciones

1. **Tecnologías**: Utiliza HTML, CSS y JavaScript para crear la aplicación web.
2. **API**: Realiza una llamada GET a la API de Star Wars ([https://www.swapi.tech/api/people/{id}/](https://www.swapi.tech/api/people/{id}/)), donde `{id}` es el ID del personaje ingresado por el usuario.
3. **Formulario**: Crea un formulario con los siguientes elementos:
   - Un campo de entrada obligatorio para el ID del personaje (1 o 2 dígitos).
   - Un botón de envío.
   - Muestra un mensaje de error a la derecha del campo si:
     - Está vacío.
     - No cumple con la expresión regular especificada.
4. **Visualización**: Al enviar el formulario, muestra la información del personaje en el DOM:
   - Nombre
   - Altura
   - Masa
   - Género
5. **Manejo de errores**:
   - Respuestas no exitosas de la API.
   - Problemas de conexión.
6. **Diseño**: Diseña una interfaz limpia y legible utilizando CSS.
7. **Comentarios**: Incluye comentarios en tu código explicando tus decisiones.

---

## Reto 3 B: Exploración de múltiples datos

### Ampliación

Con los siguientes endpoints de la API:

- **Personajes (People)**
  - Obtener todos los personajes: `https://www.swapi.tech/api/people/`
  - Obtener un personaje específico: `https://www.swapi.tech/api/people/{id}/`
- **Películas (Films)**
  - Obtener todas las películas: `https://www.swapi.tech/api/films/`
  - Obtener una película específica: `https://www.swapi.tech/api/films/{id}/`
- **Planetas (Planets)**
  - Obtener todos los planetas: `https://www.swapi.tech/api/planets/`
  - Obtener un planeta específico: `https://www.swapi.tech/api/planets/{id}/`
- **Naves (Starships)**
  - Obtener todas las naves espaciales: `https://www.swapi.tech/api/starships/`
  - Obtener una nave específica: `https://www.swapi.tech/api/starships/{id}/`
- **Especies (Species)**
  - Obtener todas las especies: `https://www.swapi.tech/api/species/`
  - Obtener una especie específica: `https://www.swapi.tech/api/species/{id}/`

### Instrucciones

1. **Formulario avanzado**: Diseña un formulario con dos campos:
   - **Tipo**: Un campo obligatorio que permite seleccionar uno de los tipos de datos proporcionados por la API (personajes, películas, planetas, etc.). Realiza validaciones para evitar datos incorrectos.
   - **ID**: Un campo opcional para ingresar el ID del tipo seleccionado.
2. **Visualización de datos**:
   - Si el ID está presente, muestra los datos relevantes del elemento en formato de tarjeta.
   - Si el ID está vacío, muestra todos los elementos del tipo seleccionado, también en formato de tarjeta.
3. **Interactividad**: Añade un efecto de `hover` en las tarjetas para mejorar la experiencia del usuario.

---
