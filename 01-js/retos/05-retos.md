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
https://restcountries.com/v3.1/all
```

### **Requisitos**
- Estiliza la tabla usando CSS.
- Permite al usuario buscar por nombre de país y actualiza la tabla dinámicamente.

---

## Reto 2: Galería de Películas

### **Objetivo**  
Consumir la API de TMDB para mostrar las películas más populares en tarjetas estilizadas y añadir una funcionalidad de filtro por género.

### **Descripción**
1. Usa la API de TMDB para obtener:
   - La lista de películas populares.
   - La lista de géneros disponibles.
2. Muestra las películas en tarjetas que incluyan:
   - Imagen de la película.
   - Título.
   - Fecha de estreno.
   - Puntuación (Rating).
3. Añade un menú desplegable que permita al usuario filtrar las películas por género.

### **API endpoints**
- Obtener películas populares:
  ```
  https://api.themoviedb.org/3/movie/popular?api_key=TU_API_KEY&language=es-ES&page=1
  ```
- Obtener géneros:
  ```
  https://api.themoviedb.org/3/genre/movie/list?api_key=TU_API_KEY&language=es-ES
  ```

### **Requisitos**
- Implementa CSS avanzado para estilizar las tarjetas (incluye sombras, efectos de hover, etc.).
- Añade un menú desplegable que filtre las películas por género.
- Gestiona los errores en caso de que la API falle.

### **Mejoras**
- Realizar un buscador para filtrar películas por el título.
